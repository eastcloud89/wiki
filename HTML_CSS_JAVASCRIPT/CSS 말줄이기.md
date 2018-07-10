# CSS 말줄이기
## 다음줄로 넘기기

	word-wrap:break-word
	
**단어가 붙어있어 다음줄로 넘기지 못해 영역이 늘어나는 경우엔????!**  

	word-break:break-all
	
## 한줄 말줄이기(가로 길이가 지정되있어야 함)
**(너비값 반드시 고정되어야 하며 display가 너비값을 인식 할 수 있어야 함!)**  

	text-overflow: ellipsis; //글자가 지정한 너비를 넘어갈 경우 처리 방법
	white-space: nowrap; //요소안에서 공백은 어떤식으로 처리할 것인가 (nowrap -> 공백을 여러개 넣어도 1개로 처리, 줄바꿈이 있어도 하지않고 1줄로 표시
	word-wrap:break; //긴 텍스트를 강제로 끊어서 줄바꿈을 해주는 속성
	overflow: hidden;
	display: inline-block; 
	width: 200px;

	
## 여러줄 말줄이기(높이가 지정되어있어야 함)
**(높이값 반드시 고정되어야 하며 display가 너비값을 인식 할 수 있어야 함!)**

*-webkit-line-clamp 속성의 경우, 웹킷 엔진을 사용하지 않는 브라우져의 경우 문제가 될수 있으므로, line-height 속성과 height 속성을 이용하여 높이를 계산하여 넣어줍니다. (height = line-height \* 줄수)*

	overflow: hidden; 
	text-overflow: ellipsis; 
	display: -webkit-box;
	-webkit-line-clamp: 2; /* 라인수 */	
	-webkit-box-orient: vertical; 
	word-wrap:break-word;
	line-height: 10px;
	height: 20px;
    
    
## IE대응
    