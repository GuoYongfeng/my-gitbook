## <a id="toc-babel-register"></a>`babel-register`

下一个常用的运行 Babel 的方法是通过 `babel-register`。这种方法只需要引入文件就可以运行 Babel，或许能更好地融入你的项目设置。

但请注意这种方法并不适合正式产品环境使用。 直接部署用此方式编译的代码不是好的做法。 在部署之前预先编译会更好。 不过用在构建脚本或是其他本地运行的脚本中是非常合适的。

让我们先在项目中创建 `index.js` 文件。

```js
console.log("Hello world!");
```

如果我们用 `node index.js` 来运行它是不会使用 Babel 来编译的。所以我们需要设置 `babel-register`。.

首先安装 `babel-register`。.

```sh
$ npm install --save-dev babel-register
```

接着，在项目中创建 `register.js` 文件并添加如下代码：

```js
require("babel-register");
require("./index.js");
```

这样做可以把 Babel *注册*到 Node 的模块系统中并开始编译其中 `require` 的所有文件。

现在我们可以使用 `register.js` 来代替 `node index.js` 来运行了。

```sh
$ node register.js
```

> **注意：**你不能在你要编译的文件内同时注册 Babel，因为 node 会在 Babel 编译它之间就将它执行了。
>
> ```js
require("babel-register");
// 未编译的：
console.log("Hello world!");
```
