# 深入浅出React和Redux

## 1 React新的前端思维方式
### 1.1 初始化一个React项目
create-react-app  
### 1.2 增加一个新的React组件
#### 1.2.1 JSX
> 所谓JSX，是JavaScript的语法扩展（eXtension），让我们在JavaScript中可以编写像HTML一样的代码。  

ReactDOM.render  
onClick（React）和onclick（HTML）  
#### 1.2.2 JSX是进步还是倒退
### 1.3 分解React应用
### 1.4 React作方式方式
#### 1.4.1j Query如何工作
#### 1.4.2 React的理念
> UI=render(data)  
#### 1.4.3 Virtual DOM
#### 1.4.4 React工作方式的优点

## 2 设计高质量的React组件
### 2.1 易于维护组件的设计要素
### 2.2 React组件的数据
> “差劲的程序员操心代码，优秀的程序员操心数据结构和它们之间的关系。”  
> ——Linus Torvalds,Linux创始人  
#### 2.2.1 React的prop
#### 2.2.2 React的state
#### 2.2.3 prop和state的对比
> prop用于定义外部接口，state用于记录内部状态；  
> prop的赋值在外部世界使用组件时，state的赋值在组件内部；  
> 组件不应该改变prop的值，而state存在的目的就是让组件来改变的。  
### 2.3 组件的生命周期
#### 2.3.1 载过过程（Mount）
> constructor  
> getlnitialState  
> getDefaultProps  
> componentWillMount  
> render  
> componentDidMount  
#### 2.3.2 更新过程（Update）
> componentWillReceiveProps  
> shouldComponentUpdate  
> componentWillUpdate  
> render  
> componentDidUpdate  
#### 2.3.3 卸载过程（Unmount）
> componentWillUnmount  
### 2.4 组件向外传递数据
### 2.5 React组件state和prop的局限

## 3 从Flux到Redux
### 3.1 Flux
#### 3.1.1 MVC 框架的缺陷
> Model（模型）负责管理数据，大部分业务逻辑也应该放在Model中；  
> View（视图）负责渲染用户界面，应该避免在View中涉及业务逻辑；  
> Controller（控制器）负责接受用户输入根据用户输入调用对应的Model部分逻辑，把产生的数据结果交给View部分，让View渲染出必要的输出。  

> 一个Flux应用包含四个部分，我们先粗略了解一下：  
> Dispatcher，处理动作分发，维持Store之间的依赖关系；  
> Store，负责存储数据和处理数据相关逻辑；  
> Action，驱动 Dispatcher的JavaScript对象；  
> View，视图部分，负责显示用户界面。  

> 如果非要把Flux和MVC做一个结构对比，那么，Flux的Dispatcher相当于MVC的Controller,Flux的Store相当于MVC的Model,Flux的View当然就对应MVC的View了，至于多出来的这个Action，可以理解为对应给MVC框架的用户请求。  
#### 3.1.2 Flux应用

``` txt
npm i flux
```

监听者模式

``` js

import {EventEmitter} from 'events';

Object.assign({}, EventEmitter.prototype, {
    //some thing
    //emit(CHANGE_EVENT) 触发change
    //on(CHANGE_EVENT, callback) 绑定change事件
    //removeListener(CHANGE_EVENT, callback) 移除change事件
    //dispatchToken
});

```

#### 3.1.3 Flux的优势
#### 3.1.4 Flux的不足
### 3.2 Redux
#### 3.2.1 Redux的基本原则
> 唯一数据源(Single Source of Truth);  
> 保持状态只读(State is read-only);  
> 数据改变只能通过纯函数完成(Changes are made with pure functions);  

在计算机编程的世界里，完成任何一件任务，可能都有一百种以上的方法，但是无节制的灵活度反而让软件难以维护，增加限制是提高软件质量的法门。  
> “如果你愿意限制做事方式的灵活度，你几乎总会发现可以做得更好。”  
> ——John Carmark  
#### 3.2.2 Redux实例

``` js
//connect(mapStateToProps, mapDispatchToProps)(Counter)
//connect 来源react-redux
//mapStateToProps
```

#### 3.2.3 容器组件和傻瓜组件
#### 3.2.4 组件Context
#### 3.2.5 React-Redux

## 4 模块化React和Redux应用
### 4.1 模块化应用要点
### 4.2 代码文件的组织方式
#### 4.2.1 按角色组织
#### 4.2.2 按功能组织
### 4.3 模块接口
> “在最理想的情况下，我们应该通过增加代码就能增加系统的功能，而不是通过对现有代码的修改来增加功能。”  
> ——Robert C. Martin  
### 4.4 状态树的设计
> 一个模块控制一个状态节点；  
> 避免冗余数据；  
> 树形结构扁平；  
#### 4.4.1 一个状态节点只属于一个模块
#### 4.4.2 避免冗余数据
#### 4.4.3 树形结构扁平
### 4.5 Todo应用实例
#### 4.5.1 Todo状态设计
#### 4.5.2 action构造函数
#### 4.5.3 组合reducer
#### 4.5.4 Todo视图
#### 4.5.5 样式
#### 4.5.6 不使用ref
### 4.6 开发辅助工具
#### 4.6.1 Chrome扩展包
#### 4.6.2 redux-immutable-state-invariant辅助包
#### 4.6.3 工具应用

## 5 React组件的性能优化
### 5.1 单个React组件的性能优化
#### 5.1.1 发现浪费的渲染时间
chrome安装React Perf插件
#### 5.1.2 性能优化的时机
> “我们应该忘记忽略很小的性能优化，可以说97%的情况下，过早的优化是万恶之源，而我们应该关心对性能影响最关键的那另外3%的代码。”  
> ——高德纳  

> 开发者永远要考虑到极端情况。  
#### 5.1.3 React-Redux的shouldComponentUpdate实现
### 5.2 多个React组件的性能优化
#### 5.2.1 React的调和(Reconciliation)过程
#### 5.2.2 Key的用法
### 5.3 用reselect提高数据获取性能
#### 5.3.1 两阶段选择过程
#### 5.3.2 范式化状态树

## 6 React高级组件
> “重复是优秀系统设计的大敌。”  
> ——Robert C.Martin  
### 6.1 高阶组件
#### 6.1.1 代理方式的高阶组件
#### 6.1.2 继承方式的高阶组件
#### 6.1.3 高阶组件的显示名
#### 6.1.4 曾经的React Mixin
### 6.2 以函数为子组件
#### 6.2.1 实例CountDown
#### 6.2.2 性能优化问题

## 7 Redux和服务器通信
### 7.1 React组件访问服务器
#### 7.1.1 代理功能访问API
#### 7.1.2 React组件访问服务器的生命周期
#### 7.1.3 React组件访问服务器的优缺点
### 7.2 Redux访问服务器
#### 7.2.1 redux-thunk中间件
#### 7.2.2 异步action对象
#### 7.2.3 异步操作的模式
#### 7.2.4 异步操作的中止
### 7.3 Redux异步操作的其他方法
#### 7.3.1 如何挑选异步操作方式
#### 7.3.2 利用Promise实现异步操作

## 8 单元测试
### 8.1 单元测试的原则
### 8.2 单元测试环境搭建
#### 8.2.1 单元测试框架
#### 8.2.2 单元测试代码组织
#### 8.2.3 辅助工具
### 8.3 单元测试实例
#### 8.3.1 action构造函数测试
#### 8.3.2 异步action构造函数测试
#### 8.3.3 reducer测试
#### 8.3.4 无状态React组件测试
#### 8.3.5 被连接的React组件测试

## 9 扩展Redux
### 9.1 中间件
#### 9.1.1 中间件接口
#### 9.1.2 使用中间件
#### 9.1.3 Promise中间件
#### 9.1.4 中间件开发原则
### 9.2 Store Enhancer
#### 9.2.1 增强器接口
#### 9.2.2 增强器实例reset

## 10 动画
### 10.1 动画的实现方式
#### 10.1.1 CSS3方式
#### 10.1.2 脚本方式
### 10.2 ReactCSSTransitionGroup
#### 10.2.1 Todo应用动画
#### 10.2.2 ReactCSSTransitionGroup规则
### 10.3 React-Motion动画库
#### 10.3.1 React-Motion的设计原则
#### 10.3.2 Todo应用动画

## 11 多页面应用
### 11.1 单页应用
### 11.2 React-Router
#### 11.2.1 路由
#### 11.2.2 路由链接和嵌套
#### 11.2.3 默认链接
#### 11.2.4 集成Redux
### 11.3 代码分片
#### 11.3.1 弹射和配置webpack
#### 11.3.2 动态加载分片
#### 11.3.3 动态更新Store的reducer和状态

## 12 同构
### 12.1 服务器端渲染vs浏览器端渲染
### 12.2 构建渲染动态内容服务器
#### 12.2.1 设置Node.js和Express
#### 12.2.2 热加载
### 12.3 React同构
#### 12.3.1 React服务器端渲染THML
#### 12.3.2 脱水和注水
#### 12.3.3 服务器端Redux Store
#### 12.3.4 支持服务器和浏览器获取共同数据源
#### 12.3.5 服务器端路由
### 12.4 同构实例
