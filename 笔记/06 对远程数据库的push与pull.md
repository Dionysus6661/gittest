## 从远程数据库pull

若是共享的远程数据库由多人同时作业，那么作业完毕后所有人都要把修改推送到远程数据库。然后，自己的本地数据库也需要更新其他人推送的变更内容。

## pull

进行拉取(Pull) 操作就可以把远程数据库的内容更新到本地数据库。

进行拉取(Pull) 操作，就是从远程数据库下载最近的变更日志，并覆盖自己本地数据库的相关内容。

![](https://backlog.com/git-tutorial/cn/img/post/intro/capture_intro3_3_1.png)

我们把在上一节中从“demo2”推送到远程数据库的内容拉取到数据库目录“demo”吧。

使用pull指令进行拉取操作。省略数据库名称的话，会在名为origin的数据库进行pull。

```
$ git pull <repository> <refspec>...
```

**用demo进行的操作**

请执行以下指令。

```
$ git pull origin master
Username: <用户名>
Password: <密码>
From https://gitee.com/liuwantao/demo.git
 * branch            master     -> FETCH_HEAD
Updating ac56e47..3da09c1
Fast-forward
 a.txt |    1 +
 1 files changed, 1 insertions(+), 0 deletions(-)
```

a.txt文档的内容已更新。

**用demo进行的操作**

我们使用log指令来确认历史记录是否已更新。

```
$ git log
commit 3da09c1134a41f2bee854a413916e4ebcae7318d
Author: lb <a@a.com>
Date:   Thu Jul 12 18:02:45 2012 +0900

    添加add的说明

commit ac56e474afbbe1eab9ebce5b3ab48ac4c73ad60e
Author: lb <a@a.com>
Date:   Thu Jul 12 18:00:21 2012 +0900

    first commit

```

太好了，我们可以看到在“demo2”的更新内容“添加add的说明”已列在这个数据库历史记录里了。

a.txt文件来确认一下内容吧。

```
学习Git
add 把变更录入到索引中
```

我们可以看到新增内容“add 把变更录入到索引中”。