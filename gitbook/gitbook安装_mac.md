有人推荐学英语的gitbook很棒， 于是搜了下如何在mac安装gitbook， 主要参考这篇文章[GitBook本地服务搭建](https://xiaotou745.gitbooks.io/gitbook/content/Install.html) 

```bash
sudo npm install gitbook-cli -g --registry=https://registry.npm.taobao.org
```

刚开始没有添加sudo， 报错， 所示某一个文件夹没有权限

--registry=https://registry.npm.taobao.org 参数是我觉得网络不稳定， 指定的淘宝源 

```bash
$ gitbook -h
```

查看是否安装完成

```bash
$ cd /Users/mac/jupyter/书籍/English-level-up-tips-master 
```

将工作目录切换到下载的别人的书的文件夹



```bash
$ gitbook serve
```

开启gitbook 服务

```bash
http://localhost:4000/
```

在浏览器中输入该网址， 就能够看到和网页版一模一样的gitbook了

