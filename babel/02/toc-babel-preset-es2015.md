## <a id="toc-babel-preset-es2015"></a>`babel-preset-es2015`

我们先从让 Babel 把 ES2015（最新版本的 JavaScript 标准，也叫做 ES6）编译成 ES5（现今在大多数 JavaScript 环境下可用的版本）开始吧。

我们需要安装 "es2015" Babel 预设：

```sh
$ npm install --save-dev babel-preset-es2015
```

我们修改 `.babelrc` 来包含这个预设。

```diff
  {
    "presets": [
+     "es2015"
    ],
    "plugins": []
  }
```
