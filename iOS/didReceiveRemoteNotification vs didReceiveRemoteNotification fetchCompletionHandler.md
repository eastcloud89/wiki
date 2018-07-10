# didReceiveRemoteNotification vs didReceiveRemoteNotification fetchCompletionHandler

## didReceiveRemoteNotification
백그라운드에 있을 때 또는 앱이 꺼져 있을 때 **푸시를 누르는 경우 실행 됨**
이때 상태는 *inactive*  
**앱이 꺼져있을 때는 이것만 반응한다!!**
## didReceiveRemoteNotification fetchCompletionHandler
백그라운드 또는 포어그라운드에 있을 때 **푸시를 받는 즉시 실행 됨**
(자체 UI 푸시를 처리할 때 또는 데이터를 갱신하기 위해 담당)

#교 비교
### 앱 실행이 아닐 경우(탭 누를 경우)
didReceiveRemoteNotification
### 포그라운드
didReceiveRemoteNotification fetchCompletionHandler
### 백그라운드
didReceiveRemoteNotification fetchCompletionHandler
### 백그라운드(탭 누를 경우)
didReceiveRemoteNotification fetchCompletionHandler
-> didReceiveRemoteNotification
