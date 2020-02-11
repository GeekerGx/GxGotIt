# 深入浅出React和Redux

## React新的前端思维方式
### 初始化一个React项目
create-react-app  
### 增加一个新的React组件
#### JSX
> 所谓JSX，是JavaScript的语法扩展（eXtension），让我们在JavaScript中可以编写像HTML一样的代码。  

ReactDOM.render  
onClick（React）和onclick（HTML）  
#### JSX是进步还是倒退
### 分解React应用
### React作方式方式
#### jQuery如何工作
#### React的理念
> UI=render(data)  
#### Virtual DOM
#### React工作方式的优点

## 设计高质量的React组件
### 易于维护组件的设计要素
### React组件的数据
> “差劲的程序员操心代码，优秀的程序员操心数据结构和它们之间的关系。”  
> ——Linus Torvalds,Linux创始人  
#### React的prop
#### React的state
#### prop和state的对比
> prop用于定义外部接口，state用于记录内部状态；  
> prop的赋值在外部世界使用组件时，state的赋值在组件内部；  
> 组件不应该改变prop的值，而state存在的目的就是让组件来改变的。  
### 组件的生命周期
#### 载过过程（Mount）
> constructor  
> getlnitialState  
> getDefaultProps  
> componentWillMount  
> render  
> componentDidMount  
#### 更新过程（Update）
> componentWillReceiveProps  
> shouldComponentUpdate  
> componentWillUpdate  
> render  
> componentDidUpdate  
#### 卸载过程（Unmount）
> componentWillUnmount  
### 组件向外传递数据
### React组件state和prop的局限

## 从Flux到Redux
### Flux
#### MVC 框架的缺陷
> Model（模型）负责管理数据，大部分业务逻辑也应该放在Model中；  
> View（视图）负责渲染用户界面，应该避免在View中涉及业务逻辑；  
> Controller（控制器）负责接受用户输入根据用户输入调用对应的Model部分逻辑，把产生的数据结果交给View部分，让View渲染出必要的输出。  

> 一个Flux应用包含四个部分，我们先粗略了解一下：  
> Dispatcher，处理动作分发，维持Store之间的依赖关系；  
> Store，负责存储数据和处理数据相关逻辑；  
> Action，驱动 Dispatcher的JavaScript对象；  
> View，视图部分，负责显示用户界面。  

> 如果非要把Flux和MVC做一个结构对比，那么，Flux的Dispatcher相当于MVC的Controller,Flux的Store相当于MVC的Model,Flux的View当然就对应MVC的View了，至于多出来的这个Action，可以理解为对应给MVC框架的用户请求。  
#### Flux应用

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

#### Flux的优势
#### Flux的不足
### Redux
#### Redux的基本原则
> 唯一数据源(Single Source of Truth);  
> 保持状态只读(State is read-only);  
> 数据改变只能通过纯函数完成(Changes are made with pure functions);  

在计算机编程的世界里，完成任何一件任务，可能都有一百种以上的方法，但是无节制的灵活度反而让软件难以维护，增加限制是提高软件质量的法门。  
> “如果你愿意限制做事方式的灵活度，你几乎总会发现可以做得更好。”  
> ——John Carmark  
#### Redux实例

``` js
//connect(mapStateToProps, mapDispatchToProps)(Counter)
//connect 来源react-redux
//mapStateToProps
```

#### 容器组件和傻瓜组件
#### 组件Context
#### React-Redux

## 模块化React和Redux应用
### 模块化应用要点
### 代码文件的组织方式
#### 按角色组织
#### 按功能组织
### 模块接口
### 状态树的设计
#### 一个状态节点只属于一个模块
#### 避免冗余数据
#### 树形结构扁平
### Todo应用实例
#### Todo状态设计
#### action构造函数
#### 组合reducer
#### Todo视图
#### 样式
#### 不使用ref
### 开发辅助工具
#### Chrome扩展包
#### redux-immutable-state-invariant辅助包
#### 工具应用
