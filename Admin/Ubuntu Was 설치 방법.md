# Ubuntu Was 설치 방법
## JAVA 1.8, Tomcat 8.0, Maridb 10.0 설치

	sudo add-apt-repository ppa:webupd8team/java
	sudo apt-get update
	sudo apt-get install oracle-java8-installer
	sudo apt-get install oracle-java8-set-default
	sudo apt-get install apache2
	sudo apt-get install tomcat8
	sudo apt-get install mariadb-server
	
	sudo apt-get install mariadb-server-10.0 // 안해도됨
	sudo apt-get install mariadb-client-10.0 // 안해도됨

## root password 세팅하는 법(이 과정을 하면 밑에 비밀번호 설정하기 안해도됨)
sudo mysql_secure_installation

## root 비밀번호 설정하기 !!!!!!!!!!!SUDO 필수!!!!!!!!!!
	sudo mysql -uroot -p
	use mysql;
	update user set password=PASSWORD("ssss") where User='root';
	flush privileges;
## MariaDB 외부접근 허용하고 비밀번호 주기
	sudo mysql -uroot -p
	use mysql;
	create user 'dev'@'%' identified by 'password!';
	grant all privileges on *.* to 'dev'@'%';
	flush privileges;
	
	sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
	bind-address 0.0.0.0 으로 변경
	
	sudo service mysql restart

