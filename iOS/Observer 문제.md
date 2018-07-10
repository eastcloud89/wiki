# Observer 문제
## observer가 두 번씩 호출 될때?
### 1) observer 가 두 번 등록되어 있는지 확인
- viewDidLoad 에 observer가 들어가 있는지,
- viewwillappear에 들어가 있다면 viewdiddisappear에서 removeObserver를 해주는지 확인

참고) 유용한 익스텐션  

	extension NSNotificationCenter {
	    func setObserver(observer: AnyObject, selector: Selector, name: String?, object: AnyObject?) {
	        NSNotificationCenter.defaultCenter().removeObserver(observer, name: name, object: object)
	        NSNotificationCenter.defaultCenter().addObserver(observer, selector: selector, name: name, object: object)
	    }
	}
	
	NSNotificationCenter.defaultCenter().setObserver(self, selector: #selector(CenterViewController.handleUserDataLoaded(_:)), name: userManager.UserDataLoaded, object: nil)

### 2) post를 두 번 하는 지 확인!!

### 3) VC가 2번 초기화 되진 않았는지 확인!!

