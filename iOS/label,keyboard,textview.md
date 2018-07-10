#Day 2
##라벨을 ...으로 하는 방법
	contentLabel.lineBreakMode = .ByTruncatingTail

##키보드 내리는 방법
	
	UIApplication.sharedApplication().sendAction("resignFirstResponder", to:nil, from:nil, forEvent:nil)

##Textview 에 패딩 주는 방법
Inset에 좌,우 값이 0이면 inset적용되지 않는다!  
원래 텍스트뷰에는 초기 인셋값이 정의되어 있으므로, 재 정의 시 유의하도록 한다.

`textView.textContainerInset = UIEdgeInsetsMake( 원하는 값, 0.001, 원하는 값, 0.001);`

