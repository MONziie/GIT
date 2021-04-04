### 向github提交代码




安装git for windows之后需要进行一些设置
就输入下面这些代码

		git config --global user.name "这个双引号里填写的是你在 github 注册的账号"
		git config --global user.email "这个双引号里填写的是你在 github 注册的邮箱"

1.进入当前项目的目录
cd 路径

2.在本地进行初始化（建立暂存区）

		git init
<p>项目初始化后在那个项目文件夹里有个文件“.git”
这个文件存储的是当前项目的所有版本信息</p>

git提交代码的流程: 文件得先从工作区提交到暂存区，然后再上传到远程仓库

##### · 下面是提交过程的相关代码

'工作区 => 暂存区'

	git add 文件名  #提交一个文件
	git add *   #提交所有文件

'暂存区 => 远程仓库'

		git remote add origin https://github.com
		
（上面的地址填写的是你自己的暂存区地址，我用一个链接代替）

		git push -u origin master
<p>【注】提交过程中可能需要你提交用户名和密码
提交之后，写一段代码，备注一些信息</p>

		git commit -m "这是第一次提交的描述"
查看当前工作区的状态，则使用git status命令，看看有没有未提交的代码

		git status
若要从暂存区恢复文件到工作区，则使用git checkout 命令

		git checkout 文件名
查看已经提交到暂存区的历史版本，则使用git log命令

		git log
恢复文件到指定的某一个版本，则使用git reset --hard 命令

		git reset --hard 版本号
		
##### · 生成ssh密匙

		ssh-keygen -t rsa -C "你github里的邮箱名称"

window电脑里查找一个文件：
我的电脑 => 用户 => 用户名文件夹 => .ssh（隐藏文件夹）=> xxx.pub（存有密匙）

##### · github账户配置密匙

		暂存区 => 远程仓库
		git remote add origin "你自己的暂存区地址"
		git push -u origin master
【注】提交过程中可能需要你提交用户名和密码

##### · 从远程仓库，克隆项目到本地，使用git clone命令

		git clone
从远程仓库，（同步/更新）项目到本地

		git pull


链接：https://zhuanlan.zhihu.com/p/111078392
-----------------------------------------------------------------------------------------------------------------------
### 完整流程

第一种方法：
1、git add .
（将本地所有修改了的文件添加到暂存区）

2、git commit  -m " "
(引号里面是你的介绍，就是你的这次的提交是什么内容，便于你以后查看，这个是将索引的当前内容与描述更改的用户和日志消息一起存储在新的提交中)

3、git pull origin 远程分支名 这是下拉代码，将远程最新的代码先跟你本地的代码合并一下，如果确定远程没有更新，可以不用这个，最好是每次都执行以下，完成之后打开代码查看有没有冲突，并解决，如果有冲突解决完成以后再次执行1跟2的操作

4、git push origin master
（git push origin 本地分支名:refs/remotes/远程分支名） 将代码推至远程就可以了


第二种方法：

1、git stash （这是将本地代码回滚值至上一次提交的时候，就是没有你新改的代码）

2、git pull origin 
远程分支名（将远程的拉下来）

3、git stash pop
（将第一步回滚的代码释放出来，相等于将你修改的代码与下拉的代码合并）

然后解决冲突，你本地的代码将会是最新的代码

4、git add .

5、git commit  -m " "

6、git push origin master
（git push origin 本地分支名:refs/remotes/远程分支名）

这几步将代码推至了远程

最后再git pull origin 远程分支名 一下，确保远程的全部拉下来，有的你刚提交完有人又提交了，你再拉一下会避免你的不是最新的问题

。



链接：https://www.jianshu.com/p/9140b1e9ecc1







------------------------------------------------------------------------------------------------------------
#### STEP1:
<p> 1.github提交代码受SSH限制，先要获取SSH授权</p>
<p> windows git desktop安装后自带SSH，验证：git bash---输入ssh</p>
<p> 2.生成密钥</p>
<p> 在 Git Bash 中输入命令ssh-keygen -t rsa，使用 rsa 算法生成密钥。
id_rsa 是密钥，id_rsa.pub 是公钥，文件存储在默认目录下C:\用户\.ssh</p>
<p> 3. 在github上添加SSH KEY
把 id_rsa.pub 中的内容复制到 GitHub 上的 Add SSH Keys 文本框中。</p>


#### STEP2:
1.配置用户名和邮箱
git config --global user.name "MONziie"
git config --global user.email "XX@qq.com"



#### STEP3:
方法1.clone生成本地仓库
    git clone git@github.com/SiXiWanZi/Test.git

  命令运行后，本地仓库和远程仓库已关联

方法2.init本地文件夹
    git init [仓库名]
    git commit [仓库名]

· 添加远程仓库
通过以下指令为本地仓库添加一个远程仓库，至此实现本地仓库与远程仓库的关联。
    git remote add origin git@github.com:SiXiWanZi/Test.git
</p>






