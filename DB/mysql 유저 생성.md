# mysql 유저 생성
## 유저생성
	use mysql;
	create user 'admin'@'%' identified by 'password';
	flush privileges;
## 유저권한
### rds
	GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD, PROCESS, REFERENCES, INDEX, ALTER, SHOW DATABASES, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION SLAVE, REPLICATION CLIENT, CREATE VIEW, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, CREATE USER, EVENT, TRIGGER ON *.* TO admin@localhost WITH GRANT OPTION;
	
### 일반
	[MySQL] 유저 권한 설정 - grant
	MySQL 의 grant 명령어로 사용자 권한 설정
	
	사용자 권한 설정
	
	mysql> grant all privileges on dbname.table to userid@host identified by 'password';
	모든 db 및 테이블에 접근권한 설정
	
	mysql> grant all privileges on *.* to userid@host identified by 'password';
	모든 db 및 테이블에 권한을 주고 로컬 및 리모트에서도 접속가능하도록 설정
	
	mysql> grant all privileges on *.* to userid@'%' identified by 'password';
	설정한 권한 적용 (반드시 해야 적용이 된다.)
	
	mysql> flush privileges;
	권한 삭제
	
	mysql> revoke all on dbname.table from userid@host
	권한 조회
	
	mysql> show grants for userid@host
	grant SELECT on pollide.* to admin@localhost identified by 'password' WITH GRANT OPTION;
	
	
	