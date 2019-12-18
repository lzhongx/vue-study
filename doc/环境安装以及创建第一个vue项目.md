# 环境安装以及创建第一个vue项目



### 目录

- 环境安装
  - 安装node.js
  - 安装 vue 和 @vue/cli

- 使用 cli 创建项目

- 项目目录结构介绍

  

### 环境安装：

1. 安装node.js

    - 先去[官网](http://nodejs.cn/download/)下载node的安装包，下载链接：http://nodejs.cn/download/，进去之后选择适合自己电脑的版本进行下载。

      ![01-download-package](../../../raw/master/doc/images/01-download-package.png)

    - 下载到本地之后直接双击运行安装包，然后一直下一步直到安装完成。

    - 在安装目录创建 "node_global" 和 "node_cache" 文件夹

     ![node-installed-directory](../../../raw/master/doc/images/01-install-node1.png)

    - 在命令行中运行下面两条命令，将刚才创建的两个目录设置为 npm 安装依赖包的全局安装路径和缓存路径。

      `npm config set prefix "C:\Program Files\nodejs\node_global"   ` 

      `npm config set cache "C:\Program Files\nodejs\node_cache"`

      ![set-global-cache-directory](../../../raw/master/doc/images/01-install-node2.png)

      在这里运行 `node --version` 和 `npm --version`， 我们可以看到在安装 node 的时候，npm 也已经安装好了。

    - 设置环境变量：

      将刚才的安装目录添加到系统环境变量的 path 中，我这里是“C:\Program Files\nodejs”，同时添加的全局安装地址，我这里是 "C:\Program Files\nodejs\node_global"。

2. 安装vue 和 @vue/cli

     - 运行 `npm install vue -g` 和 `npm install @vue/cli -g` 命令安装 vue 和 @vue/cli。

      若出现下面报错信息，则需要使用管理员权限运行命令行

      ![install-vue](../../../raw/master/doc/images/01-install-vue1.png)

     - 安装完成之后，我们可以在上面设置的全局安装目录下找到刚才安装的依赖包





### 使用 cli 创建项目

1. 打开命令行运行 `vue vreate vue-study` ，其中 `vue-study` 是项目的名称

2. 等待一段时间之后，在出现的界面中选择 "default (babel, eslint)"

![01-create-project1](../../../raw/master/doc/images/01-create-project1.png)

3. 再次等待一段时间，出现下面的界面时就表示项目创建完成了

   ![01-create-project2](../../../raw/master/doc/images/01-create-project2.png)

4. 进入刚刚创建的项目目录内，运行 `npm run serve` 启动项目，在浏览器中通过 “http://localhost:8081” 地址访问。

   ![01-create-project3](../../../raw/master/doc/images/01-create-project3.png)

   运行效果：

   ![01-create-project4](../../../raw/master/doc/images/01-create-project4.png)



### 项目目录结构介绍



```
|--- node_modules                  // node 依赖包文件夹
|--- public
     |--- favicon.ioc
     |--- index.html               // 项目首页
|--- src                           // 源码文件加
     |--- assets                   // 项目资源文件夹
          |--- logo.png
     |---components                // 项目组件文件夹
          |--- HelloWorld.vue      // HelloWorld 组件
     |--- App.vue                  // Vue 的根组件
     |--- main.js                  // 项目入口
|--- .gitignore                    // git 提交时忽略忽略文件的配置
|--- babel.config.js
|--- package.json                  // 当前项目(模块)的描述信息
|--- README.md                     // readme 文档
```



#### node_modules

每一个 vue 项目都需要依赖其他的项目或模块，这些需要通过 npm 进行加载的依赖模块就存放在 node_modules 文件夹下。

#### public

这个目录主要存放一些不需要进行编译的静态资源文件

#### src

源代码存放的目录，主要的开发工作都在这个目录中完成。

- ##### assert

  资源文件夹，存放 logo 等图片

- ##### components

  组件文件夹，开发的组件都可以放在这个目录下

- ##### App.vue

  程序的根组件，最终会挂载到 index.html 文件的 `<div id="app"></div>` 上，即替换该 div 

- ##### main.js

  程序入口，在这个文件内初始化全局唯一的 Vue 对象和其他需要全局注册的组件或变量等

#### babel.config.js

兼容性配置文件，向下兼容，将 ES6及以上版本的代码转换为 ES5

#### package.json

本项目(模块)的描述信息

- name: 模块名称
- version: 版本号
- main: 入口文件
- scripts: 支持的脚本
- keywords: 关键字，有助于其他开发者使用 `npm search` 时发现这个项目
- description: 模块的描述
- author: 作者
- repository: 模块代码的 repo 信息，包括 type 和 URL，type 可以时 git 或 svn，URL则是模块的 repo 地址
- license: 开源许可
- dependencies: 生产环境依赖包的列表
- devDependencies: 开发、测试环境依赖包的列表
- engines: 声明项目需要的 node 或 npm 版本范围

