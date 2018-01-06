# EDRCDB
This demo-project established a B/S mode tested system in earthquake &amp; disasters resistance information management (EDRIMS) based of CBR theory in the use of programming languages, PHP, HTML and development tools, Dreamware, Sublim text 2. The tested system can be enabled to achieve case retrieve, case reuse, case revise and case retain and other functions via the universal browsers.

Develop Environment 

AppServ

AppServ 2.5.10
Apache 2.2.8
PHP 5.2.6
MySQL 5.0.51b
phpMyAdmin-2.10.3
Download
Sourceforge.net : http://prdownloads.sourceforge.net/appserv/appserv-win32-2.5.10.exe?download

MD5SUM : 279c0c39866fbecb8a3904969fd5d0f4

AppServ 2.6.0
Apache 2.2.8
PHP 6.0.0-dev
MySQL 6.0.4-alpha
phpMyAdmin-2.10.3
Download
Sourceforge.net : http://prdownloads.sourceforge.net/appserv/appserv-win32-2.6.0.exe?download

MD5SUM : e3a108c9b17f3572e53c07f52d236481


@@@@@System Configration@@@@@

重装AppServe
设置字符集：gbk_simplified chinese
enabled：InnoDB ： 勾选（Yes）

MySQL和phpMyAdmin
根用户：root
根密码：123

@@@@@CharSet Configration@@@@@

对应的根文件关键配置显示如下：
[client]

port=3306

[mysql]

default-character-set = gbk

@ 在命令行查看字符集设置

	SHOW variables like "char_%";

@在命令行查看插件或引擎

	
	show engines;
	

@查看版本信息

	select @@version;
		5.0.51b-community-nt-log

@@@@@消除简体中文乱码@@@@@

@所有HTML网页编码均为UTF-8
@所有php文件Header头都声明为UTF-8
	header("Content-Type:text/html;charset=utf-8");	
@所有MySQL字符设置都为gbk,仅MySQL系统默认为UTF-8 
@phpMyAdmin连接校对为gbk_ chinese_ci，整理为gbk_ chinese_ci
@所有php文件加上下面四句话
	mysql_query("SET NAMES UTF8");//设置中文字符集
	mysql_query('set character_set_client = utf8');
	mysql_query('set character_set_connection = GBK');
	mysql_query('set character_set_results = utf8');
@数据库引擎为InnoDB，表的引擎也是InnoDB

[client]

port=3306

[mysql]

default-character-set = gbk

# SERVER SECTION
# ----------------------------------------------------------------------
#
# The following options will be read by the MySQL Server. Make sure that
# you have installed the server correctly (see above) so it reads this 
# file.
#
[mysqld]

# The TCP/IP Port the MySQL Server will listen on
port=3306

#Path to installation directory. All paths are usually resolved relative to this.
basedir="A:\AppServ/MySQL"

#Path to the database root
datadir="A:\AppServ/MySQL/data/"

# The default character set that will be used when a new schema or table is
# created and no character set is defined
default-character-set = gbk
character-set-server = gbk
collation-server = gbk_chinese_ci
init_connect = 'SET collation_connection = gbk_chinese_ci'
init_connect = 'SET NAMES gbk'

# The default storage engine that will be used when create new tables when
#default-storage-engine=INNODB

@@@@@@phpMyAdmin  CharSet Configration@@@@@@

ALTER DATABASE `caoyong` DEFAULT CHARACTER SET gb2312 COLLATE gb2312_chinese_ci;
