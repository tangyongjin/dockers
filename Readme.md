# php7.3.33 docker

## 说明

php 配置
```
php.ini:      /usr/local/etc/php/php.ini
error_log:	 /tmp/php_errors.log
upload_max_filesize:	2M


```


## init.sh

```
#!/bin/bash
rm -r /var/run/apache2/apache2.pid
rm -fr /tmp/php_errors.log
touch  /tmp/php_errors.log
chmod 777  /tmp/php_errors.log
service apache2 restart &&   bash

```

## apache info

```
Server version: Apache/2.4.56 (Debian)
Server built:   2023-04-02T03:06:01
```
### webroot location
>  DocumentRoot /var/www/html


## issues
- 利用init.sh ,手工创建 php error log 
- 利用init.sh, rm -r /var/run/apache2/apache2.pid