
### 配置Apache+php+Mysql
* `一次性安装`

```Shell
[root@bogon /] yum -y install httpd php mysql mysql-server php-mysql httpd-manual mod_ssl mod_perl mod_auth_mysql php-mcrypt php-gd php-xml php-mbstring php-ldap php-pear php-xmlrpc mysql-connector-odbc mysql-devel libdbi-dbd-mysql
```

* `启动服务配置`
```Shell
chkconfig httpd on    #[设置apache为自启动]
chkconfig mysqld on   #[mysqld服务]
service httpd start   #[自启动 httpd 服务]
service mysqld start  #[自启动mysqld服务]
```

* `设置mysql数据库root帐号密码`
```Shell
mysqladmin -u root password '新密码' #[引号内填密码]
```
