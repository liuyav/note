#定位
用于构建用户界面的渐进式框架（易用、灵活、高效）
ps:vue是一个框架，代表一整套的解决方法。vue.js是一个库（库与框架的区别在于控制权）

##响应式
只有计划好的属性才可以做响应

原型方法与静态方法
原型方法必须通过实例来调用，静态方法用函数挂载

对象的响应属性
1. Vue.set(obj, attr, val) --- 静态方法
2. vm.$set(obj, attr, val) --- 实例方法
3. vm.attr = val; --- 改写属性

数组的响应属性
1. 使用数组的变异方法，变异方法共同特征（改写原数组）


##计算属性
定义在computed里面，他不是方法，属性的值是函数的返回值

作用：把处理数据的逻辑抽离在计算属性中，使模版更加轻易易读



##路由
rooter-link
1. 精准匹配：exact
2. to 跳转到指定路径
3. :to 跳转到命名视图（:to="{name: compName}"）

嵌套路由（子路由），children属性
1. 默认子路由，子路由path设置为空
2. 设置子路由之后，父路由名字不设置，放在子理由上

路由嵌套，路径不嵌套
1. 子路由里面的 path 写成绝对路径形式

单个路由对应多个视图组件
1. 使用 components

动态路径
1. path 中以 /path/:var? 变量定义,?（0-1次）
2. 在createed()生命周期通过路由信息对象参数获取
3. watch 监控路由信息对象，拿到参数

记录滚动条位置
1. scrollBehavior() 点击浏览器前进后退，切换导航时候触发

$router router实例对象

$route 当前激活的路由信息对象，每个组件实例都会有

##编程式导航
back()、forward()、go()、push()、replace()

##导航钩子函数
执行位置：router全局、单个路由、组件中

router实例上：beforeEach、afterEach
单个路由：beforeEnter
组件的钩子函数：beforeRouterEnter、beforeRouterUpdate、beforeRouterLeave

钩子函数接受参数：
to: 进入路由对象
from: 离开的路由对象
next: 用来绝对跳转和取消导航


##vuex
定义状态使用 state
状态的计算属性 getter
修改状态，提交一个 mutation
异步的状态，提交一个 action

mapState几种写法（扩展在计算属性上）
1. 接收一个函数（函数参数为state）
2. key/value 形式
3. 接收一个数组

mapGetters（扩展在计算属性上）

mapMutations、mapActions（扩展在methods上）
1. key/value 形式
2. mutation 传参写在行间


##axios
自定义请求实例
axios.create({})

transformRequest转换请求（只适合于put、post、patch）
1. 转化发送数据（data）的格式
2. 了解 content-type

transformResponse转换响应
1. 转换返回数据的格式

validateStatus：设置请求状态成功状态码范围

cancelToken: 取消请求

并发请求
1. axios.all()
2. axios.spread() 分割并发请求参数

axios.interceptors.request.use()请求拦截器（请求之前对config进行操作）
axios.interceptors.response.use()请求拦截器（请求之前对config进行操作）

