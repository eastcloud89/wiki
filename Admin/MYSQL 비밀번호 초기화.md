# MYSQL 비밀번호 초기화
	sudo /etc/init.d/mysql stop
	sudo killall -9 mysqld
	sudo mysqld_safe --skip-grant-tables --skip-networking &
	mysql -uroot
	FLUSH PRIVILEGES;
	use mysql;
	update user set password=PASSWORD("mynewpassword") where User='root';
	flush privileges;
	quit
	sudo /etc/init.d/mysql start