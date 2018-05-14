# Memcached是高性能的，分布式的内存对象缓存系统，用于在动态应用中减少数据库负载，提升访问速度。


开始安装memcache

### 1、查找Memcached

yum search memcached


### 2、安装memcache和php相关扩展

yum -y install –enablerepo=rpmforge memcached php-pecl-memcache
#如果提示没安装成功 yum update一下，然后再执行命令成功即把memcache服务端和php memcache扩展都安装好，会在/usr/lib64/php/modules/memcache.so

### 3、验证安装

memcached -h   #应该会输出一些帮助信息


### 4、设置开机启动

chkconfig memcached on


### 5、启动memcached

service memcached start


#到这里memcache服务端安装成功，测试安装是否成功

### 6、测试服务端是否安装成功
#如果提示lsof not found，使用yum install lsof即可

### 7、接下来加载php memcache扩展
找到php配置文件，一般使用yum默认安装在etc/目录下，如果没找到可以建立一个文件输出phpinfo搜索Configuration File可以查看到php.ini文件位置，开启memcache扩展extension=/usr/lib64/php/modules/memcache.so，重启php服务



service php-fpm restart
### 8、检测php扩展是否安装ok 
在输出phpinfo页面搜索memache，可查看到memcache扩展

### 9、新建mem.php，输入如下代码：

```php
<?php  
  $mem = new Memcache;  
  $mem->connect("127.0.0.1", 11211);  
  $mem->set('key', 'This is a test, Hello World!', 0, 60);  
  $val = $mem->get('key');  
  echo $val;  
?>  

```
