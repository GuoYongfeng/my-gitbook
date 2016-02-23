
## <a id="toc-babel-cli"></a>`babel-cli`

Babel 的 CLI 是一种在命令行下使用 Babel 编译文件的简单方法。

让我们先全局安装它来学习基础知识。

```sh
$ npm install --global babel-cli
```

我们可以这样来编译我们的第一个文件：

```sh
$ babel my-file.js
```

这将把编译后的结果直接输出至终端。使用 `--out-file` 或着 `-o` 可以将结果写入到指定的文件。.

```sh
$ babel example.js --out-file compiled.js
# 或
$ babel example.js -o compiled.js
```

如果我们想要把一个目录整个编译成一个新的目录，可以使用 `--out-dir` 或者 `-d`。.

```sh
$ babel src --out-dir lib
# 或
$ babel src -d lib
```
