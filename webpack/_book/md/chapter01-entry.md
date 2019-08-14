## Ready
1. 安装 webpack
2. 安装 webpack-cli

## webpack 命令
1. webpack 默认执行 webpack.cofig.js
2. webpack --config filename（运行一个webpack任务）

## entry 单个入口写法
```
module.exports = {
  entry: './path/to/my/entry/file.js'
}
```
相当于
```
module.exports = {
  entry: {
    main: './path/to/my/entry/file.js'
  }
}
```

## entry 对象写法
```
module.exports = {
  entry: {
    app: './src/app.js',
    adminApp: './src/adminApp.js'
  }
}
```

## output 用法
1. 接收一个绝对路径

```
module.exports = {
  output: {
    filename: 'bundle.js',
    path: 
  }
}
```
filename: 用于指定输出文件的文件名，输出一个 bundle.js 到 dist 目录下

## output 多个入口的出口
使用占位符保证每个文件都有唯一的名字，例：
```
module.exports = {
  entry: {
    app: './src/app.js',
    search: './src/search.js'
  },
  output: {
    filename: '[name].js',
    path: __dirname + '/dist'
  }
};

// 写入到硬盘：./dist/app.js, ./dist/search.js
```



## devServer
1. webpack-dev-server（开启devServer，默认执行webpack.config.js）
2. webpack-dev-server --config filename（以filename跑一个devServer任务）
2. 运行命令，对文件进行打包，打包在内存中

## loader
1. 帮助处理文件内容，多个loader按照从下往上、从右往左的顺序执行loader
2. babel-loader babel-core
3. css-loader 处理css模块
4. style-loader 将css模块处理的内容插入都结构中
5. 在webpack中在css中引入资源，webpack视为模块，需要引入file-loader进行处理
6. file-loader 将图片移动到打包目录、图片重命名、生成一个路径（sadasdsah.jpg）
7. 引入一个图片模块时候，会引入一个路径（类型文件名字的路径）
8. url-loader 增强的 file-loader，可实现根据图片大小进行编码或者打包
9. 加载资源时候，webpack会忽略？之后的内容
10. css-loader module:true 启动 css 模块化
11. exclude 排除匹配
12. include 包含匹配


## 插件（帮助做一些事情）
1. html-webpack-plugin
2. NamedChunksPlugin（开发模式自动加的插件、根据文件名来稳定你的chunkid）
3. NamedModulesPlugin（开发模式自动加的插件、在热加载时直接返回更新文件名，而不是文件的id）
4. UglifyJsPlugin（生产模式自动启用的插件、用来压缩js）
5. NoEmitOnErrorsPlugin（生产模式自动启用的插件、遇到错误代码不跳出）
6. ModuleConcatenationPlugin（生产模式自动启用的插件、作用域提升）
7. FlagIncludedChunksPlugin（生产模式自动启用的插件、检测并标记模块之间的从属关系）
8. OccurrenceOrderPlugin（生产模式自动启用的插件、告诉webapck各个模块间的先后顺序，这样可以实现最优的构建输出。）
9. SideEffectsFlagPlugin（生产模式自动启用的插件、告诉webapck去清除一个大的模块文件中的未使用的代码，这个大的文件模块可以是自定义的，也可以是第三方的（注意：一定要 package.json 文件中添加 sideEffects": false）。）

## mode
1. 设置 mode 会更改 process.env.NODE_ENV 的值，并启用相应的插件
2. development 会启用 NamedChunksPlugin、NamedModulesPlugin
3. production 会启用 UglifyJsPlugin、NoEmitOnErrorsPlugin、ModuleConcatenationPlugin、FlagIncludedChunksPlugin、OccurrenceOrderPlugin、SideEffectsFlagPlugin、FlagDependencyUsagePlugin

