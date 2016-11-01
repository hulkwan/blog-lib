### phpcs检查代码规范 ###

1. about phpcs

    > PHP_CodeSniffer is a set of two PHP scripts; the     main phpcs script that tokenizes PHP, JavaScript     and CSS files to detect violations of a defined     coding standard, and a second phpcbf script to     automatically correct coding standard violations.     PHP_CodeSniffer is an essential development tool     that ensures your code remains clean and consistent.    

2. about install
    
    *通常情况下通过pear安装，php7不支持pear，可以采用composer安装（下面主要针对composer安装)*

    安装步骤：

    * 1.使用安装包安装php第三方包管理器Composer
下载并运行Composer-Setup.exe. 该程序将自动安装最新版本的Composer 并自动设置执行程序目录到系统环境变量，安装完成后可在任何目录里启动命令行并使用Composer命令.

    * 2.安装 PHP_CodeSniffer、 PHP Mess Detector 和 PHP Coding Standards Fixer
在命令行里运行:
composer global require squizlabs/php_codesniffer;
composer global require phpmd/phpmd;
composer global require fabpot/php-cs-fixer;

    * 3.安装完成后，将phpcs.bat 、phpmd.bat和php-cs-fixer.bat 所在的目录 ../.composer/vendor/bin/ 加入到环境变量，然后在命令行里执行下phpcs、phpmd、php-cs-fixer两个命令，不出意外就成功啦
    
4. 配置文件加入到*Composer\vendor\squizlabs\php_codesniffer\CodeSniffer\Standards* 目录中
5. 关于配置
    
    - phpcs -i 查看当前配置
    - phpcs --config-set <option> <value>  设置配置
6. 使用 

    - phpcs -n xxxxx   （编码检查的是一个示例， 更多命令请参考 phpcs -h）
    
7. 修复代码

    - phpcs /path/to/code --suffix=.fixed（费覆盖式修复示例）
8. 参考文章

    - [如何在windows上安装phpmd，phpcs和php-cs-fixer命令](https://zhidao.baidu.com/question/1736004101260730827.html)
    - [使用PHP_CodeSniffer规范你的代码](http://bbs.lampbrother.net/read-htm-tid-152445.html)
    - [为你的 PHP_CODESNIFFER 构建自定义规则](http://xwsoul.com/posts/813)
    - [PHP代码规范与质量检查工具PHPCS,PHPMD的安装与配置](http://blog.csdn.net/cyaspnet/article/details/51773331)
    - [squizlabs/PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)