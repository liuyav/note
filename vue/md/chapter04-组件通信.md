## 组件特性
1. 高内聚资源（组件资源内部高内聚html、css、js，组件资源由自身加载控制）
2. 作用域独立，组件内部变化不会对外部产生影响
3. 自定义标签
4. 可相互组合（组件之间相互组合，构成页面）
5. 规范化接口（参数同一规范，管理生命周期）
6. 组件是通用的，里面不要写具体的业务逻辑，业务逻辑交给需要的地方去写（需要的地方需要知道，组件内部发生的某件事情，在做处理）

## 单向数据流
父级的 props 的更新会向下流动到子组件中，反过来不行

这样会防止子组件意外修改父组件的状态，导致应用数据流向难以理解（父组件的状态使用很多地方，子组件改了，父组件其他地方也被改动了）

## 组件的双向数据绑定
如果确定状态的作用范围，不会影响其他组件的情况下，可以使用组件的双向绑定

父组件使用 .sync 修饰符，子组件触发 $emit('update:props', val)

组件v-model 实现，子组件使用 value 接收，子组件触发 $emit('input', val)

v-model会以value的形式把父组件的值传给子组件，v-model 会自动监听input事件

## Vue 组件通信方案
1. props/自定义事件
2. 事件总线（event bus）
3. Vuex 状态管理
4. 深层次组件$attrs和$listeners
5. provide 与 inject

## 父子组件
父组件向子组件传参，使用 props
子组件向父组件传参，使用自定义事件（子组件使用$emit发布一个事件，父组件使用v-on监听子组件发布的事件）

## 多层组件通信
发送事件，所有组件共有的对象，对象身上有on emit

新创建 new Vue，也可以使用根实例

使用根实例：
```
// 发布事件
this.$root.$emit('eventName', val)
// 监听事件
this.$root.$on('eventName', fn)
```

新创建对象：
```
Vue.use({
  install(vue) {
    Vue.prototype.$eventBus = new Vue;
  }
})

// 发布事件
this.$eventBus.$emit('eventName', val)
// 监听事件
this.$eventBus.$on('eventName', fn)
```

弊端：
1. 谁都可以改，谁都可以监听，没有规则可言，没办法调试
2. $root 遇到内部使用的同名事件，也会触发

## Vuex
什么时候使用VueX:
1. 多个视图依赖同一状态
2. 来自不同视图的行为需要变更同一状态

state 定义状态：
```
// 定义
state: {
  n: 1
}

// 访问
this.$store.state.n
```

commit 改变状态：
```
// 定义状态
mutations: {
  changeN(state, m) {
    state.n = m;
  }
}

// 改变状态
this.$store.commit('changeN', 3)
```





