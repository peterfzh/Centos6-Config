# Centos6 - 各种配置文件管理

### 版本控制类

* `安装SVN的Shell`
```Shell
[root@bogon /]yum install -y svn
```

* `创建SVN的工作目录`
```Shell
[root@bogon /]svnadmin create /var/svn
```

* `配置SVN信息`
```Shell
配置文件在 /var/svn/conf
--------------------------------------------------------------------------------------------------------
auths           #权限配置管理
passwd          SVN的用户名和密码
svnserve.conf   #SVN的配置信息

auths 的配置
--------------------------------------------------------------------------------------------------------
[/]           项目路径如果全路径，则直接写"/",否则[/项目/项目01]
username=rw   读写的权限

passwd 的配置
--------------------------------------------------------------------------------------------------------
[users]
username=password

svnserve.conf 的配置
--------------------------------------------------------------------------------------------------------
[general]
anon-access = none
auth-access = write
password-db = passwd
authz-db = authz
```

### 配置Apache+php+Mysql
* `一次性安装`

```Shell
yum -y install httpd php mysql mysql-server php-mysql httpd-manual mod_ssl mod_perl mod_auth_mysql php-mcrypt php-gd php-xml php-mbstring php-ldap php-pear php-xmlrpc mysql-connector-odbc mysql-devel libdbi-dbd-mysql
```
