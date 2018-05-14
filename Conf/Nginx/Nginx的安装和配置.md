# Nginx的安装和配置
* ### `yum安装`
```shell
yum install nginx
```
* ### `rpm安装`
```shell
rpm -ivh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm  
2.yum -y install nginx  
3.yum -y php-fpm  
4.service php-fpm restart  
5.service nginx restart  
6.chkconfig php-fpm on  
7.chkconfig nginx on  

```

* ### '配置 /etc/nginx/conf.d/default.conf'
```bash
server {  
    listen       80;  
    server_name  localhost;  
    autoindex    on;  
    #charset koi8-r;  
    #access_log  /var/log/nginx/log/host.access.log  main;  
  
    location / {  
        root   /var/www/html;  
        index  index.html index.htm index.php;  
    }  
  
    location ~ \.php$ {  
        root           /var/www/html;  
        fastcgi_pass   127.0.0.1:9000;  
        fastcgi_index  index.php;  
        fastcgi_param  SCRIPT_FILENAME  /var/www/html$fastcgi_script_name;  
        include        fastcgi_params;  
    
}
```
