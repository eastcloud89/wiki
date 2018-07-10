# Ubuntu Tomcat8 메모리 늘리는 방법
## 환경
* Ubuntu 16.04
* Tomcat 8
* EC2

## 톰캣 할당 메모리 확인 법
	sudo service tomcat8 status
	
	 └─12976 ........... -Djava.awt.headless=true -Xms512m -Xmx1024m
	 
## xms와 xmx
* xms 최소 힙 사이즈 영역 크기
* xmx 최대 힙 사이즈 영역 크기

## 메모리 늘리는 법
### 1번 방법 - 톰캣 HOME 경로에서 메모리 할당 크기 변경
		
	sudo su
	sudo echo 'export CATALINA_OPTS="-Xms512m -Xmx1024m"' > /usr/share/tomcat8/bin/setenv.sh

### 2번 방법	- 톰캣 실행 스크립트에서 메모리 할당 크기 변경
***<이걸로 해결됨>***
	
	sudo nano /etc/default/tomcat8
	
	=> JAVA_OPTS="-Djava.awt.headless=true -Xms512m -Xmx1024m -XX:+UseConcMarkSweepGC"
		 	
### 3번 방법 - 톰캣 서비스 실행 스크립트에서 메모리 할당 크기 변경		 	
 	sudo nano /etc/init.d/tomcat8
 	
 	=> JAVA_OPTS="-Djava.awt.headless=true -Xms512m -Xmx1024m"
 	
 	sudo systemctl daemon-reload
 	sudo service tomcat8 restart