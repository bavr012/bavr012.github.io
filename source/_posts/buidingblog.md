---
title: buiding blog
date: 2019-06-04 20:23:09
tags:
---

### 第一步

- 安装所需环境
1. 安装git
```cmd
[sudo] apt install git
```
2. 安装nodejs
```cmd
$
```
3. 安装hexo
```cmd
sudo npm install hexo-cli -g
```
- 下面最好是vscode，里面有自带的hexo环境[https://marketplace.visualstudio.com/items?itemName=fknop.vscode-npm](https://marketplace.visualstudio.com/items?itemName=fknop.vscode-npm)

### 第二步

- 建立本地blog
1. 在vscode使用快捷键`shift+ctrl+p`输入hexo init(在所需目录下)初始化项目
2. 输入`hexo server`启动服务浏览器访问[http://localhost:4000](http://localhost:4000)
3. 输入`hexo new`
4. 在blog/source/_posts目录下就可以看到一个新文件，就是刚建的文件，文件则为此次博客，所使用的语法为markdown语法（或html）

### 第三步
- github连接
1. 初次运行 Git 前的配置
```bash
git config --global user.name "yourname"
git config --global user.email "your_email@example.com"
git config --list
```
2. github设置添加ssh
```bash
ssh-keygen -t rsa -C "your_email@example.com"
后面一律回车，使用空密码
```
3. 密钥访问GitHub

    在C:\Users\94188\.ssh目录下找到id_rsa.pub文件，使用记事本打开复制公钥，进入GitHub个人主页设置的ssh and gpg key下(https://github.com/settings/keys),将公钥粘贴到key下保存。

4. 建立本地与GitHub连接

    建立新仓库(https://github.com/new)命名
`yourname.github.io`，进入仓库点击clone or download，点击use ssh，点击复制框中的代码如`git@github.com:yourname/yourname.github.io.git`,再进入刚建立本地博客的本地目录的_config.yml，把最后的代码填好，如下所示，然后保存。
```code
deploy:
  type: git
  repo: git@github.com:yourname/yourname.github.io.git
```

5. 终于到了最后一步了，哈哈哈，是不是有点开心呢。

    在bash下执行`hexo d`命令进行部署，就好啦。剩下的就是自己做博客了，在自己以前建的博客就可以做了，也可在vscode使用快捷键用`hexo new`命令建新文件。每次写完记得在快捷键后用`hexo clean`清除多余文件，再在bash下用`hexo d`部署。

- markdown语法以及安装过程中有错请参考[https://hexo.io/zh-cn/docs/]