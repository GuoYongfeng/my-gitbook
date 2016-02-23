## <a id="toc-babel-polyfill"></a>`babel-polyfill`

Babel 几乎可以编译所有时新的 JavaScript 语法，但对于 APIs 来说却并非如此。

比方说，下列含有箭头函数的需要编译的代码：

```js
function addAll() {
  return Array.from(arguments).reduce((a, b) => a + b);
}
```

最终会变成这样：

```js
function addAll() {
  return Array.from(arguments).reduce(function(a, b) {
    return a + b;
  });
}
```

然而，它依然无法随处可用因为不是所有的 JavaScript 环境都支持 `Array.from`。

    Uncaught TypeError: Array.from is not a function


为了解决这个问题，我们使用一种叫做 [Polyfill（代码填充，也可译作兼容性补丁）](https://remysharp.com/2010/10/08/what-is-a-polyfill) 的技术。 简单地说，polyfill 即是在当前运行环境中用来复制（意指模拟性的复制，而不是拷贝）尚不存在的原生 api 的代码。 能让你提前使用还不可用的 APIs，`Array.from` 就是一个例子。

Babel 用了优秀的 [core-js](https://github.com/zloirock/core-js) 用作 polyfill，并且还有定制化的 [regenerator](https://github.com/facebook/regenerator) 来让 generators（生成器）和 async functions（异步函数）正常工作。

要使用 Babel polyfill，首先用 npm 安装它：

```sh
$ npm install --save babel-polyfill
```

然后只需要在文件顶部导入 polyfill 就可以了：

```js
import "babel-polyfill";
```
