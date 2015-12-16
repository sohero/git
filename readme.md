 * 初始化git仓库，使用`git init`命令
 * 添加文件到Git仓库，分两步：

    - 第一步，使用命令`git add <file>`。注意可反复多次使用，添加多个文件；每次`commit`前，必须要将文件`add`进去。
    - 第二步，使用命令`git commit`，完成。

 * 查看仓库状态：`git status`
 * 查看修改内容：`git diff`
 * `HEAD`指向当前版本，上一版本是`HEAD^`,上上个版本是`HEAD^^`，以此类推; 回退版本命令：`git reset --hard commit_id`,或者`git reset --hard HEAD^`
 * 查看提交历史：`git log`,单行显示:`git log --pretty=oneline`
 * 查看命令历史：`git reflog`
 * 工作区和暂存区：`add`命令将工作区的修改提交到暂存区，`commit`将暂存区的修改提交到库。
 ![working directory](0.jpg)
 * 丢弃工作区的修改：`git checkout -- <file>`，丢弃暂存区的修改：`git reset HEAD <file>`
 * 删除文件：`git rm <file>`,然后`git commit`
 * 生成SSH Key的命令：`ssh-keygen -t rsa -C "email@email.com"`，git bash中。在用户主目录里生成两个文件：`id_rsa`是私钥，`id_rsa.pub`是公钥
 * 要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`;关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；
 * 克隆远程库到本地库：`git clone git@github.com:michaelliao/gitskills.git`；Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。
 * 查看分支：`git branch`;创建分支：`git branch <name>`;切换分支：`git checkout <name>`;创建+切换分支：`git checkout -b <name>`;合并某分支到当前分支：`git merge <name>`;删除分支：`git branch -d <name>`
 * 查看分支合并图：`git log --graph`
 * 暂存工作现场`git stash`;查看已存现场`git stash list`;恢复现场`git stash apply`;删除现场`git stash drop`;恢复并删除`git stash pop`
 * 如果要丢弃一个没有被合并过的分支，可以通过`git branch -D <name>`强行删除。
 * 查看远程库信息，使用git remote -v；
 * 本地新建的分支如果不推送到远程，对其他人就是不可见的；
 * 从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；
 * 在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；
 * 建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；
 * 从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。
 * 命令git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id；
 * git tag -a <tagname> -m "blablabla..."可以指定标签信息；
 * git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；
 * 命令git tag可以查看所有标签。`git show <tagname>`
 * 命令git push origin <tagname>可以推送一个本地标签；
 * 命令git push origin --tags可以推送全部未推送过的本地标签；
 * 命令git tag -d <tagname>可以删除一个本地标签；
 * 命令git push origin :refs/tags/<tagname>可以删除一个远程标签。
 * 忽略某些文件时，需要编写`.gitignore`；Github准备好的配置文件：https://github.com/github/gitignore
 * `.gitignore`文件本身要放到版本库里，并且可以对`.gitignore`做版本管理！
 * 配置文件：配置Git的时候，加上`--global`是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。
    - 每个仓库的Git配置文件都放在`.git/config`文件中
    - 当前用户的Git配置文件放在用户主目录下的一个隐藏文件`.gitconfig`中