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
### 组件向外传递数据
### React组件state和prop的局限
