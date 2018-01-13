title: "在github page上用hexo搭建博客"
date: 2015-03-31 20:00:11
tags:
---

## github建立项目
需要在github上建立一个以github用户名开头的name.github.io(name为github用户名)的项目，然后开启github page,另外本机要部署好git的环境，以及设置git的私钥

## hexo安装部署
node.js的安装就不多说了，安装后，执行一下命令初始化项目
``` js
hexo init
```
### 相关插件
npm install hexo-generator-sitemap
npm install hexo-generator-feed
``` bash
Plugins:
- hexo-generator-feed
- hexo-generator-sitemap
```


## 出现的主要问题
### hexo部署项目失败
 在更新后，也修改了_config.yml配置，但执行hexo d -g 失败，提示“ERROR Deployer not found: github",需要执行以下操作
 ```bash
 npm install hexo-deployer-git --save
 ```
 同时修改_config.yml里的
 ```
 deploy:
  type: git      //原来配置的是github
 ```
然后执行hexo d -g，则成功了
