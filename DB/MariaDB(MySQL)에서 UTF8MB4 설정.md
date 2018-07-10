# MariaDB(MySQL)에서 UTF8MB4 설정
1. 설정파일 수정

		[client]
		default-character-set = utf8mb4
		
		[mysql]
		default-character-set = utf8mb4
		
		[mysqld]
		character-set-server = utf8mb4
		collation-server = utf8mb4_unicode_ci
		
		character-set-client-handshake = FALSE // false 선택시, 클라이언트 언어설정 무시하고 서버(DB)의 캐릭터 설정으로 진행
		
2. 이모티콘 사용하는 기존 테이블 수정

		ALTER DATABASE database_name CHARACTER SET = utf8mb4 COLLATE = utf8mb4_unicode_ci;
		ALTER TABLE table_name CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;	
	
