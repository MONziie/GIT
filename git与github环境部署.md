### 1.创建SSH Key
Git和github之间是通过SSH加密的，因此需要执行下面的操作：

a、在本地主目录查找，是否有.ssh目录，如果有，打开该目录，一般会有这两个文件：id_rsa(私钥)和id_rsa.pub（公钥），
如果有的话，直接跳过，如果没有的话，打开命令行，输入如下命令：
ssh-keygen  -t rsa –C “youselfemail@email.com”（你自己的邮箱地址，推荐和注册github的邮箱保持一致）,

PS：如果本地还未生成SSK key，可以通过该命令生成： ssh-keygen -t rsa -C "youremailaddress@mail.com" 


b、登录github，右上角：设置→settings-SSH and GPR keys→New SSH key，然后输入你的标题，输入上面的公钥，然后点击保存。




### 2、创建仓库
点击右上角，添加→New repository，按照下图所示创建仓库：
然后进入创建的仓库，点击Clone or download，找到你的仓库地址：
然后通过命令:git remote add origin https://github.com/zwg481026/APITest.git，将本地仓库和github仓库连接就好了。



原文链接：https://www.cnblogs.com/imyalost/p/8777684.html
