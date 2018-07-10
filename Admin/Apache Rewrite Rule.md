# Apache Rewrite Rule
## 1. enable
`sudo a2enmod rewrite`

## 2. 설정 변경
- /etc/apache2/apache.conf 파일에 `AllowOverride All` 로 수정 

## 3. .htaccess 생성
**/var/www/html 에 생성**
 
	RewriteEngine on
	RewriteCond %{QUERY_STRING} ^v=(\w*)[&]*(.*)$
	RewriteRule ^watch$ http://beauteach.com/videoDetailPage?videoNo=27&v=%1 [R=301,NC,L]
	
	//일치하는 경로가 없을 경우 해당 규칙 저용
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule ^(.*)$ http://beauteach.com [R=301,L]
	
	//모든 경로에 대해 해당 규칙 적용
	RewriteRule (.*) http://beauteach.com [R=301,L]
	
###참고링크
- [정규식설명](http://www.nextree.co.kr/p4327/)
- [정규식시뮬레이션](https://regexr.com/)
- [설명1](https://simonecarletti.com/blog/2009/01/apache-rewriterule-and-query-string/)
- [설명2](https://pat.im/461)
- [설명3](https://pat.im/894)
- [설명3](http://soul0.tistory.com/139)
- [설명3](http://soul0.tistory.com/270)

### 참고
- [R=301,L] 여기서 띄워쓰기 하면 안댐
- 해당 조건 충족시 다음 조건을 무시 하려면 'L' 적용
- 캐쉬 없이 로딩은 구글 시크릿모드에서 개발자도구 열고 새로고침 오른쪽 클릭 또는 커맨드 쉬프트 r
- RewriteCond는 조건문, RewriteRule은 실행문
- parameter의 경우는 RewriteCond에서 파싱해주는 대로 RewriteRule에 적용됨
- 로그 사용 필요시, 
`RewriteLog /home/blog/rewrite_log_admin3.log
RewriteLogLevel 9`

### 예제
	RewriteEngine on
	RewriteCond %{QUERY_STRING} v=([^\?&"'>]+) [NC,OR]
	RewriteRule ^watch$ https://www.beauteach.com/videoDetailPage?v=%1&utm_source=youtube&utm_medium=typing&utm_campaign=%{HTTP_HOST}%{REQUEST_URI}/%1 [R=301,NC,L]
	
	RewriteCond %{HTTP_HOST} b2youtu.be [NC]
	RewriteCond %{REQUEST_URI} ^/([^\?&"'>]+) [NC]
	RewriteRule ^(.*)$  https://www.beauteach.com/videoDetailPage?v=%1&utm_source=youtube&utm_medium=typing&utm_campaign=%{HTTP_HOST}%{REQUEST_URI}/%1 [R=301,NC,L]
	
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule ^(.*)$ https://www.beauteach.com [R=301,L]
	
	RewriteRule (.*) https://www.beauteach.com [R=301,L]
