# iOS scrollview 완벽정리
##  scrollview 구성 시, autolayout을 사용하고 자 할 때,
scrollview  
	containerview(width나 height값을 스크롤뷰 사이즈랑 같게 또는 수치를 정해주어야 한다)

**이때, containerview에 동적으로 뷰를 addsubview 할 경우,**  
scrollview의 contentsize도 조정해야 할 뿐만 아니라,  
containerview의 너비 constarint값도 조정해 주어야 한다.

**addSubview를 동적으로 해주지 않을 경우(스토리보드에 넣어놨을 경우)**
scrollview의 contentsize 조정하지 않아도 됨

*이미 containerview에 view를 넣고, constraint를 잡아놓았을 경우,*
containerview의 자식의 크기만큼 커지게 되어있다. width의 우선순위 값을 500으로 잡아준다. 

## 스크롤뷰 안에 버튼있을 때 이벤트 처리
    mindDetailScrollView.canCancelContentTouches = false
    mindDetailScrollView.delaysContentTouches = false  

**이렇게 하면 스크롤뷰 안에 있는 뷰(스크롤뷰 등)에서 이벤트를 먹일 수 있다!**