# lazy, view와 subviews

## 자식이 포함되었는 지 확인하는 방법
    if(!locSubview.isDescendantOfView(locView)){

## 특정 시점에 뷰를 로드하고 싶다면?
### lazy키워드를 사용하여 해당 시점에 변수를 호출하면 그때 생성됨!

	lazy var subview = CustomView(frame:)