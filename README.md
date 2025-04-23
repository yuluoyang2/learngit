# git自用使用教程
## 安装和配置
### Windows
* 访问`https://git-scm.com/download/win`,并按过程下载
* 配置Git，执行下面两条命令
  * `git config --global user.name "xuwc"`
  * `git config --global user.email "xuwencong2003@foxmail.com"`
* 配置代理，避免无法连接
  * `git config --global http.proxy http://127.0.0.1:7890`
  * `git config --global https.proxy http://127.0.0.1:7890`
### linux
* 安装命令 `sudo apt-get install git`
* 其余配置同上
## 创建版本库
1. 初始化一个Git仓库,通过`git init`命令把这个目录变成Git可以管理的仓库
2. 使用命令`git add <file>`，注意，可反复多次使用，添加多个文件
3. 使用命令`git commit -m <message>`，完成。
## 版本管理
* `git status`命令可以让我们时刻掌握仓库当前的状态
  * ```Changes not staged for commit``` 未添加到暂存区
  * ```Changes to be committed:``` 已添加到暂存区,但是未提交
  * ```Untracked files:``` 未被跟踪的文件
* `git diff <filename>`命令查看工作区和暂存区的区别
* `git log --graph --pretty=oneline`以图形化和单行显示的方式查看提交历史记录
* `git restore <file1> <file2> ...` 恢复工作目录中的文件
* `git restore --staged <file1> <file2> ...` 从暂存区移除文件
* `git reset --hard <commit_id>` 切换到指定版本
* `git reset --hard HEAD~n` 回退到前n个版本
* `git rm test.txt`   从工作区和暂存区中删除文件，并将删除操作记录到暂存区
## 远程仓库
* `git remote add origin https://github.com/yuluoyang2/learngit.git` 此命令的作用是把本地仓库和远程仓库建立连接
* `git remote -v` 查看远程仓库信息
* `git remote rm origin` 删除远程仓库
* `git push -u origin main` 建立本地分支与远程分支的关联, 简化后续的推送和拉取命令
* `git push origin main` 推送本地分支到远程仓库
* `git pull origin main` 拉取远程仓库到本地仓库
* `git clone https://github.com/yuluoyang2/learngit.git` 克隆远程仓库到本地仓库
## 分支管理
* `git branch` 查看分支
* `git branch <name>` 创建新分支
* `git branch -d <name>` 删除分支
* `git branch -D <name>` 强制删除分支
* `git branch --set-upstream-to=origin/branch-name branch-name` 设置本地 branch-name 分支跟踪远程仓库 origin 上的 branch-name 分支，后续在本地 branch-name 分支上执行 git pull 或 git push 等操作时，无需再显式指定远程仓库和远程分支名称
* `git checkout <name>` 切换分支
* `git checkout -b <name>` 创建并切换到新分支
* `git checkout -b branch-name origin/branch-name` 从远程仓库中创建分支
* `git switch <name>` 切换分支
* `git switch -c <name>` 创建并切换到新分支
* `git merge <name>` 合并分支到当前分支
* `git merge --no-ff -m "merge with no-ff" dev` 合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并
* `git stash` 保存工作现场
* `git stash list` 查看保存的工作现场
* `git stash apply` 恢复工作现场
* `git stash drop` 删除工作现场
* `git stash pop` 恢复并删除工作现场
* `git cherry-pick <commit_id>` 从其他分支中拣选提交，合并到当前分支
* `git rebase <branch>` 把分出去的分支合并到当前分支，并且合并为一条
## 使用github
1. 点"Fork"就在自己的账号下克隆了一个新仓库
2. 从自己的账号下clone
3. 如果你想修复一个bug，或者新增一个功能,可以往自己的仓库推送
4. 最后可以在GitHub上发起一个pull request
## 自定义git
* .gitignore的使用
* 使用可视化工具
## 未完待续





