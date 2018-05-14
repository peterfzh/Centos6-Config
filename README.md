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

auths  #权限配置管理
passwd #SVN的用户名和密码
svnserve.conf #SVN的配置信息

```
