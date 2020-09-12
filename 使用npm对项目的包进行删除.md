

上传文件我们都知道，比如在window操作系统下，下载winscp，其他工具比如FileZilla，来连接远程服务器，然后上传文件。当我往机器上传项目文件时，直接复制拷贝。或者解压缩时。上传还算快的，如果是以压缩包的形式的话。

但是当我想要从机器中删除项目时，尤其是删除node_modules里面的文件时，你会发现删除十分的慢。

怎么删除包？
#### uninstall  dependencies in package.json
比如我的项目中有这些包

```
axios, vue, vue-router, vue-server-renderer, vuetify, vuex
cord-js
cors, express, express-sesssion, request
```
那我就一个一个记下来

```
dev:
@vue/cli-plugin-babel, 
@vue/cli-plugin-eslint,
@vue/cli-service,
babel-eslint,
eslint,
eslint-plugin-vue,
stylus,
stylus-loader,
vue-cli-plugin-vuetify,
vue-template-compiler,
vuetify-loader
```
然后在前面加上`npm uninstall`或者`npm install`
```
dev:
npm uninstall @vue/cli-plugin-babel, 
npm uninstall @vue/cli-plugin-eslint,
npm uninstall @vue/cli-service,
npm uninstall babel-eslint,
npm uninstall eslint
npm uninstall eslint-plugin-vue
npm uninstall stylus
npm uninstall stylus-loader
npm uninstall vue-cli-plugin-vuetify
npm uninstall vue-template-compiler
npm uninstall vuetify-loader
```

可以复制然后粘贴到终端，这些会一个一个执行的。

其实有一个程序化的卸载所有方法，不过不好用，会报错比如某个包需要依赖另一个包，然后就卸载不了。