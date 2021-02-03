# fed-e-task-04-05-master
1.通过该项目，请简要说明 typescript 比 javascript 的优势在哪？

    a. ts 为 js 增加了一个类型系统, 静态检测代码类型, 开发者可以在运行之前就被提示错误信息, 对于有类型限制的数据, 在可读性上面也有很大的优势.
    
    b. js本身为弱类型语言, 也有着隐式转换、运行时确认类型的特点, 但也是这些原因, 在项目体量越来越大的时候, 其劣势也就越来越明显, 使用ts, 可以使得代码在 可读性、延展性、减少出错 上面有很大的优势.
    
    c. ts 是 js 的超集, 这意味着在 ts 中写 js 也是兼容的
    
    d. IDE支持, 以vscode为例, 在对于类型接口都有类型提示, 便于开发者进行开发

2.请简述一下支付流程
    
    a. 客户端点击购买, 向服务端发送请求, 并入参相应参数 

    b. 服务端根据接收的信息, 校验通过后, 向支付宝下单, 并获取支付地址, 将该地址传回客户端

    c. 客户端获取地址后, 跳转到该支付地址

    d. 该地址为支付宝的地址, 在操作登录后(如果未登录), 支付订单

    e. 支付宝收到支付请求, 校验通过后, 向服务端发送支付成功的通知, 服务端修改相应订单内容, 支付宝通知客户端支付成功

    f. 客户端展示支付成功界面, 尔后跳转到购物车界面

3.react-redux 的主要作用是什么，常用的 api 有哪些，什么作用？

    react-redux 使得 react 组件能够从 redux 读取数据、调度actions 到容器中修改数据

    常用api： 

      a. Provider：包裹react内容的组件, 入参属性store, 其后代组件可以使用 connect 方法从 store中获取、修改数据

      b. connect：它为连接的组件提供了存储中所需的数据片段，以及可用于向存储调度操作的功能

      c. hooks: 提供一组钩子api, 用于取代现有的 connect 高阶组件, 这些API允许您订阅Redux存储和调度操作，而不必将组件包装在connect()中
            useSelector: 从 Redux store state 中提取数据
            useDispatch: 从 Redux store 中返回对 dispatch 的引用, 在需要的时候执行 dispatch actions
            useStore: 返回对 Provider 入参 store 的对象的引用

4.redux 中的异步如何处理？

    a. redux-thunk: 在中间件函数内部 action 增加了 function 类型的判断, action是函数的话, 返回函数的执行结果. 如此, 异步就可以写在函数内部

    b. redux-saga: 暴露 put、takeEvery, 配合generator函数, 实现异步, 其将api与store解耦, 是比redux-thunk更好的解决方式
