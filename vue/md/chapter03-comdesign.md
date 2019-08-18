## 组件化
学习 element ui 中优秀的组件设计

vue-cli3 中安装 element：vue add element

## element form 设计
1. input 的 v-model 双向数据绑定
   - 传递 value 属性
   - 监听 input 事件
2. slot 插槽实现组件嵌套设计
3. 数据模式和检验规则传递给内部组件
   - provide
   - inject
4. input 值发生改变，怎样通知父组件做校验（校验规则在input父组件上）
   - this.parent.$emit()
5. 怎样进行校验
   - 基于 async-validator
     - new Schema(rules).validator({values}, err=> {})

## 注意事项
1. 组件标签名字小写