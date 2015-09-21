# 易启秀
易启秀是一款移动互联网营销的手机网页DIY制作工具，免费为中小微企业或团队提供业务场景应用展示，还可以查看网页的访问量、潜在客户报名量等。

## 标签
- 在线交互媒体设计平台
- 网页DIY制作工具
- H5页面移动场景应用制作
- H5创意创作平台

## 类似软件
- 易企秀 www.eqxiu.com 有电脑板，手机客户端（Android，iOS），网页版。
- 爆米兔 www.baomitu.com
- 兔展 www.rabbitpre.com
- vxplo www.vxplo.com
- 百幕秀 www.bmshow.com
- 云来 www.yunlai.cn
- 润云A秀 www.h-xiu.com 公众号： hoperuncloud

## 安装说明
- 把文件包上传到网站根目录。
- 然后导入数据库文件到数据库。

### 伪静态规则说明
- apache，用的是根目录那个.htaccess
- iis6，根目录的http.ini
- nginx，请将下列代码填写到自定义伪静态规则。填写的server{}里面
```
if (!-e $request_filename) {
	rewrite  ^(.*)$  /index.php?s=$1  last;
	break;
}
```
- iis7，把.htaccess里面的内容换成
```
<IfModule mod_rewrite.c>
  Options +FollowSymlinks
  RewriteEngine On
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^(.*)$ index.php/$1 [QSA,PT,L]
</IfModule>
```

### 数据库要修改2处
```
// Application\Common\Conf\systemConfig.php
$public_system_db_host = '127.0.0.1';	（这个不要修改）
$public_system_db_name = 'gldfsh';  //你的数据库名称
$public_system_db_user = 'root';   //你的数据库用户名
$public_system_db_pwd = '123456';  //你的数据库密码
// Conf\db.php
'DB_NAME' => 'ewesambo',	//你的数据库名称
'DB_USER' => 'root',	//你的数据库用户名
'DB_PWD' => 'root',   //你的数据库密码
```

### 默认后台账号密码都是admin
- 前台地址： http://域名/
- 后台地址： http://域名/admin.php

### 版权修改
- logo: /Public/css/images/logo.png
- 前台版权在\Public\eq\27\eqShow-2.7.1.js
- 还有\Application\Home\View\Index\index.html
- 后台版权的都在tpl/System这个文件夹
