# rds emoji 설정방법
- parameter group 에서 새로운 그룹 생성
	- 이때 type을 db parameter cluster group으로 하면 전체 instance 적용됨
- 세팅 방법

		character_set_client     = utf8mb4            
		character_set_connection = utf8mb4            
		character_set_database   = utf8mb4            
		character_set_filesystem = binary             
		character_set_results    = utf8mb4            
		character_set_server     = utf8mb4            
		character_set_system     = utf8               
		collation_connection     = utf8mb4_unicode_ci 
		collation_database       = utf8mb4_unicode_ci 
		collation_server         = utf8mb4_unicode_ci
		
- 인스턴스 이동 후 클러스터 그룹 변경	