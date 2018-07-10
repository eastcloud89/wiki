# iOS 리젝사유 총집합

1. 유튜브 링크가 있는데 검색이 된다는 이유로 4+ -> 12+로 올리라고 리젝
	* 유튜브 iFrame으로 embed 시킴

			webView.loadHTMLString(
			"<html><head><title>Falling</title><style>body,html,iframe{margin:0;padding:0;}</style>
			</head><body><iframe frameborder=\"0\" width=\"\(ScreenSize.SCREEN_WIDTH)\" 
			height=\"\(ScreenSize.SCREEN_HEIGHT-64.0)\" 
			src=\"https://www.youtube.com/embed/\(videoId)?autoplay=1&showinfo=0&rel=0\" 
			frameborder=\"0\" allowfullscreen></iframe></body></html>", baseURL: nil)
			webView.scrollView.bounces = false
			webView.scrollView.showsHorizontalScrollIndicator = false
			webView.scrollView.showsVerticalScrollIndicator = false
            

2. 리뷰로 포인트 준다는 것이 형평성에 어긋난다고 리젝
	* 결국 해당 로직 삭제

3. 자동구독갱신 아이템이 있는데 관련규정, 개인정보보호, 서비스 약관을 찾을 수 없다고 해서 리젝
	* 항의함            