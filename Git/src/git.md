### git底层命令
    git对象
        git hash-object-w fileUrl:生成一个key value存到.git/objects
        
    tree对象
        往暂存区添加一条记录
    commit对象
        echo"注释"|git commit-tree treehash
    查询对象命令
        git cat-file -p hash:那对应对象的内容
        git cat-file -t hash:那对应对象的类型
    查看暂存区
        git ls-files -s 
  
 ### git高层命令
    安装
        git --version
    初始化配置
        git config --global user.name""
        git config --global user.email""
        git config --list
    初始化仓库
        git init
    C新增
        在工作目录中新增文件
        git status
        git add ./
        git commit -m "msg"
    U修改
        在工作目录中修改文件
        git status
        git add ./
        git commit -m "msg"
    D删除&重命名操作
        删除              重命名
        git rm 文件名      git mv fileName newfileName
        
        git status        git status
        git add ./
                git commit -m "msg"
    R查询
        git status    查询工作区文件状态(已托管:已暂存,已提交,已修改;未托管)
        日志
        git log 打印全部日志
        git log --oneline 在一行打印日志(一次提交一行)
        git log --oneline --decorate --graph --all 打印不同分支历史记录
        git reflog 查看提交信息,包括已经删除的分支的提交信息
        区别
        git diff 查看未暂存文件的修改
        git diff --staged 查看已暂存文件的修改
    分支
        本质是一个提交对象
        HEAD:指针,默认指向master分支;切换分支其实就是让HEAD指向不同的分支
        每次提交后,HEAD随着指向的分支一起向前移动
        查看
        git branch
        git log --oneline --decorate --graph --all 查看整个项目的分支图
        创建
        git branch 分支名 在当前提交对象上创建分支
        git branch name commithash 在指定提交对象上创建分支
        切换
        git checkout 分支名
        git checkout -b 分支名 创建并切换到新分支
        修改
        git branch -m oldName newName(本地分之重命名,还未推到远程)
        已经推到远程
            本地重命名 git branch -m oldName newName
            删除远程分支 git push --delete origin oldName
            上传新命名的本地分支 git push origin newName
            把修改后的本地分支和远程分支相关联 git branch --set-upstream-to origin/newName
            git branch --set-upstream-to origin/newName
        删除
        git branch -d 分支名 :删除已经合并的分支(删除之前要切换到主分支)
        git branch -D 分支名 :强制删除分支(未合并的分支;删除之前要切换到主分支)
        合并
        git merge 分支名(快进合并)
        典型合并:需要解决冲突
    git存储
        git stash list查看存储
        git stash创建存储(会提交,git log命令看不到提交,我们相当于未提交)
        进入分支,查看栈力是否有未完成的工作
        git stash apply 只运用栈顶的元素,不会删除
        git stash drop 栈顶名字,删除存储的元素
        git stash pop 应用存储并立刻从栈删除它
### git 后悔药 撤回操作
        工作区
        暂存区
        版本库
        撤回在工作区的修改(git已托管的文件)
        git checkout --fileName/git restore fileName
        撤回暂存
        git restore --staged fileName
        撤回提交
        版本库中不会撤回提交对象,只会重新提交一次.
        git commit --amend
        git reset命令

   sllvsicxjczjx

     啊撒健康

        啊哈哈 我学会了 pop 

