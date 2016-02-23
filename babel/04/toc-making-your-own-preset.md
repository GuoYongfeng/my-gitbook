## <a id="toc-making-your-own-preset"></a>制作你自己的预设（preset）

手动指定插件？插件选项？环境特定设置？所有这些配置都会在你的项目里产生大量的重复工作。

为此，我们鼓励社区创建自己的预设。 这可能是一个针对特定 [node 版本](https://github.com/leebenson/babel-preset-node5)的预设，或是适用于你[整个](https://github.com/cloudflare/babel-preset-cf)[公司](https://github.com/airbnb/babel-preset-airbnb)的预设。.

创建预设非常容易。比方说你这样一个 `.babelrc` 文件：

```js
{
  "presets": [
    "es2015",
    "react"
  ],
  "plugins": [
    "transform-flow-strip-types"
  ]
}
```

你要做的就是依循命名约定 `babel-preset-*` 来创建一个新项目（请务必对这个命名约定保持责任心，也就是说不要滥用这个命名空间），然后创建两个文件。

首先，创建一个 `package.json`，包括针对预设所必要的 `dependencies`。

```js
{
  "name": "babel-preset-my-awesome-preset",
  "version": "1.0.0",
  "author": "James Kyle <me@thejameskyle.com>",
  "dependencies": {
    "babel-preset-es2015": "^6.3.13",
    "babel-preset-react": "^6.3.13",
    "babel-plugin-transform-flow-strip-types": "^6.3.15"
  }
}
```

然后创建 `index.js` 文件用于导出 `.babelrc` 的内容，使用对应的 `require` 调用来替换 plugins／presets 字符串。

```js
module.exports = {
  presets: [
    require("babel-preset-es2015"),
    require("babel-preset-react")
  ],
  plugins: [
    require("babel-plugin-transform-flow-strip-types")
  ]
};
```

然后只需要发布到 npm 于是你就可以像其它预设一样来使用你的预设了。

* * *
