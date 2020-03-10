## 重学git

### 一、init 创建

* 首先在远程仓库（GitHub、Gogs、gitlab等）创建一个仓库

* 然后在本地项目初始化一个本地仓库（当前创建.git目录）

  > `git init`

----

### 二、add 将要提交的文件的信息添加到索引库中

> `git add .` 

 * 将所有修改添加到暂存区（删除的文件除外），如果带参数 -u 则表示把被修改过或已删除文件添加到索引库, -a 则是被修改过或已删除文件和所有未跟踪的文件信息添加到索引库

> `git add README.md` 

* 将README.md文件添加到暂存区

> `git add src/*.js`

* 将src下的所有js文件添加到暂存区 

---

### 三、commit 将更改记录(提交)到存储库 如果您提交，然后立即发现错误，可以使用 git reset

> `git commit -m "xxx描述"`

 * 将索引的当前内容与描述更改的用户和日志消息一起存储在新的提交中

> `git commit --amend`

 * 会使用与当前提交节点相同的父节点进行一次新的提交, 旧的提交将会被取消, 相当于重命名（i插入、:wq保存退出）

---

### 四、remote 命令管理一组跟踪的存储库(管理远程仓库)

> `git remote`

 * 要查看当前配置有哪些远程仓库, 会列出远程仓库名称, 例如 origin

> `git remote add origin http://github.com/xrwben/git-study.git`

---

### 五、push 命令用于将本地分支的更新, 推送到远程主机

> `git push -u origin master`

 * 将本地的master分支推送到origin主机的master分支, -u选项指定一个默认主机, 后面使用可以不加任何参数使用`git push`

> `git push --set-upstream origin master`

 * 同上, -u为省略形式, 表示如果当前分支与多个主机存在追踪关系, --set-upstream 选项会指定指定该主机为默认主机

> `git push --all origin`

 * 将多有的本地分支都推送到origin主机(origin即设置远程仓库的地址名称), 不管是否存在对应的远程分支都可以把分支推上去

> `git push --force origin`
 
 * 如果远程主机的版本比本地版本更新, 一定要推送, 可以使用 -–force 强推覆盖远程仓库 

> `git push origin --tags`

 * git push不会推送标签(tag)，除非使用 --tags 选项

---

### 六、pull 将远程存储库中的更改合并到当前分支中

> `git pull origin master`

 * 等同于先`git fetch`再`git merge FETCH_HEAD`, 如果不存在追踪信息, 则提示会跟push一样提示, 如果存在则可以省略表示`git pull`

> `git fetch`

 * 相当于是从远程获取最新版本到本地，不会自动合并

---

### status、log、diff 查看更改

> `git status`

 * 显示工作目录和暂存区的状态, 此命令能看到那些修改被暂存到了, 哪些没有, 哪些文件没有被Git tracked到, 不显示已经commit到项目历史中去的信息

> `git log`

 * 查看日志详细信息

 > `git log`

 * 查看更改详情 +表示有内容添加 -表示有内容删除

---

### reset 撤消之前的一些操作(如：git add, git commit等)

> `git reset --soft HEAD~1`

 * 重设reset索引、暂存区, 工作目录更改的代码保持不变

> `git reset --hard HEAD~3`

 * 重设reset索引、暂存和工作目录, 更改的代码重置消失到commit初始状态

 > `git reset --hard HEAD`

 * 相当于清空当前修改

 **HEAD 表示当前索引, HEAD^ 表示上一步, HEAD~1(同HEAD^)、HEAD~2、HEAD~3 表示撤销到到之前第几次提交** 

---

### clone 克隆

> `git clone xxxxx`

 * 在git clone的时候, 所有本地分支默认与远程主机的同名分支建立追踪关系

---

### checkout 切换、创建分支

> `git checkout -b 新建分支名`

 * 会在当前分支的基础（最近一次的commit）上新建一个分支

> `git checkout -m master`

 * 如果当前分支再test-branch-1且有本地没有暂存的修改, 则切换分支会报错提示, `-m` 标志将尝试三路合并, 把当前的未提交的本地修改合并过去, 这种情况极有可能产生冲突

> `git checkout .`

 * 把当前目录所有**修改的文件**从HEAD中签出并且把它恢复成未修改时的样子, 相当于**撤销所有修改**, 效果同`git reset --hard HEAD`

> `git checkout -- a.js`

 * 撤销特定文件的修改

---

### merge 将两个或两个以上的开发历史加入(合并)一起

> `git merge branch-1 branch-2`

 * 合并分支branch-1和branch-2到当前分支
