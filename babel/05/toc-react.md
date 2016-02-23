### <a id="toc-react"></a>React

React 已经大幅改变了他们的 API 以适应 ES2015 的类语法（[此处了解更新的 API](http://babeljs.io/blog/2015/06/07/react-on-es6-plus/)）。 再者，React 依赖 Babel 来编译它的 JSX 语法，并弃用了它自己的工具来支持 Babel。 你可以按照[上述说明](#babel-preset-react)安装 `babel-preset-react` 包来开始。.

React 社区采用 Babel 并围绕它来运行，现在社区已经创建了[大量的转换器（transforms）](https://www.npmjs.com/search?q=babel-plugin+react)。.

最令人瞩目的是 [`babel-plugin-react-transform`](https://github.com/gaearon/babel-plugin-react-transform) 插件，它集成了大量 [React 专用转换器](https://github.com/gaearon/babel-plugin-react-transform#transforms)可以启用诸如 *热模块重载*等其他调试工具。

<!--
### Ember

> [WIP]
-->
