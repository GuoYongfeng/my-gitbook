## <a id="toc-babel-preset-react"></a>`babel-preset-react`

设置 React 一样容易。只需要安装这个预设：

```sh
$ npm install --save-dev babel-preset-react
```

然后在 `.babelrc` 文件里补充：

```diff
  {
    "presets": [
      "es2015",
+     "react"
    ],
    "plugins": []
  }
```
