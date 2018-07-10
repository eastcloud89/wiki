# visual vm 설치방법

1. sudo nano /usr/share/tomcat8/bin/setenv.sh
2. 입력

		export CATALINA_OPTS="$CATALINA_OPTS -Dcom.sun.management.jmxremote 
		-Dcom.sun.management.jmxremote.port=10005 -Dcom.sun.management.jmxremote.ssl=false 
		-Dcom.sun.management.jmxremote.authenticate=false 
		-Dcom.sun.management.jmxremote.local.only=false -Djava.rmi.server.hostname=localhost"

3. sudo netstat -lp | grep java
-> 10005는 위에서 입력해준 jmxremote port
-> 나머지 열린 포트를 찾아야된다! 아래에서 39290

4. 로컬에서 아래 코드 실행

		ssh -N -v -L 39290:127.0.0.1:39290 -L 10005:127.0.0.1:10005 ubuntu@도메인 -i pem파일 경로
		
5. visualVM 실행 후 jmx 추가 눌러주고 localhost:10005 입력	