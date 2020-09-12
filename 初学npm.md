# 初学npm


#### CLI documentation - Using npm - config - Shorthands and Other CLI Niceties

npm flag shorthands

npm的一些缩写

查看[文档](https://github.com/npm/npmconf/blob/master/config-defs.js#L405)， 比如

```
 ,D : ["--save-dev"] // npm i -D mocha-loader
 , y : ["--yes"]   // 比如 npm init -y
```




## CLI documentation - Using npm - scripts
#### misc-scripts

```
npm run-script <stage>

{
	"scripts": {
		"sayhi": "echo hello"
	}
}

npm run-script hello
or
npm run hello
```

## CLI 文档 > 配置 npm > packag

e.json



### main

```
The main field is a module ID that is the primary entry point to your program. That is, if your package is named foo, and a user installs it, and then does require("foo"), then your main module’s exports object will be returned.

This should be a module ID relative to the root of your package folder.

For most modules, it makes the most sense to have a main script and often not much else.
```

这个main字段是一个模块ID，这个模块ID是你的程序的主要入口点。就是说，如果你的包的名字是**foo**，并且一个用户安装了它，并且做了**require("foo")**，然后你的主要的模块的输出对象会被返回。

这个应该是一个模块ID，这个模块相对于你的包文件夹的根。

对于大多数模块来言，去拥有一个main脚本，并且通常没有别的，这是最有意义的。

> 上面说的是对于普通的包。那么这在webpack中算什么？是不是可以理解webpack这整个项目文件，算是一个包呢？即main就是要打包的入口文件的路径加上文件名。



关于D，看Main Concepts - 5. State and Lifecycle - Adding LifeCycle Methods to a Class 







## Packages and modules - Contributing packages to the registry - Creating and publishing unscoped public packages（创建并且发布unscoped公共包）





根据教程

```
$ npm publish
npm notice
npm notice package: s6-final-steps@1.0.0
npm notice === Tarball Contents ===
npm notice 396B   package.json
npm notice 81B    README.md
npm notice 424B   webpack.config.js
npm notice 72.6kB dist/index.bundle.js
npm notice 335B   dist/index.html
npm notice 72.7kB dist/webpack-numbers.js
npm notice 128B   src/anotherEntry.js
npm notice 603B   src/index.js
npm notice 350B   src/ref.json
npm notice === Tarball Details ===
npm notice name:          s6-final-steps
npm notice version:       1.0.0
npm notice package size:  51.9 kB
npm notice unpacked size: 147.6 kB
npm notice shasum:        fd577519acb2030a2fd9e23e0f1625c394b5d149
npm notice integrity:     sha512-vWup9YlDEVs5i[...]Yl9HfT4eJr6kg==
npm notice total files:   9
npm notice
npm ERR! code E401
npm ERR! 401 Unauthorized - PUT https://registry.npmjs.org/s6-final-steps - You must be logged in to publish
packages.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\Administrator\AppData\Roaming\npm-cache\_logs\2019-08-24T09_24_05_523Z-debug.log
```

出现了401，这里要登录，但是怎么登录呢，我明明在浏览器登录了啊？

先登录， 参考 Getting started - Setting up your npm user account - Testing you new account with npm login

即使用`npm login`，然后输入`username, password, email`

再次使用`npm publish`

结果

```
$ npm publish
npm notice
npm notice package: s6-final-steps@1.0.0
npm notice === Tarball Contents ===
npm notice 396B   package.json
npm notice 81B    README.md
npm notice 424B   webpack.config.js
npm notice 72.6kB dist/index.bundle.js
npm notice 335B   dist/index.html
npm notice 72.7kB dist/webpack-numbers.js
npm notice 128B   src/anotherEntry.js
npm notice 603B   src/index.js
npm notice 350B   src/ref.json
npm notice === Tarball Details ===
npm notice name:          s6-final-steps
npm notice version:       1.0.0
npm notice package size:  51.9 kB
npm notice unpacked size: 147.6 kB
npm notice shasum:        fd577519acb2030a2fd9e23e0f1625c394b5d149
npm notice integrity:     sha512-vWup9YlDEVs5i[...]Yl9HfT4eJr6kg==
npm notice total files:   9
npm notice
npm ERR! code E403
npm ERR! 403 Forbidden - PUT https://registry.npmjs.org/s6-final-steps - you must verify your email before publishing a new package: https://www.npmjs.com/email-edit

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\Administrator\AppData\Roaming\npm-cache\_logs\2019-08-24T09_42_16_445Z-debug.log
```

去验证邮箱，再试`npm publish`

```
$ npm publish
npm notice
npm notice package: s6-final-steps@1.0.0
npm notice === Tarball Contents ===
npm notice 396B   package.json
npm notice 81B    README.md
npm notice 424B   webpack.config.js
npm notice 72.6kB dist/index.bundle.js
npm notice 335B   dist/index.html
npm notice 72.7kB dist/webpack-numbers.js
npm notice 128B   src/anotherEntry.js
npm notice 603B   src/index.js
npm notice 350B   src/ref.json
npm notice === Tarball Details ===
npm notice name:          s6-final-steps
npm notice version:       1.0.0
npm notice package size:  51.9 kB
npm notice unpacked size: 147.6 kB
npm notice shasum:        fd577519acb2030a2fd9e23e0f1625c394b5d149
npm notice integrity:     sha512-vWup9YlDEVs5i[...]Yl9HfT4eJr6kg==
npm notice total files:   9
npm notice
+ s6-final-steps@1.0.0
```

成功了














