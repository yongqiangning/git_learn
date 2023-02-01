# 在本地应用git管理文件版本

## begin: git解决可以解决什么问题

git的功能非常强大, 在网上有非常多完整的介绍,这里笔者通过最基础的7个命令,介绍下对于非专业开发人员,git能为我们解决什么问题

### 1.工作党: 汇报PPT的版本追踪

在写重要的汇报PPT时, 我们经常仔细斟酌然后再交给leader审核, 最后再邮件发出, 这时候可能自己已经有了【初版v1】【初版v2】，leader一定会要求再突出下重点，再补充些细节， 这时候就有了【修改版v1】【修改版v2】，甚至会再出现【最终版v1】【最终版v2】。。。

### 2.学生党: 论文的版本追踪

在写毕业论文时无法避免的会有【初稿】、【二稿】、【三稿】、【四稿】、【最终稿】， 过分的还会有【最终稿修改版】、【最终稿修改版2】、【最终稿修改版2绝不再改版】、【最终稿修改稿2这次真的不改版】、【最终稿修改稿2这次真的不改版再改是狗】



本文的目标是通过本地git的版本管理功能避免这些杂乱的版本标题， 实现一个文件名记录所有版本, 避免了不舍得删除历史版本, 又看到很多文件心烦的问题

## 一、git版本管理功能概述

我们对于版本管理的需求以下三点能够解决大部分问题

1. 版本提交

   git有自己的版本管理规则， 共分为两步， 第一步，已经修改的内容先保存一下(相当于ctrl+s) 对应git命令为git add (即添加文件修改到缓存), 第二步,完成一个版本后提交版本(相当于文档另存为,并给文档取个不一样的名字) , 对应的git命令为git commit -m xxx , 这里xxx就是给版本的注释,相当于文件名了 

2. 查看所有历史版本列表

   查看历史版本, 一行命令就可以 git log --oneline

3. 切回指定的历史版本

   有时候需要参考历史版本的某段内容, 需要将文件恢复到指定版本, 也可以一行命令搞定,对应git命令为: git checkout xxx 这里xxx是指定的版本编号 

## 二、git管理本地文件实战举例 

   在[上篇文章]()中我们已经介绍了windows下安装git的全部过程， 这里直接从如何在本地初始化一个git仓库(Repository)开始介绍

### 1.新建本地仓库

   在需要追踪的文件所在文件夹右键-->点击Git Bash Here-->在窗口中输入git init  

   ![git_init](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_init.gif)

### 2. 配置git用户名和邮箱

配置git 用户名: git config --global user.name "username"

配置git邮箱: git config --global user.email "email"

![配置git用户名和邮箱](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/配置git用户名和邮箱.gif)



### 2. 新建文件

   在文件夹里新建需要追踪的文件并编辑内容

   ![新建文件](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/新建文件.gif)

### 3.加入缓存

在空白处右键-->选中Git Bash Here-->输入git add . -->按enter键 

这里add . 中点(.)的意思是all, 将所有修改点都add近git的缓存

![git_add](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_add.gif)

### 4.验证是否add成功

使用git status 命令,可以查看目前git追踪的文件夹的文件状态

![git_status](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_status.gif)



这里可以看到, 返回的结果中, 显示no commits yet 表示缓存中存在待提交(commit)的内容, 下一行的changes to be commited 详细说明了哪些文件的修改待提交

![git_status_add](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_status_add.png)

### 5.提交一个版本并写下注释

这里需要使用的命令是git commit -m xxxx , 其中commit 是提交的意思, -m是参数(mark的缩写,表示注释) 

该命令会把缓存中的内容提交称为一个版本, 并写有注释xxxx , 同时生成一个唯一的版本id(版本id后续会用到) 

![git_commit](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_commit.gif)  

#### 5.1 commit后查看git status 

![git_status_commit](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_status_commit.gif)

可以看到commit之后, 再查看git status 显示nothing to commit,working tree clean 表示目前缓存中是干净的, 没有待提交的文件

![image-20220306215943753](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_status_commit.png)

#### 5.2 修改文件内容并add+commit 得到有一个新的版本 

![git_add_commit](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_add_commit.gif)

### 6.查看历史所有的版本

使用git log --oneline 可以查看所有的历史版本 , 其中oneline是参数, 功能是让每个版本返回一行,且版本id长度为7位的简化版, 如果不见oneline参数,会返回更加详细的信息, 读者可以自己试下, 这里笔者认为oneline返回的信息已经足够了 

![git_log_oneline](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_log_oneline.gif)

可以看到, 目前的master版本是【初版v1】其id为51a301f , 最开始的版本【新建文件】的id是931d84a , 

这两个id后续切换版本的时候需要使用到

![git_log_oneline](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_log_oneline.png)

### 7.切换到历史指定版本

使用git checkout xxx 可以切换到指定的版本, 其中xxx是版本id

![git_checkout](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_checkout.gif)

### 8.将版本切换到最新版本master

git checkout master 会将版本切换到最新版本, 这里master是主版本的意思,切换到最新版本时不能指定id, 只能是master

![git_checkout_master](https://gitee.com/monkeyman/picture/raw/master/2.git_use_local/picture/git_checkout_master.gif)



## Ending

到这里, 利用git管理本地文件的命令已经介绍完了, 相信它能够给从未接触过git的同学一个初步的印象,以最少的命令解决最常用的功能。

以上涉及的7个命令, 总结如下表

| git命令                                 | 功能                                                         |
| --------------------------------------- | :----------------------------------------------------------- |
| git init                                | 在当前目录中初始化新的git仓库                                |
| git add .                               | 将新增的变化添加到缓存里                                     |
| git commit -m xxx                       | 将缓存区的内容提交到本地git仓库,并形成一个新的版本, <br/>其中-m参数是mark的缩写,  表示注释, -m后面的xxx是注释内容, <br/>版本的注释就是使用xxx表示, 版本注释很重要相当于版本的名字 |
| git log --oneline                       | 查看git的版本历史<br/>其中--oneline是表示返回简略信息, 并且每个版本一行<br/>如果不到--oneline参数会返回更详细的版本信息<br/>不过笔者建议日常使用加上该参数 |
| git checkout xxx<br/>gitcheckout master | 将版本切换到指定的版本,其中xxx是版本id<br/>版本id可以使用git log获取<br/>需要切回最新版本的时候使用git checkout master |
| git status                              | 查看当前git的状态, 会返回待提交或者未add的修改内容           |

