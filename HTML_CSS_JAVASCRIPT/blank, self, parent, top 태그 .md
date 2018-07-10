# blank, self, parent, top 태그 

blank :  기존의 창은 그대로이고 새로운 인터넷 창하나를 더 띄워서 거기에 링크된 페이지를 연다. 
((ex))  <a href="aaa.html" target="_blank">링크</a> 


self : 기존에 떠있는 자기 창에다가 링크된 페이지를 연다. 
((ex))  <a href="aaa.html" target="_self">링크</a> 


parent : 기존창의 바로 전창에다가 링크된 페이지를 연다. 만약에 인터넷창을 3개 열어 두었다고 하면 1, 2, 3 이렇게 열었다고 하면 3번창에서 parent속성의 태그링크를 클릭하면 바로 전에 열었던 2번 창에 페이지가 표시된다. 
((ex))  <a href="aaa.html" target="_parent">링크</a> 


top : 현재 열려있는 최상위 인터넷창에다가 페이지를 연다. 
((ex))  <a href="aaa.html" target="_top">링크</a>