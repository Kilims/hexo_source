---
title: React (0) node+npm+yarn安装，淘宝镜像，proxy设置
date: 2017-12-05 23:58:05
tags: [前端, react, node, npm, yarn]
---

在前端的世界里，node, npm, yarn可以说是撑起世界的世界树，而作为基石，学习需要三个过程：
1.了解 
2.会安装，会用
3.会设置

## node + npm 

Node.js
> 基于[Chrome V8](http://blog.csdn.net/xyqzki/article/details/45745507) 引擎的 JavaScript 运行环境
> [事件驱动](https://baike.baidu.com/item/%E4%BA%8B%E4%BB%B6%E9%A9%B1%E5%8A%A8/9597519?fr=aladdin)、[非阻塞式 I/O](http://cnodejs.org/topic/4f50dd9798766f5a610b808a) 的模型
> 附带[包管理器 npm](https://www.cnblogs.com/mangoniki/p/5381820.html)

### 安装 (windows)

进入[node官网下载页面](https://nodejs.org/en/download/)下载，当前提供的LTS(long time support)版本是 8.9.2


#### MSI installer安装（推荐)

正常情况下通过这个安装。

点击下载后，一步步执行即可，完成安装可在电脑cmd中输入 

``` bash
//检验安装
 $ node --version
 $ v8.9.2
 $ npm -v
 $ 4.0.5
```

进行检验。


#### ZIP文件下载

下载后配置电脑的PATH和NODE_HOME，即可。

这个方法适用于电脑被设置了限制的伙伴们，检验方法同上

### 配置npm淘宝镜像源

#### 为什么这么做？

因为正常来讲npm下载包都是从[国外仓库](https://registry.npmjs.org/)，速度贼慢。解决方式有两种：

1. 搭建代理服务器，俗称“科学上网工具”
2. 设置淘宝镜像源

前者复杂有空可以写写，目前介绍第二种方法。

#### 单纯改变registry

``` bash
//单纯改变源仓库
 $ npm config set registry http://registry.npm.taobao.org/
```

以后要发布包的时候，必须改回原来的仓库

命令为
``` bash
//改回默认仓库
 $ npm config set registry https://registry.npmjs.org/
```
#### alias一个cnpm(推荐)


``` bash
//alias cnpm
 $ npm install -g cnpm --registry=https://registry.npm.taobao.org
```

## yarn

### Why yarn ?

![yarn benefit](./yarn_benefit.png)

单单第一点就足以让我们转向yarn了

### 安装

``` bash
$ npm install -g yarn
```



``` bash
如果你alias了淘宝镜像源，那么往后有关npm的命令你都应该改为
$ cnpm install -g yarn
```

### 设置

``` bash
$ yarn config set registry https://registry.npm.taobao.org
```

常用的命令：

``` bash
// 查看下载源
$ yarn config get registry

// 初始化项目
$ yarn init -y

// 安装webpack
$ yarn add webpack

// 更新到最新的
$ yarn upgrade webpack

// 安装项目里的依赖
$ yarn install
```
