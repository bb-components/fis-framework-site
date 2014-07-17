## fis-framework-site

### 书写文档一些注意事项

- 如果要引入图片，请放到 `assets/images/`下面，并在使用时使用`![]({{site.img}}/xxx.png)` 这种方式引入
- 如果需要添加侧边栏，请到`_data/navs`下对应的解决方案的数据文件中添加
- 每个文档必须设置category，category的规则是，何种解决方案就必须设置成解决方案的名字，比如`fis-plus`，必须是`fis-plus`。如果有子category则用`fis-plus/user`这种方式。
- 任何示例中出现分界符`{%`和`%}`的文档，需要将文档内容放置到`{% raw %} {% endraw %}`中间，防止被jekyll解析。_注意，如果加了这个，添加图片的变量`{{site.img}}`是无法解析的。_