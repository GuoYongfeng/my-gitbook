### <a id="toc-running-babel-cli-from-within-a-project"></a>在项目内运行 Babel CLI

尽管你*可以*把 Babel CLI 全局安装在你的机器上，但是按项目逐个安装在**本地**会更好。

有两个主要的原因。

  1. 在同一台机器上的不同项目或许会依赖不同版本的 Babel 并允许你有选择的更新。
  2. 这意味着你对工作环境没有隐式依赖，这让你的项目有很好的可移植性并且易于安装。

要在（项目）本地安装 Babel CLI 可以运行：

```sh
$ npm install --save-dev babel-cli
```

> **注意：**由于全局运行 Babel 是一个坏习惯，如果你要卸载全局安装的版本可以运行：`npm uninstall --global babel-cli`。.

安装完成后，你的 `package.json` 应该如下所示：

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "devDependencies": {
    "babel-cli": "^6.0.0"
  }
}
```

现在，我们不直接从命令行运行 Babel 了，取而代之我们将把运行命令写在 **npm scripts** 里，这样可以使用 Babel 的本地版本。

只需将 `"scripts"` 字段添加到你的 `package.json` 文件内并且把 babel 命令写成 `build` 字段。.

```diff
  {
    "name": "my-project",
    "version": "1.0.0",
+   "scripts": {
+     "build": "babel src -d lib"
+   },
    "devDependencies": {
      "babel-cli": "^6.0.0"
    }
  }
```

现在可以在终端里运行：

```js
npm run build
```

这将以与之前同样的方式运行 Babel，但这一次我们使用的是本地副本。
