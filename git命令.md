##git命令

 - 列表项

标签（空格分隔）： 基础工具

---

1. setting and config 
 

- git config 

- git help


2. get and create a project
- git init 
    对所建存储库的一个大概描述。初始化。
- git clone
   会创建一个新的目录。进入此目录，进行相关的操作 。
- git add 
  增添内容后，是文件从工作路径在执行提交命令之前保存至暂存状态。
- git status 
 修改文件的工作路径和缓存区的不同。显示那些文件被修改，那些在缓存区但未提交。
- git diff 
查看任意两个分支的不同之处。工作路径和缓存区，缓存区之间，缓存和提交，提交之间。
- git commit
提交修改的文件。git commit filename -m descriptionOfModify
- git rm
移除文件。git rm filename -cached:从缓存区删除，本地开发路径中依然存在。
3. branching and merging 
- git branch 
分支管理，可以列出，增加，删除，重命名一个分支。

- git merge

       合并分支
    
- git log

        列出当前所在仓库的提交记录

- git stash

      临时存储工作区未提交的文件，以保证开发路径在同一个区域不存在未提交的文件。




 ##如何将本地目录添加到远程仓库
 
 1. git init 初始化
 
        gitbash中进入本地目录-->`git init` (把当前项目git化)-->

 2. git add  将当前目录跟踪
        
        `git add .`(交给git经管)-->

 3. git commit 提交
 
     `git commit -m XXX`(写明提交信息)-->
 4. git remote 将本地库与git上那个项目相关联
 
        `git remote add origin git@github.com:yourname/yourrepository.git`-->

     这个过程可能出现的错误：`fatal: remote origin already exists.`
     
     解决方法：`git remote rm origin`后再执行 `git remote add ...`命令

5.  git push命令
    `git push -u origin master` 将本地库提交到github上。
    
        这个过程可能出现的错误：
            
            Warning: Permanently added the RSA host key for  IP address '192.30.252.131' to the list of known hosts. Permission denied (publickey).fatal: Could not read from remote repository. Please make sure you have the correct access rights and the repository exists.


      解决方法：

        在bash中:1.`ssh-keygen -t rsa -b 4096 -C "dengluming"`回车,按提示操作，会生成`The key fingerprint`及值得随机图片。2. `ssh-agent -s`3.`ssh-add ~/.ssh/id_rsa` (这一步会出现的错误：`Could not open a connection to your authentication agent`解决:`ssh-add ~/.ssh/id_rsa`)
       
       	
       	
       可能出现的问题2：
       
       	`error: failed to push some refs to 'git@github.com:wangruiFE/base_tools.git'`
       
      解决的方案：
      
      		`git pull --rebase origin master`
