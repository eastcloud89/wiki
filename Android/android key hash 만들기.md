# android key hash 만들기
	keytool -exportcert -alias androiddebugkey -keystore /Users/song/.android/debug.keystore -storepass android -keypass android | openssl sha1 -binary | openssl base64
