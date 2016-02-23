
## <a id="toc-babel-core"></a>`babel-core`

如果你需要以编程的方式来使用 Babel，可以使用 `babel-core` 这个包。

首先安装 `babel-core`。.

```sh
$ npm install babel-core
```

```js
var babel = require("babel-core");
```

字符串形式的 JavaScript 代码可以直接使用 `babel.transform` 来编译。.

```js
babel.transform("code();", options);
// => { code, map, ast }
```

如果是文件的话，可以使用异步 api：

```js
babel.transformFile("filename.js", options, function(err, result) {
  result; // => { code, map, ast }
});
```

或者是同步 api：

```js
babel.transformFileSync("filename.js", options);
// => { code, map, ast }
```

要是已经有一个 Babel AST（抽象语法树）了就可以直接从 AST 进行转换。

```js
babel.transformFromAst(ast, code, options);
// => { code, map, ast }
```

对于上述所有方法，`options` 指的都是 http://babeljs.io/docs/usage/options/

* * *
