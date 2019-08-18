## vue 工作机制
new Vue() 之后，初始化生命周期、事件、props、methods、data、computed、watch等，最重要的通过 Object.definePropety 设置 setter 与 getter，实现响应和依赖收集

初始化之后调用 $mount 挂载组件

$mount 会启动编译器

编译器（对模版的扫码）会做这些事情：
1. 初始化视图
2. 初始化 watcher

编译器在这个阶段会生成一些渲染函数（更新函数），生成 vdom 树（在进行数据更新的时候会进行 diff 算法比较，计算中做的最小dom更新，这样做，用js的计算时间换取dom操作时间）

编译器会做依赖收集，通过 watcher 监听实现更新

编译模块分为三个步骤：
1. parse（解析界面非html部分代码，形成语法树AST）
2. optimize（标记一些静态节点，用于后面的性能优化，在diff时候直接略过）
3. generate（把一部分生成的AST转化为渲染函数）

paser 任务
1. 转换内部内容为片段Fragment
2. 执行编译，将编译完html结果追加在 $el


## 虚拟dom
用js对象的形式模拟dom节点，进行dom节点的比对

## 响应式原理