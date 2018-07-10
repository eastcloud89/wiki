# 아마존 SSH 접근

	ssh -i [pem 파일 경로] ubuntu@[IP주소]
	
## 에러처리 
### bad permission
	chmod 400 (인증서 경로)
	
### public key required 
	인증서가 일치하지 않음