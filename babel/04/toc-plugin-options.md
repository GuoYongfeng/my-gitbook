## <a id="toc-plugin-options"></a>插件选项

很多插件也有选项用于配置他们自身的行为。 例如，很多转换器都有“宽松”模式，通过放弃一些标准中的行为来生成更简化且性能更好的代码。

要为插件添加选项，只需要做出以下更改：

```diff
  {
    "plugins": [
-     "transform-es2015-classes"
+     ["transform-es2015-classes", { "loose": true }]
    ]
  }
```

> 接下来几周内我会更新插件文档来详细介绍每一个选项。[关注我以获知更新](https://twitter.com/thejameskyle)。.
