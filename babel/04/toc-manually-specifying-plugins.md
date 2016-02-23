## <a id="toc-manually-specifying-plugins"></a>手动指定插件

Babel 预设就是一些预先配置好的插件的集合，如果你想要做一些不一样的事情你会手动去设定插件，这和使用预设几乎完全相同。

首先安装插件：

```sh
$ npm install --save-dev babel-plugin-transform-es2015-classes
```

然后往 `.babelrc` 文件添加 `plugins` 字段。.

```diff
  {
+   "plugins": [
+     "transform-es2015-classes"
+   ]
  }
```

这能让你对正在使用的转换器进行更细致的控制。
