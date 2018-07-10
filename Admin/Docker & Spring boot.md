# Docker & Spring boot
## 개념정의
### Docker?  
* 컨테이너를 싣고 다니는 고래. 
* 여러개의 컨테이너(이미지)를 실행하고 이미지 저장과 배포하는 역할을 함

### 이미지
* 서비스 운영에 필요한 서버 프로그램, 소스 코드, 컴파일된 실행파일이 묶여져 있는 것
* Ex) Ubuntu & Spring / Mysql

### 컨테이너
* 이미지가 실행되고 있는 상태

### docker 설치하기
	sudo wget -qO- https://get.docker.com/ | sh
	
### Mysql 컨테이기 만들기
	
	docker run -d \
	--name demo-mysql \
	-e MYSQL_ROOT_PASSWORD=p4SSW0rd \
	-e MYSQL_DATABASE=demo \
	-e MYSQL_USER=dbuser \
	-e MYSQL_PASSWORD=dbp4ss \
	mysql:latest
	    
### sudo 없이 실행하기
	sudo su
	sudo usermod -aG docker ${user}
	sudo service docker restart

### java 설치
	sudo apt-get install default-jre
	sudo apt-get install default-jdk

	   