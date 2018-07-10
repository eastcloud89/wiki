# convertRect, convertPoint 총 정리
## fromView
self.view.convertRect(childView.frame, fromView: childView.superview.frame)  
=> self.view를 기준 점으로(0,0) | childView의 부모 입장(좌표체계)에서 본 childView의 절대 좌표   

Ex) let parentView = UIView(20,20,100,100)  
let childView = UIView(20,20,100,100)
let uncleView = UIView(10,10,100,100)

parentView.addSubview(childView)

let test = self.view.convertRect(childView.frame, fromView: parentView.frame)  
-> self.view를 기준점으로(0,0) parentView를 좌표로 계산하고, childView의 위치를 부모 좌표에서 계산해준다. <40,40,100,100>

let test = uncleView.convertRect(childView.frame, fromView: parentView.frame)  
-> self.view를 기준점으로(10,10) parentView를 좌표로 계산하고, childView의 위치를 부모 좌표에서 계산해준다. <40,40,100,100>

## toView
childView.superview.convertRect(childView.frame, toView: self.view)  
=> childView.superview를 기준 점으로(0,0) | childView의 좌표를 얻어내고 그것을 self.view의 좌표체계로 변환