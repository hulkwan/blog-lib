前言

    在大家使用github的过程中，一定会碰到这样一种情况
	就是每次要push 和pull时总是要输入github的账号和密码
	这样不仅浪费了大量的时间且降低了工作效率。在此背景下，
	本文在网上找了两种方法来避免这种状况，这些成果也是先人提出来的，在此只是做个总结。

###方法一 

1. 创建文件存储GIT用户名和密码

	在%HOME%目录中，一般为C:\users\Administrator，也可以是你自己创建的系统用户名目录，反正都在C:\users\中。文件名为.git-credentials,由于在Window中不允许直接创建以"."开头的文件，所以需要借助git bash进行，打开git bash客户端，进行%HOME%目录，然后用touch创建文件 .git-credentials, 用vim编辑此文件，输入内容格式：

	touch .git-credentials

	vim .git-credentials

	https://{username}:{password}@github.com
2. 添加Git Config 内容

	进入git bash终端， 输入如下命令：

	git config --global credential.helper store

	执行完后查看%HOME%目录下的.gitconfig文件，会多了一项：

	[credential]

    helper = store

	重新开启git bash会发现git push时不用再输入用户名和密码

###方法二
1. 添加环境变量

	在windows中添加一个HOME环境变量，变量名:HOME,变量值：%USERPROFILE%
2. 创建git用户名和密码存储文件

	进入%HOME%目录，新建一个名为"_netrc"的文件，文件中内容格式如下：

	machine {git account name}.github.com

	login your-usernmae

	password your-password

	重新打开git bash即可，无需再输入用户名和密码

###方法三
	
GNU Linux 用户可以使用 ‘cache’ 认证助手包来缓存认证信息，运行下面的命令来启用凭据缓存，启用后每次输入密码将保存一小时（3600秒）

```
git config --global  credential.helper  'cache --timeout 3600'
```

查看 ‘cache’ 认证助手的所有配置:

```
git helpcredential-cache
```