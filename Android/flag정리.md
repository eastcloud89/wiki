# flag정리
## android:excludeFromRecents = "true"
홈키 눌렀을 때 테스크 목록에서 안뜨게 하기 위함
## android:launchMode="singleInstance"
새로운 task의 루트에 해당 액티비티 생성하고 다른 액티비티를 시작하도록 허용하지 않음
## FLAG\_ACTIVITY\_NEW\_TASK
새로운 task에 액티비티 생성 **(FLAG\_ACTIVITY\_MULTIPLE\_TASK 이 설정되있고, task의 affinity가 다를때**

[참고링크](http://theeye.pe.kr/archives/1298)