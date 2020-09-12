

什么是Peer Dependencies？ 我翻译成“同等依赖”。看一下这个发表在Node.js官网的[文章](https://nodejs.org/es/blog/npm/peer-dependencies/)
可以理解成某个包依赖package A v1和package B v1，但是package B v1依赖于package B v1依赖于package A v2。 这里v1和v2表示的是版本。

只要弄明白这个概念，那么下次只要在npm中安装或卸载包时，如果出现某个包依赖于peer dependencies，就只要看看这个依赖会不会自动下载？如果作者没有在写这个插件的时候处理，那么自己安装。然后看一下npm官网`docs home - CLI document - Configuring npm -  package.json - peerDependencies`关于peer dependencies的[介绍](https://docs.npmjs.com/files/package.json.html#peerdependencies)。