第一步：建立git仓库 
cd到你的本地项目根目录下，执行git命令
git init

第二步：将项目的所有文件添加到仓库中
git add .
如果想添加某个特定的文件，只需把.换成特定的文件名即可

第三步：将add的文件commit到仓库
git commit -m "注释语句"

第四步：去github上创建自己的Repository，创建页面如下图所示： 
这里写图片描述
点击下面的Create repository，就会进入到类似下面的一个页面，拿到创建的仓库的https地址，红框标示的就是
这里写图片描述

第五步：重点来了，将本地的仓库关联到github上
git remote add origin https://github.com/ZhongAndGit/仓库名
后面的https链接地址换成你自己的仓库url地址，也就是上面红框中标出来的地址

第六步：上传github之前，要先pull一下，执行如下命令：
git pull origin master
敲回车后，会执行输出类似如下 

第七步，也就是最后一步，上传代码到github远程仓库
git push -u origin master
执行完后，如果没有异常，等待执行完就上传成功了，中间可能会让你输入Username和Password，你只要输入github的账号和密码就行了




出现问题
$ git push origin master
Warning: Permanently added the RSA host key for IP address '192.30.253.112' to the list of known hosts.
To git@github.com:Tuesdday/pythoncode.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:Tuesdday/pythoncode.git'
#提交代码时报错
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

解决问题两步
git pull --rebase origin master 
git push -u origin master
