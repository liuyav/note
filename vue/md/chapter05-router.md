## 路由详细配置参数
```
new Router({
  // 路由模式
  mode: '',
  routers: [
    {
      path: '/',
      redirect: PageA   // 路由重定向
      name: A   // 命名路由
    },
    {
      path: '/a',
      component: PageA,
    },
    {
      path: '/b/:id',
      component: PageBDetail
    }
  ],

})
```

## 导航
rooter-link
1. 精准匹配：exact
2. to 跳转到指定路径
3. :to 跳转到命名视图（:to="{name: compName}"）

嵌套路由（子路由），children属性
1. 默认子路由，子路由path设置为空
2. 设置子路由之后，父路由名字不设置，放在子理由上

路由嵌套，路径不嵌套
1. 子路由里面的 path 写成绝对路径形式

单个路由对应多个视图组件（命名视图）
1. 使用 components

动态路由
1. path 中以 /path/:var? 变量定义,?（0-1次）
2. 在createed()生命周期通过路由信息对象(this.$route)参数获取
   - 参数属性传递，给路由设置一个 props 设置为 true
3. watch 监控路由信息对象，拿到参数

记录滚动条位置
1. scrollBehavior() 点击浏览器前进后退，切换导航时候触发

$router router实例对象

$route 当前激活的路由信息对象，每个组件实例都会有

##编程式导航
back()、forward()、go()、push()、replace()

##导航钩子函数
执行位置：router全局、单个路由、组件中
  - 全局，每次路由跳转都会触发
  - 单个路由，写在配置里面

router实例上：
  - beforeEach：所有路由执行之前，数据校验的时候非常有用
  - beforeResolve：导航确认之前，所有组件内的守卫和异步路由解析之后，被调用
  - afterEach：全局后置钩子，可以用来设置页面元信息
    - 不需要下一步，没有next

单个路由：beforeEnter

组件的钩子函数：
  - beforeRouterEnter
    - 里面不能调用 this，原因是执行守卫的时候组件还没有被创建
  - beforeRouterUpdate
    - 当前路由改变，但是该组件被复用的时候调用（例：动态路径路由之间的跳转）
    - 可以访问 this
  - beforeRouterLeave
    - 导航离开该组件对应的路由被调用
    - 可以访问 this
    - 禁止用户还没保存数据之前离开

钩子函数接受参数：
to: 进入路由对象
from: 离开的路由对象
next: 用来绝对跳转和取消导航

## 异步组件
import()