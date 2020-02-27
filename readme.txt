每个人都有完整版本库，可以随时在本机提交
如果两个人同时修改了A文件，把各自修改的A文件互相交换，然后合并，就可以了
一般也会有个中央服务器，用于交换各自的修改(如果某个文件正在被修改，svn会用锁控制，这样可以不需要合并功能。这一点比git好,git无法知道某个文件是否被其它人修改,所以git需要合并功能很强大)
分布式版本控制系统还有BitKeeper,Mercurial,Bazaar等，最简单最流行的是git
版本控制系统只能管理文本文件，像图片，视频这些二进制文件没法管理
git commit 可以一次提交很多文件
git init 初始化仓库
git add 添加文件
git status 掌握工作区状态
git diff 查看修改内容
git log 查看历史版本
回退版本 git reset --hard commit_id
查看以前命令 git reflog
HEAD 指针指向文件当前版本
git reset --hard HEAD^ 回退到上一版本
git log --pretty=oneline 展示git log 版本信息
工作区：就是工作目录
暂存区：版本库里的概念，版本中有暂存区，master分支
先是用git add 提交修改到暂存区
再是用git commit 把暂存区所有修改提交到master分支
git管理的是修改，所有修改必须git add到暂存区，然后git commit才能生效
git diff HEAD -- readme.txt 比较工作区和版本库的差别
discard:丢弃
git checkout -- readme.txt 把工作区最近一次的修改丢弃掉
git reset HEAD readme.txt 把暂存区的修改丢弃掉，与版本库当前版本一致
如果提交到版本库了，可使用版本回退
如果提交到远程库了，那就shit!!了
git rm 命令把文件删除掉，并把此修改提交到暂存区，如果想找回，则git reset HEAD test.txt,把暂存区修改清除掉，然后git checkout -- test.txt 则把原文件找了回来。
git checkout 实际上是把版本库的版本替换工作区的版本

关联一个远程库:git remote add origin git@github.com:GeorgeYuDong/learngit.git
第一次推送本地内容到远程库：git push -u origin master。以后推送不用-u参数
分布式版本系统好处之一就是不用考虑远程库存在，没有网络可以工作。有网络提交就完成了同步。
git clone命令，可克隆远程库到本地

