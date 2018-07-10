# letsencrypt ssl적용법
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-apache
sudo certbot --apache -d b2youtube.com

000-default-le-ssl.conf 선택
Redirect 선택


## 테스트주소
https://www.ssllabs.com/ssltest/analyze.html?d=b2youtube.com


## 갱신방법
sudo certbot renew

## 예전버전 갱신 방법
./ letsencrypt-auto renew