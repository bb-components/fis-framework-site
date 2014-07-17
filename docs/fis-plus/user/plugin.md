---
layout: post
title: 插件配置
category: fis-plus/user
---

> FIS提供灵活易扩展的插件系统，用户可以在开发过程中根据需求新增各类编译流程插件，同时通过配置将二次开发的插件添加到处理流程中。

## 插件配置

fis编译系统具有一个既简单又容易扩展的插件体系，在不做任何定制的情况下即可满足前端开发的基本需求，与此同时，系统也具有极强的可扩展性，fis的两大编译流程一共提供了10项扩展点，再加上命令行扩展能力，fis系统一共具有 11项扩展点。在FIS-PC中，默认配置前端模板处理、XSS修复等插件：

```javascript
fis.config.set('modules', {
    parser : {
        less : 'less',  //对less文件处理的插件
        tmpl: 'bdtmpl'  //对前端模板处理的插件
    },
    postprocessor: {
        tpl: 'require-async',  //对tpl文件新增标准后处理器插件
        js: 'jswrapper, require-async' //对js文件新增标准后处理器插件
    },
    optimizer : {
        tpl : 'smarty-xss,html-compress' //对tpl文件新增xss修复以及压缩的代码优化器插件
    }
});

fis.config.set('settings.parser.bdtmpl', {
    //对前端模板处理的插件中，初始化参数
        LEFT_DELIMITER : '<#',
        RIGHT_DELIMITER : '#>'
});
```

用户可以在[插件扩展列表](http://fis.baidu.com/docs/advance/plugin-list.html)中，fis系统更多插件扩展的方式。

## 插件部署

插件开发完发布使用都为npm包的方式，本地使用时可直接进行本地npm包安装,同时用户需要将使用的插件名称告诉FIS组成员进行编译机部署。