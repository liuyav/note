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

## 技巧
1. vuex 管理数据实现缓存