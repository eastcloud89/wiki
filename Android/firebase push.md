# firebase push
## 상태에 따른 처리 
### 백그라운드 상태(클라이언트 앱이 관여하지 않음)
#### android
* 자동으로 시스템에 표시됨

#### ios
* 

### 포그라운드 상태
#### ios
* didReceiveRemoteNotification:이 처리

#### android
* Android에서는 onMessageReceived()가 처리
* 데이터 번들의 notification 키에 알림이 포함

## FIREBASE 알림작성기
* 메시지 내용 - 내용("body")

		"notification" : {
			"body" : "great match!",
			"title" : "Portugal vs. Denmark", 
			"icon" : "myicon"
		}

* 고급 옵션
	* 제목 - 제목(노티피케이션에 포함됨 "title")
	* 맞춤 데이터 - 키/값

			"data" : {
			  	"Nick" : "Mario",
			  	"Room" : "PortugalVSDenmark"
			}

## 푸시 아이콘 정하기
	 <application
	        android:allowBackup="true"
	        android:hardwareAccelerated="true"
	        android:icon="@mipmap/ic_launcher"
	        android:label="@string/app_name"
	        android:supportsRtl="true"
	        android:theme="@style/AppTheme.NoActionBar">

        <!-- [START fcm_default_icon] -->
        <!-- Set custom default icon. This is used when no icon is set for incoming notification messages.
             See README(https://goo.gl/l4GJaQ) for more. -->
        <meta-data
            android:name="com.google.firebase.messaging.default_notification_icon"
            android:resource="@mipmap/ic_launcher_small" />
        <!-- Set color used with incoming notification messages. This is used when no color is set for the incoming
             notification message. See README(https://goo.gl/6BKBk7) for more. -->
        <meta-data
            android:name="com.google.firebase.messaging.default_notification_color"
            android:resource="@color/colorPrimaryDark" />