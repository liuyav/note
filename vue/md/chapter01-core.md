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

