### 安装使用git

1. 下载安装，cmd输入git查看是否安装完成

2. 配置环境变量，V2.28.0安装完已配置

3. 配置git账号

   1. 点击git安装目录下的`git-bash.exe`进行配置
   2. 配置username： `git config --global user.name "XXX"`
   3. 配置email： `git config --global user.emali "xxx@xxx.com"`
   4. 查看配置： `git config --global --list`

4. 生成ssh

   1. 上面的git命令行下，继续输入： `ssh-keygen -t rsa`
   2. 然后回车继续
   3. 会在系统盘当前用户目录下生成.ssh文件夹（即： `C:\XXX\.ssh`），包含两个文件
   4. 将ssh文件夹中的 `id_rsa.pub` 内容（即公钥）添加到Github中（即 GitHub登录后中点击头像 -> settings -> SSH and GPG keys -> add SSH key）

5. 初始化git仓库

   1. 打开git命令行，cd到想要的目录下。（或直接新建文件夹后鼠标右键选择git bash）

   2. 输入 `git init` 即可，会显示 如下`Initialized empty Git repository in D:/tools/testGit/.git/` 

   3. 向仓库中添加文件：

      - `touch index.html` 新建文件

      - `git status` 查看文件目录和文件状态（modified、staged、committed）

      - `git add 'index.html'` 添加文件到暂存区，通过 `git status` 会发现文件名颜色变成绿色

      - `git add .` 目录下文件将都被add

      - `git commit -o xxx.xx -m '提交说明'`  注意： `-o` 后写提交的文件 `-m` 后写提交的说明

      - ESC + `:wq`  可以退出vim操作

      - 推送本地仓库内容到远程GitHub： `$ git remote add origin https://github.com/nangezi123/testGit.git` 此处网址为GitHub上new repository新建的仓库

      - 推送操作： `git push -u origin master`  

      - >>> 把本地库的内容推送到远程，使用 `git push`命令，实际上是把当前分支master推送到远程。 
        >>>
        >>> 由于远程库是空的，我们第一次推送`master`分支时，加上了 `–u`参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。推送成功后，可以立刻在github页面中看到远程库的内容已经和本地一模一样了， 
        >>>
        >>> 从现在起，只要本地作了提交，就可以通过如下命令：`git push origin master`
        >>>
        >>> 把本地master分支的最新修改推送到github上了，现在你就拥有了真正的分布式版本库了。

      

