# PhpBlog
PHP + VUE Study

项目搭建:

1、下载laravel-master,解压改为项目名。

2、CMD，进到项目根目录

3、替换composer镜像:composer config repo.packagist composer https://packagist.phpcomposer.com

4、安装相关依赖包：composer install

5、复制.env.example，重命名为.env

6、设定APP_KEY：php artisan key:generate

PHPStorm项目上传github:

1、在github上创建仓库后 复制仓库地址 比如 https://github.com/xinglsx/phpblog.git

2、在intelij中 VCS——Checkout from Version Contrl——Git中 粘贴仓库url地址

3、会从github仓库中拷贝一份项目，然后就可以在本地直接进行git操作。

4、然后需要把相关的GIT文件夹里面的内容拷贝到已有的项目中去。

5、打开项目，右击项目根目录->git->add会将所有可以提交的项目文件加入到git中。

6、然后提交：VCS->commint，提交之后可以选择同步推送

7、或者单独选择推送:VCS->git->push


navicat 连接MYSQL8.0报1251错误解决方法：

原因是mysql8 之前的版本中加密规则是mysql_native_password,而在mysql8之后,加密规则是caching_sha2_password, 解决问题方法有两种,一种是升级navicat驱动,一种是把mysql用户登录密码加密规则还原成mysql_native_password. 

命令：

ALTER USER 'root'@'localhost' IDENTIFIED BY 'password' PASSWORD EXPIRE NEVER; #修改加密规则 

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; #更新一下用户的密码 

FLUSH PRIVILEGES; #刷新权限 

