instalação zabbix 6.0

$ cat/etc/*release

$ free -h

$ df -h

$ timedatectl status

$ date

$ timedatectl set-timezone America/Sao_Paulo

$ timedatectl list-timezones

$ dnf -y install chrony

$ systemctl enable --now chronyd

$ systemctl status chrony

$ chronyc sources

$ service chronyd restart

$ systemctl status firewalld

$ firewall-cmd --permanent --add-service=http

$ firewall-cmd --reload

$ dnf install -y net-tools vim nano wget curl tcpdump

$ getenforce

$ cat /etc/selinux/config

$ dnf info mysql-server

$ dnf -y install mysql-server

$ systemctl enable --now mysqld

$ systemctl status mysqld


######################

CRIAR UMA SENHA PARA O USUARIO ROOT DO MYSQL

$ mysql

mysql> create database zabbix character set utf8m64 collate utf8m64_bin;

mysql> create user 'zabbix'@'localhost' identified by 'Zabbix6!user';

mysql> grant all privileges on zabbix.* to 'zabbix'@'localhost';

mysql> flush privileges;

mysql>exit

##########################

INSTALAÇÃO DO ZABBIX

$ rpm -Uvh http://repo.zabbix.cm/zabbix/6.0/rhel/8/x86_64/zabbix-realese-6.0-1.el8.noarch.rpm

$ dnf clean all

$ dnf -y install zabbix-server-mysql zabbix-sql-scripts zabbix-selinux-policy

$ cd /usr/share/doc/zabbix-sql-scripts/

$ cd mysql

$ zcat server.sql.gz | mysql -u zabbix -p zabbix

$ mysql -u zabbix -p zabbix

mysql> show tables;

mysql> quit;

$ vim /etc/zabbix/zabbix_server.conf

DBPassword=Zabbix!user

qw!

$ systemctl enable --now zabbix-server

$ systemctl status zabbix-server

$ tail -n50 /var/log/zabbix/zabbix_server.log

$ dnf -y install zabbix-web-mysql zabbix-nginx-conf

$ vim /etc/nginx/nginx.conf

server {
	#listen 80 default_server;
	#listen [::]:80 default-server;
	#server_name -;
}
wq!

$ vim /etc/nginx/conf.d/zabbix.conf

listen 80;
server_name _;

wq!

systemctl enable --now nginx php-fpm
















































