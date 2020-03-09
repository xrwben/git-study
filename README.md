## 重学git

#### 一、init 创建

* 首先在远程仓库（GitHub、Gogs、gitlab等）创建一个仓库

* 然后在本地项目初始化一个本地仓库（当前创建.git目录）

  > `git init`

 ----

#### 二、add 将要提交的文件的信息添加到索引库中

> `git add .` 

 * 将所有修改添加到暂存区（删除的文件除外），如果带参数 -u 则表示把被修改过或已删除文件添加到索引库, -a 则是被修改过或已删除文件和所有未跟踪的文件信息添加到索引库

> `git add README.md` 

* 将README.md文件添加到暂存区

> `git add src/*.js`

* 将src下的所有js文件添加到暂存区 

---

#### 三、commit 将更改记录(提交)到存储库 如果您提交，然后立即发现错误，可以使用 git reset

> `git commit -m "xxx描述"`

---

#### 四、remote 命令管理一组跟踪的存储库(管理远程仓库)

> `git remote add origin http://github.com/xrwben/git-study.git`

---

#### push 命令用于将本地分支的更新，推送到远程主机

---

#### status、log、diff 查看更改

> `git status`

 * 显示工作目录和暂存区的状态, 此命令能看到那些修改被暂存到了, 哪些没有, 哪些文件没有被Git tracked到, 不显示已经commit到项目历史中去的信息

> `git log`

 * 查看日志详细信息

 > `git log`

 * 查看更改详情 +表示有内容添加 -表示有内容删除

 ---

#### reset 撤消之前的一些操作(如：git add, git commit等)

> `git reset --soft HEAD~1`

 * 重设reset索引、暂存区, 工作目录更改的代码保持不变

> `git reset --hard HEAD~3`

 * 重设reset索引、暂存和工作目录, 更改的代码重置消失到commit初始状态

 > `git reset --hard HEAD`

 * 相当于清空当前修改

 **HEAD 表示当前索引, HEAD^ 表示上一步, HEAD~1(同HEAD^)、HEAD~2、HEAD~3 表示撤销到到之前第几次提交** 

---