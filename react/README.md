## jsx
1. 基于 js 的语言，融合了 xml
2. js 中书写 xml
3. 一个顶层元素，且不是 body
4. 支持插值表达式（布尔值、null、undefined不会输出）
5. 插值表达式不能直接输出对象
6. 输出数组对象，对数组转字符串处理，并且使用空字符串进行拼接
7. 属性设置和 html/xml 类似，val 可以用字符串或者插值表达式

## jsx 样式设置
1. clasName 代替 class
2. style 值必须使用对象，对象必须放在插值表达式里面

## 列表输出
1. react 中没有模块语法，插值表达式只支持表达式，不支持语句（for、if）
2. 可以书写函数表达式，数组使用 map，对象使用 Object.keys()

## 封装函数复用
1. 在 react 中叫组件
2. 拥有独立功能的一个模块
3. 提供了另外一种调用方式，标签方式
4. 标签化传参，通过标签属性传参，组件接收一个 props 对象，接收所有标签上所有的属性

## 用类实现组件化
1. 组件类需要继承 React.Component
2. 一个函数或者类作为组件去使用的化，名称必须首字母大写
3. 组件类必须实现一个 render() 方法

## state
1. react 事件处理函数的 this 需要用 bind 函数进行绑定
```
// 定义状态
constructor() {
  super(...arguments);
  this.state = {
    attr: val;
  }
}

// 修改状态
this.setState({
  attr: val;
})
```

## 子集向父级传递数据
1. 父级定义方法，自己执行父级定义的方法
2. 父组件改变 state，子组件定义是否更新生命周期函数

## 生命周期
挂载阶段：
1. constructor()
2. componentWillmount()
3. render()
4. componentDidMount();

更新阶段
1. componentWillReceiveProps(nextProps)
  - 父组件更新会触发子组件的这个函数
  - nextProps 父组件更新带来的参数
2. shouldComponentUpdate(nextProps, nextState)
  - 是否需要重新渲染
  - return true/false
3. componentWillUpdate(nextProps, nextState)
4. render()
5. compontDidUpdate(prevProps, prevState)

## script type
bable/babel

