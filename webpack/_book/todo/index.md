## Ready
1. 安装 webpack
2. 安装 webpack-cli

## webpack 命令
1. webpack --config filename（运行一个webpack任务）

## devServer
1. webpack-dev-server（开启devServer）
2. 运行命令，对文件进行打包，打包在内存中

## 插件
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

