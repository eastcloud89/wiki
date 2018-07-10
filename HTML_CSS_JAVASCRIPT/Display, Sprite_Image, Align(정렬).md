#Day 1

##<a name="Display"></a>Display 속성
###block
한 줄 전체를 차지한다. **(width=100%)** 
margin, width, height 적용 가능 
*Ex)div*,*p* 태그
###inline
딱 끝나는 지점까지만 적용  
<del>margin, width, height 적용 불 가능</del>
*Ex)span*
###inline-block
**Block** 속성 처럼 한줄 전체를 차지 하지 않고,  
**margin, width, height 적용 가능**  
*Float*처럼 사용 가능

###Refer  
[링크1](http://www.beautifulcss.com/archives/1179)
[링크2](http://aboooks.tistory.com/85)
  
  
##<a name="Sprite-Image"></a>Sprite Image
여러개의 개별 이미지들을 하나로 합쳐 HTTP 요청횟수와 파일용량을 줄이고,
렌더링 성능을 향상시키는 방법

css의 background-image, background-position 기능 사용

	<!DOCTYPE html>
	<html lang="en">
	<head>
	<meta charset="UTF-8">
	<title>Example of Navigation Menu Based on Image Sprite</title>
	<style type="text/css">
	    ul.menu {
	        list-style-type: none;
	    }
	    ul.menu li {
	        padding: 5px;
	        font-size: 16px;
	        font-family: "Trebuchet MS", Arial, sans-serif;
	    }
	    ul.menu li a {
	        height: 50px;
	        line-height: 50px;
	        display: inline-block;
	        padding-left: 60px; /* To sift text off the background-image */
	        color: #3E789F;
	        background: url("../images/mySprite.png") no-repeat; /* As all link share the same background-image */
	    }
	    ul.menu li.firefox a {
	        background-position: 0 0;
	    }
	    ul.menu li.chrome a {
	        background-position: 0 -100px;
	    }
	    ul.menu li.ie a {
	        background-position: 0 -200px;
	    }
	    ul.menu li.safari a {
	        background-position: 0 -300px;
	    }
	    ul.menu li.opera a {
	        background-position: 0 -400px;
	    }
	    ul.menu li.firefox a:hover {
	        background-position: 0 -50px;
	    }
	    ul.menu li.chrome a:hover {
	        background-position: 0 -150px;
	    }
	    ul.menu li.ie a:hover {
	        background-position: 0 -250px;
	    }
	    ul.menu li.safari a:hover {
	        background-position: 0 -350px;
	    }
	    ul.menu li.opera a:hover {
	        background-position: 0 -450px;
	    }
	</style>
	</head>
	<body>
		<ul class="menu">
	        <li class="firefox"><a href="#">Firefox</a></li>
	        <li class="chrome"><a href="#">Chrome</a></li>
	        <li class="ie"><a href="#">Explorer</a></li>
	        <li class="opera"><a href="#">Opera</a></li>
	        <li class="safari"><a href="#">Safari</a></li>
	    </ul>
	</body>
	</html>  
	
![이미지스크린샷](http://www.tutorialrepublic.com/lib/images/sprite_navigator.jpg)
###Refer 

[링크](http://www.tutorialrepublic.com/css-tutorial/css-sprites.php)

## <a name="Align-Way"></a>가운데 정렬 4가지 방법

###Refer 
[링크](http://blog.naver.com/skydoor2014/220562850945)