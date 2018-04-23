#Git

* pwd:显示当前位置
* -r：包括文件夹
* ls:查看目前目录下所有文件
* ls -a:可查看所有文件
* ls --help：帮助
* clear：将当前位置移动到页面最顶端
* cd(相对路径)：跳转目录
* cd../ ：返回上一个目录
* touch 文件名(加上扩展名)：新建文件
* mkdir：创建文件夹       创建多个用空格
* cat(文件名)：查看文件内的内容
* rm(文件名)：删除文件   -r 可删除文件夹
* cp(文件名) (目录)：复制该文件到某个目录下
* cp(文件名)(文件名)：重名名
* cp -r：可复制文件夹
* cp css/* css1/：将css内的所有文件 复制到css1下
* mv：移动
* mv(文件夹或文件)：不需要-r参数
* -f：强制删除
* ~：代表用户主目录
* /：代表用户根目录
* cd d：跳转到d盘
* ./：代表当前目录

##Git 基本命令
* 在linux上安装git 在终端输入 sudo apt-get install git
* git clone 地址(https/ssh) 克隆网上的仓库到本地
* ctrl c:结束当前命令
* git add 文件名或.(所有的修改)：将你的修改让git记录
* git status：查看当前仓库的文件状态
* git commit -m''： 将你做的git add的修改做成一个版本  版本留言必须写 而且要真实
* git push：将本地的版本提交到远端
* 添加ssh：相当于电脑和git关联
* ssh-keygen：生成密钥  默认存储到用户主目录下
* cat ~/ .ssh/id_rsa.pub：复制密码到github网站 点击头像 settings SSH 添加4
* ssh作用：你如果使用的是ssh地址克隆的仓库 git push 的时候不用输入用户名和密码

#git生成

* git init：初始化本地文件夹为git仓库
* git add .
* git commit _m''
* git push：因为是首次提交 所以不清楚远端仓库地址 需要使用git remote add origin 地址 在本地添加一个远端仓库地址，然后使用 git push -u origin master 提交到远端的你添加的仓库
* git pull：将远端优先于本地的版本拉取到本地 让远端和本地同步 然后再次做本地的提交 按q退出
* 注意：如果远端的更新和本地的版本拉取到本地非要提交的时候，发生冲突 git pull会失败，需要在冲突的文件下手动解决冲突，手动解决冲突，相当于再次修改  所以需要git add 等下次再提交
* 历史回滚：git reset --hard HEAD^  git reset --hard[版本号]
* 本地仓库 回响到上一个版本或与版本号对应的版本 
* git push -f:强制将本地的版本推送到远端 覆盖远端版本
* git log --pretty=oneling：查看版本历史 每个版本在一行显示
* git reflog：查看git记录过的所有历史版本

# 分支操作
* git branch (分支名)：创建一个分支
* git branch：查看本地分支
* git branch -a：查看所有分支
* git branch -r：查看远端分支
* git checkout (分支名)：切换分支
* 主分支上有的内容，在新建分支的时候也会有同样的内容
* 在本地新建分支之后，远端没有分支，需要下面命令才能 推送到新建的分支上   git push -u origin dev
* git branch -d (分支名)：删除本地分支
---
##### 删除远端分支并提交
* git branch -d -r origin/(分支名)：删除远端分支
* git push origin ：(分支名)：提交
---------
* git checkout -b(分支名)：新建分支并切换

### 合并分支
* git merge (分支名)：当前所在分支合并其他分支 
* git merge之后，本地仓库已经合并分支的修改了，需要使用git push推送到远端
* git pull origin master：拉取主分支上的更新

* gh-pages：
* github用户名.github.io 仓库 直接访问仓库名就可以访问index.html  若想要其他仓库达到同样的效果，需要使用gh-pages分支
* 要展示的页面放到gh-pages分之下，然后提交 之后 访问地址 github用户名.github.io/别的仓库名

####ctrl+c：结束当前命令

##:linux系统何如安装 nodejs
* 1：安装cur1  sudo apt-get install curl
* 2:安装 nvm(node 版本管理) curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
* 3:使用nvm安装node
# npm
* npm init 初始化你的项目为npm的项目，使用npm管理自己的项目依赖 会生成一个package.json
* npm install jquery --save：使用npm安装非工具类依赖
* npm install webpack --save-dev：使用npm安装工具类依赖
* --save-dev 可以换成 -D
* npm i:会将package,json 里面记录的所有项目依赖全部安装，并且版本完全一致
* npm i -g (包名)：安装全局包 系统下任何地方都可以使用该包的命令
* 导出：modules.exports
* 导入：require()

#node

* node模块：核心模块 第三方模块  自定义模块
* 核心模块导入方式：require('模块名')
* 第三方模块导入方式：require('模块名')
* 自定义模块：需要自己导入导出
* git 仓库根目录下的 .gitignore 文件，是忽略上传文件，里面写的内容上传的时候不会上传到git