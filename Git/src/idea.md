# idea

1.安装与卸载

2.项目开发

3.基本设置

显示工具条

![image-20200420092349538](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420092349538.png)

鼠标悬浮提示（默认？）

显示方法分隔符

![image-20200420092616231](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420092616231.png)

忽略大小写

![image-20200420092743716](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420092743716.png)

主题设置

![image-20200420092906542](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420092906542.png)

颜色设置

背景色/文字颜色

![image-20200420093249458](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420093249458.png)

自动导包

![image-20200420093618442](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420093618442.png)

单行显示多个Tabs

![image-20200420093732721](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420093732721.png)

设置字体

![image-20200420093921537](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420093921537.png)

配置类文档注释信息和方法注释模版

比较代码

![image-20200420100438895](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420100438895.png)

折叠包名

![image-20200420101831822](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420101831822.png)

4.快捷键

删除单行代码

```
ctrl+y
```

快速补全分号

```
ctrl+shift+enter
```

快速检索

```
ctrl+shift+alt+n
```

```java
执行 alt +r
    提示补全 alt+/
    单行注释 ctrl+/
    多行注释 ctrl+shift+/
    乡下复制 ctrl+alt+down
    下移 alt+down
    向下开始新的一行 shift+enter
    向上开始新的一行 shift+ctrl+enter
    查看源码 ctrl+shift+t  ctrl+选中
    万能纠错 alt+enter
    退回前一个编辑页面 alt+left
    查看继承关系f4
    格式化代码 ctrl+shift+f
    提示方法参数类型 ctrl+alt+/
    选中数行，整体下移 tab+shift
    查看类结构 ctrl+o
    重构 alt+shift+r
    大小写转换 ctrl+shift+y
    生成构造 alt+shift+s
    收起方法 alt+shift+c
    dakai alt+shift+x
    打开在本地位置 ctrl+shift+x+
    生成try catch等结构 ctrl+shift+z
    
```

模板设置

```
main psvm
sout
soutp soutm soutv xxx.sout
fori
ifn
```

![image-20200420162844147](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420162844147.png)step over 进入下一步，如果当前行断点是一个方法，则不进入方法体内

![image-20200420162906097](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420162906097.png)step into进入下一步，如果当前行断点是一个方法，则进入方法体内

![image-20200420162920165](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420162920165.png)force step into进入下一步，如果当前行断点是一个方法，则进入方法体内

![image-20200420162932634](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420162932634.png)step out 跳出

![image-20200420162943341](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420162943341.png)

![image-20200420163004172](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420163004172.png)



# git

git对象

key：val组成的键值对（key是val对应的hash）键值对在git内部是一个blob类型

初始化

```
单个用户git config --global user.name""
git config --global user.email 
所有用户--system 
单文件 git config user.name
```

对象和区域

```
工作区 暂存区 版本库
```

```
git对象 树对象 提交对象
git文件的一次次版本
树对象 项目的一次次版本
```

git项目第一步

初始化仓库

```
git init
```

![image-20200420211140790](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200420211140790.png)

基础linux命令

clear 清屏

echo ‘test content’往控制台输出信息

ll：将当前目录下的子文件&子目录平铺在控制台

find 目录名：将对应目录下的子孙文件/目录平铺在控制台

find 目录名 -typef 将对应目录下的文件平铺在控制台

rm 文件名 删除文件

mv 源文件 重命名文件 重命名

cat 文件的url 查看对应文件的内容

vim 文件的url（英文模式下）

按i键 进入插入模式 进行文件的编辑

esc &： 进行命令的执行

wq 保存

set nu 设置行号

```
git add 添加的文件先到版本库生成git对象再到暂存区，申城git对象是增量的不是覆盖的
一个流程最少包含一个git对象树 提交对象 
git hash-object -w 文件名
git update-index
git commit
git write-tree
git commit-tree
```

工作目录下的文件：以跟踪 未跟踪 以跟踪三种状态已提交已修改未修改

git diff 更新未暂存

git diff --cached 暂存未提交

git crud操作

```
git init  初始化仓库
git status 查看状态
git add filename 添加到暂存区
git commit 提交到仓库，进入vim模式编辑注释
git diff 查看已修改为暂存的内容
git diff --staged 查看已暂存未提交的内容
git log 查看提交日志
git log --oneline 在一行查看提交日志
git commit -m 提交到仓库，添加注释
git commit -a -m  以跟踪的文件跳过暂存区直接提交到仓库
git rm 文件名 删除中作目录中对应的文件 再将修改添加到暂存区
git mv 原文件名 新文件名
git cat-file -t hash 类型
git cat-file -p hash 内容
```

git分支操作

```1
创建分支 git branch 分支名 分支一个活动的指针，在提交对象的前面 本质是一个指向提交对象的指针
head 是一个指针默认指向master
每次有新的提交，head带着当前指向的分支，一起向前移动
切换分支 git checkout 分支名
git checkout -b 分支名 
git branch 分支名 hash
合并分支 
删除分支 git branch -d 分支名 不能自己删自己
git branch -D 分支名 强制删除分支
显示分支列表 git branch
查看各分支历史版本 git log --oneline --decorate --graph --all
配别名操作 git config --global alias.lol "log --oneline --decorate --graph --all"
每次切换分支前，当前分支一定是干净的（已提交状态）在切换分支时，如果当前分支上有未暂存的修改（第一次） 或者有未提交的暂存（第一次）分支可以切换成功，但是会污染分支
切换分支动：head 暂存区 工作目录
git merge 合并分支 快进合并，不会产生冲突
典型合并 git merge iss53
解决冲突：找到冲突的文件，修改
git存储
git stash 将未完成的命令保存到一个栈上，存储也提交了，日志上看不到
git stash list 查看存储
git stash apply 
git stash drop 要删除的元素
git stash pop 应用储藏然后立即从栈上删除

```

git撤销 

```
git reflog head有变化，reflog就记录 git log 
文件纳入git管理
工作区 撤回工作目录的修改 git checkout -- filename git restore filename
暂存区git ls-files -s git cat-file -p hash 撤回暂存 git reset HEAD filename
版本库 撤回提交1.注释写错先git add./
git commit --amend 
HEAD~ 往回退一个head git reset --soft HEAD~只动head
git reset --mixed HEAD~ 动head 动暂存区
git reset --hard HEAD~ 动head 动暂存区 动工作目录--hard会销毁数据
```

| checkout commithash                    | git reset --hard commithash              |
| -------------------------------------- | ---------------------------------------- |
| 只动HEAD                               | 动HEAD而且带着分支一起走                 |
| 对工作目录是安全的                     | 强制覆盖工作目录                         |
| git checkout --filename相比于          |                                          |
| git reset --hard commithard --filename |                                          |
| 第一第二步都没做                       |                                          |
| 只会动了工作目录                       |                                          |
| git checkout commithash <file>         | 将会跳过第一步，更新暂存区，更新工作目录 |

数据恢复

```
git branch 新分支 
```

打tag

```
里程碑
给历史上的某一个提交打上标签 git tag v1.4.3/git tag v13.2 commithash
查看特定标签 git show 版本号
删除标签 git tag -d 标签名
检出分支 git checkout 分支号，同时创建分支
```

代码风格

```java
Eslint 
```

推之前请凭据

```
git config --global --unset user.name 删除配置
```

团队协作

```
1.一定要初始化一个空的仓库 github上操作
2.创建本地仓库，
	git remote 别名 仓库地址
	git init
	将源码复制
	修改用户名和邮箱
	git add ./
	git commit -m ""
3.推送本地仓库到远程仓库（清理windows凭据）
	git push 别名 分支
4.克隆远程仓库
	git clone 仓库地址（在本地生成。git文件，默认配了别名orgin）
5.邀请
6.成员做贡献
	。。。
	git push 别名 分支
7.更新修改
	git fetch 别名 （将修改同步到远程跟踪分支上）
	git merge 远程跟踪分支 合并分支
	
	
	
```

