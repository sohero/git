 * 初始化git仓库，使用`git init`命令
 * 添加文件到Git仓库，分两步：

    - 第一步，使用命令`git add <file>`。注意可反复多次使用，添加多个文件；每次`commit`前，必须要将文件`add`进去。
    - 第二步，使用命令`git commit`，完成。

 * 查看仓库状态：`git status`
 * 查看修改内容：`git diff`
 * `HEAD`指向当前版本，上一版本是`HEAD^`,上上个版本是`HEAD^^`，以此类推; 回退版本命令：`git reset --hard commit_id`,或者`git reset --hard HEAD^`
 * 查看提交历史：`git log`,单行显示:`git log --pretty=oneline`
 * 查看命令历史：`git reflog`