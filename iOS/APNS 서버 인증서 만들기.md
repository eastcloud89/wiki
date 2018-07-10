# APNS 서버 인증서 만들기

## 1번 방법
준비물

* aps_pro.cer(푸시 인증서 웹사이트에서 다운)
* key.p12(aps_pro.cer의 key)

		openssl x509 -in aps_pro.cer -inform DER -out aps_pro.pem -outform PEM
		openssl pkcs12 -nocerts -out key.pem -in key.p12
		openssl pkcs12 -export -inkey key.pem -in aps_pro.pem -out aps_pro.p12

## 2번 방법
준비물

* cert.p12(aps_pro.cer의 인증서 내보내기 - 항목 개별 내보내기)
* key.p12(aps_pro.cer의 key 내보내기 - 항목 개별 내보내기)

		openssl pkcs12 -clcerts -nokeys -out cert.pem -in cert.p12
		openssl pkcs12 -nocerts -out key.pem -in key.p12
		openssl rsa -in key.pem -out key.unencrypted.pem
		cat cert.pem key.unencrypted.pem > apns.pem
		
		
## 참고링크
[링크](http://ddirty.tistory.com/50)	