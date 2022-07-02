## 为什么用Git

要把文档还原到编辑前的状态，大家都是怎么做的呢？

最简单的方法就是先备份编辑前的文档。使用这个方法时，我们通常都会在备份的文档名或目录名上添加编辑的日期。但是，每次编辑文档都要事先复制，这样非常麻烦，也很容易出错。

![备份文档的实例](https://backlog.com/git-tutorial/cn/img/post/intro/capture_intro1_1_1.png)

再加上，如果像上图那样毫无命名规则的话，就无法区分哪一个文档是最新的了。而且，如果是共享文件的话，应该加上编辑者的名字。还有，那些文档名字没有体现修改内容。

另外，如果两个人同时编辑某个共享文件，先进行编辑的人所做的修改内容会被覆盖，相信大家都有这样的经历。

![共享文件操作失败实例](https://backlog.com/git-tutorial/cn/img/post/intro/capture_intro1_1_2.png)

Git版本管理系统就是为了解决这些问题应运而生的。

### 使用Git进行版本管理

Git是一个分布式版本管理系统，是为了更好地管理Linux内核开发而创立的。

Git可以在任何时间点，把文档的状态作为更新记录保存起来。因此可以把编辑过的文档复原到以前的状态，也可以显示编辑前后的内容差异。

而且，编辑旧文件后，试图覆盖较新的文件的时候（即上传文件到服务器时），系统会发出警告，因此可以避免在无意中覆盖了他人的编辑内容。

![使用版本管理的共享文件操作实例](https://backlog.com/git-tutorial/cn/img/post/intro/capture_intro1_1_3.png)

> 用Git管理文件的话，更新的历史会保存在Git，所以不需要备份文件啦。非常方便吧！

## 安装Git

首先下载你的系统的Git客户端

[Git下载地址](https://git-scm.com/downloads)

这里以Windows举例, 下载之后, 双击安装即可

安装完成之后请执行 version命令，如果显示Git的版本就说明安装成功了。

```
git --version
```

## 一些开始的设定

安装Git之后，请输入您的用户名和电子邮件地址。该设置操作在安装Git后进行一次就够了。这些信息将作为提交者信息显示在更新历史中。

Git的设定被存放在用户本地目录的.gitconfig档案里。虽然可以直接编辑配置文件，但在这个教程里我们使用config命令。

桌面空白处右键打开 Git Bash, 执行命令

```
$ git config --global user.name "<用户名>"
$ git config --global user.email "<电子邮件>"
```

以下命令能让Git以彩色显示。

```
$ git config --global color.ui auto
```

您可以为Git命令设定别名。例如：把「checkout」缩略为「co」，然后就使用「co」来执行命令。

```
$ git config --global alias.co checkout
```

在windows使用命令行（Git Bash）的时候，含有非ASCII的文件名就会显示为 `\123\123\311`， 可以进行下面的设定：

```
$ git config --global core.quotepath off
```