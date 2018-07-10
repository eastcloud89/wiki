# heroku 배포 방법
	heroku login
	heroku app:create 앱이름
	git init
	git add *
	git commit -am "commit 내용"
	heroku git:remote -a pollide (최초 한번)
	git push heroku master
	