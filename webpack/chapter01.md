## entry 单个入口写法
```
{
  entry: './path/to/my/entry/file.js'
}
```
相当于
```
{
  entry: {
    main: './path/to/my/entry/file.js'
  }
}
```

## entry 对象写法
```
entry: {
  app: './src/app.js',
  adminApp: './src/adminApp.js'
}
```

## output 用法
```
output: {
  filename: 'bundle.js',
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
