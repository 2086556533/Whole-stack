# GIT分布式版本控制系统

1. 分布式版本控制系统与集中式版本控制系统的区别

   分布式版本控制系统根本没有 中央服务器 ，每个人的电脑上都是一个 完整的版本库 ，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。既然每个人电脑上都有一个完整的版本库，那多个人如何协作呢？比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。分布式版本控制系统的安全性要高很多，因为每个人电脑里都有 完整的版本库 ，某一个人的电脑坏掉了不要紧，随便从其他人那里复制一个就可以了。而集中式版本控制系统的中央服务器要是出了问题，所有人都没法干活了。

2. 用户设置

   安装完成后，还需要最后一步设置，在命令行输入：

   ```
   git config --global user.name "Nico"    
   git config --global user.email "allcky@qq.com"
   ```

   因为Git是分布式版本控制系统，所以每个机器都必须自报家门：你的名字和Email地址。

   注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

3. GIT重要概念

   * 工作区：可以理解成–项目文件夹”learngit“。Git把init过的文件夹叫做工作区，工作区中的内容，是我们当前编写代码，进行项目工作的地方。在这里，我们可以随意的添加、修改代码，或者添加其他的代码。
   * 暂存区：可以理解成–剪切板。前面我说过，提交给老板之前，我将当前文件，先复制到剪切板中，然后再粘贴到”.提交版”文件夹中。Git的暂存区就类似于剪切板，暂时的放置需要提交的文件。
   * 版本库：可以理解成–目标文件夹”.提交版”。”.提交版”保存了我所有的历史版本稿件。Git中的版本库也是一样的，而且更为强大，它不仅保存了每一个版本，还包含了变更的内容、时间、变更注释等等诸多信息。
   * 远程仓库：可以理解成–网盘。当多个人共同完成一个项目，比如我和几个人一起写稿子时；或者你在办公室写好稿子，回家想继续写。这是可以先把稿子保存到网盘上，再通知团队成员下载，或者回到家下载下来继续编辑。代码也一样，GitHub就是一个远程的仓库，我可以通过Git将版本库的内容全部放到GitHub上。

4. GIT工作流程

   1. 工作区  add    暂存区   commit   版本库    push    远程仓库     pull    版本库   reset    工作区

5. 常用命令

   1. git init 初始化仓库   将当前目录变成可以使用GIT管理的仓库
   2. git add .  将当前目录下新加入的文件加入仓库中的暂存区
   3. git commit -m "***"   将修改后的文件添加进远程仓库  -m后面输入的是对此次提交进行的说明如果没有输入-m  就会在之后弹出编辑页面  可以输入注释然后按ESC退出编辑模式，再次输入：wq！退出编辑器，执行成功后Git会告诉你，几个文件被改动，插入了多少行内容
   4. git status  查看当前目录内的文件状态
   5. git status -s  使用精简方式显示、
   6. git diff  查看内容差异 // 查看工作区和暂存区中的文件区别
   7. git log 查看历史纪录  记录按照先后顺序排列，第一列为最新提交版本，第二列次之，以此类推
   8. git log --oneline 精简模式查看历史记录
   9. git reset --hard HEAD^  回退到上一个版本
   10. git reset ************  回到未来   回到指定版本（**表示版本号）
   11. git reflog 用来记录每一条命令
   12. git checkout -- <file> 丢弃对输入文件的修改，从暂存区取回原来的文件 对删除同样有效
   13. git rm <file> 删除文件
   14. git checkout -b dev  创建dev分支并切换  相当于  git branch dev  git checkout dev
   15. git branch 查看当前分支
   16. 

