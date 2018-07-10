# mongodb 덤프 및 복구방법
## Dump

	테스트 서버에 접속
	ssh -i /Users/song/projects/fever/key/"falling.pem" ubuntu@52.78.93.22
	mongodump --out ~/dump/20161110 --host 52.79.138.56 -ugwhDev --db fallingSNS
	gwh!031


## 복구
덤프 폴더에 백업 파일을 넣는다!

	Ex)/home/ubuntu/dump
	
	contents.bson	contents.metadata.json

그리고 다음 명령어를 실행한다

	mongorestore --host 127.0.0.1 --port 27017 -ugwhDev --db fallingSNS ~/dump/20161110/fallingSNS/ --drop