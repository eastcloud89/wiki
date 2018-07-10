# 안드로이드 SHA1??
## 디버깅용
1. ~/.android/ 로 이동한다
2. 명령어를 입력한다.
`keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android`. 

## 릴리즈용
`keytool -list -v -keystore your_keystore_name -alias your_alias_name`