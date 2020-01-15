# Git'configure
## 1.设置用户名和邮箱(--global 为全局参数,表明本地所有Git仓库都会使用这个配置)
 - git config --global user.name "sukai"
 - git config --global user.email "sycmyx@163.com"
## 2.Create SSH Key
 - ssh-keygen -t rsa -C "sycmyx@163.com"

## 3.添加密钥(SSH key)，并验证是否成功
 - 将上一步骤生成的密钥即.ssh/id_rsa.pub中内容全部复制。
 - 在github的 Settings-->SSH and GPG keys-->New SSH key,key中粘贴复制的内容(Title自定义).
 - ssh -T git@github.com  在git中输入验证
## 4.创建项目
 - Github创建仓库 Git01,本地创建同名文件夹Git01
## 5.初始化本地文件夹
 - git init
## 6.连接远程仓库
 - git remote add origin https://github.com/nmyzer/Git01.git
## 7.从远程仓库拉取文件,远程仓库没有则跳过
 - git push -u origin master
## 8.将本地文件夹push到远程仓库 
 - git stauts                  　   查看工作目录的状态
 - git add "filename"               将文件添加到暂存区  添加当前目录下所有 git add .
 - git commit -m "commitment"       提交更改,添加备注信息(此时将暂存区的信息提交到本地仓库)
 - git push origin master           将本地仓库的文件push到远程仓库(若 push 不成功，可加 -f 进行强推操作)
## 9.常见问题
 - Q2.git pull origin master 出现如下提示: 
 - fatal: refusing to merge unrelated histories
 - 解决: 如下操作即可解决
 - git pull origin master --allow-unrelated-histories

## 10.分支及版本控制
 - sanpshot 快照,简述 
 - 创建新分支 : "testing",不切换到新分支中: git branch testing
 - 查看各个分支所指向的对象: git log --oneline --decorate
 - -> 3e56cda (HEAD -> master, origin/master, testing) first commit
 - 分支切换   : git checkout testing
 - 再次查看各个分支所指向的对象: git log --oneline --decorate
 - -> 3e56cda (HEAD -> testing, origin/master, master) first commit
 - 比较的是工作目录中当前文件和暂存区域快照之间的差异,
 - 也就是修改之后还没有暂存起来的变化内容: git diff
 - 若要查看已暂存的将要添加到下次提交里的内容,可以用 git diff --cached 命令
