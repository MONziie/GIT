### 向github提交代码
#### STEP1:
1.github提交代码受SSH限制，先要获取SSH授权
 windows git desktop安装后自带SSH，验证：git bash---输入ssh
2.生成密钥
在 Git Bash 中输入命令ssh-keygen -t rsa，使用 rsa 算法生成密钥。
id_rsa 是密钥，id_rsa.pub 是公钥，文件存储在默认目录下C:\用户\.ssh
3. 在github上添加SSH KEY
把 id_rsa.pub 中的内容复制到 GitHub 上的 Add SSH Keys 文本框中。


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
·






