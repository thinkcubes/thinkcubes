---
ID: 498
post_title: >
  javascript 로 키보드 입력을
  체크하기
author: ""
post_date: 2009-10-09 08:10:53
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/10/09/javascript-%eb%a1%9c-%ed%82%a4%eb%b3%b4%eb%93%9c-%ec%9e%85%eb%a0%a5%ec%9d%84-%ec%b2%b4%ed%81%ac%ed%95%98%ea%b8%b0/'
published: true
---
<P><A href="http://www.freeism.co.kr/tc/615">textarea 글자수 제한에서 substring() 문제</A>의 연장선이다.<BR><BR>파이어폭스에서 알려진 버그로 한글 입력 시 onKeyDown, onKeyUp 이벤트를 인식하지 못하는 문제가 있다.<BR><BR>그런게 onKeyPress를 이용하니 IE에서 인식을 못하고, 파이어폭스에서는 인식을 한다.<BR><BR>그래서 분기를 시켜보았다.<BR><BR><FONT color=#0000ff>function isKeyPress( e ) {<BR>&nbsp; &nbsp; document.getElementById('test').innerHTML = document.getElementById('text').value.length;<BR>}<BR><BR>function setup(event) {<BR>&nbsp; &nbsp; var evtObject = document.frm.text;<BR>&nbsp;<BR>&nbsp; &nbsp; if(evtObject.addEventListener) { &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; // for firefox<BR>&nbsp; &nbsp; &nbsp; &nbsp; evtObject.addEventListener("keypress", isKeyPress, false); <BR>&nbsp; &nbsp; } else if(evtObject.attachEvent) { &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;// for ie<BR>&nbsp; &nbsp; &nbsp; &nbsp; evtObject.attachEvent("onkeyup", isKeyPress);<BR>&nbsp;&nbsp; &nbsp;}<BR>}<BR><BR>window.onload=setup;</FONT><BR><BR><FONT color=#ff7635>&lt;textarea id="text" name="text"&gt;&lt;/textarea&gt;<BR>&lt;div id="test"&gt;&lt;/div&gt;</FONT><BR><BR>키보드 입력을 받을 때마다 div 영역에 글자수를 프린트해주는 로직이다.<BR><BR>파이어폭스에서 사용하는 addEventListener를 확인해보고 onKeyPress 이벤트 핸들러를 생성하고,<BR><BR>IE에서는 addEventListener를 대체하는 attachEvent 라는 것을 이용해서 onKeyUp 이벤트 핸들러를 생성한다.<BR><BR>그래서 파폭이면 onKeyPress, IE면 onKeyUp 핸들러를 이용하게 된다.<BR><BR>단, 문제점!!<BR><BR>직접 테스트를 해보니, onKeyPress 핸들러는 한동작 늦게 반응한다.<BR><BR>즉, aa 라고 두 글자를 치면 갯수를 1개로 인식한다.<BR><BR><BR>도움받은 사이트 : <A href="http://blog.naver.com/metalorion?Redirect=Log&amp;logNo=50042192040">http://blog.naver.com/metalorion?Redirect=Log&amp;logNo=50042192040</A></P>