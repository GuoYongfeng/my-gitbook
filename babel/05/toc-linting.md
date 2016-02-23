### <a id="toc-linting"></a>语法检查（Linting）

[ESLint](http://eslint.org) 是最流行的语法检查工具之一，因此我们维护了一个官方的 [`babel-eslint`](https://github.com/babel/babel-eslint) 整合软件包。

首先安装 `eslint` 和 `babel-eslint`。.

```sh
$ npm install --save-dev eslint babel-eslint
```

> **注意：**兼容 Babel 6 的 `babel-eslint` 目前正处于预发行版本。 安装[最新的](https://github.com/babel/babel-eslint/releases) 5.0 beta 版来兼容 Babel 6。

然后创建或使用项目现有的 `.eslintrc` 文件并设置 `parser` 为 `babel-eslint`。.

```diff
  {
+   "parser": "babel-eslint",
    "rules": {
      ...
    }
  }
```

现在添加一个 `lint` 任务到 npm 的 `package.json` 脚本中：

```diff
  {
    "name": "my-module",
    "scripts": {
+     "lint": "eslint my-files.js"
    },
    "devDependencies": {
      "babel-eslint": "...",
      "eslint": "..."
    }
  }
```

接着只需要运行这个任务就一切就绪了。

```sh
$ npm run lint
```

详细信息请咨询 [`babel-eslint`](https://github.com/babel/babel-eslint) 或者 [`eslint`](http://eslint.org) 的文档。

### <a id="toc-code-style"></a>代码风格

JSCS 是一个极受欢迎的工具，在语法检查的基础上更进一步检查代码自身的风格。 Babel 和 JSCS 项目的核心维护者之一（[@hzoo](https://github.com/hzoo)）维护着 JSCS 的官方集成。

更妙的是，JSCS 自己通过 `--esnext` 选项实现了这种集成，于是和 Babel 的集成就简化成了直接在命令行运行：

    $ jscs . --esnext


或者在 `.jscsrc` 文件里添加 `esnext` 选项。

```diff
  {
    "preset": "airbnb",
+   "esnext": true
  }
```

详细信息请咨询 [`babel-jscs`](https://github.com/jscs-dev/babel-jscs) 或是 [`jscs`](http://jscs.info) 的文档。

<!--
### Code Coverage

> [WIP]
-->
