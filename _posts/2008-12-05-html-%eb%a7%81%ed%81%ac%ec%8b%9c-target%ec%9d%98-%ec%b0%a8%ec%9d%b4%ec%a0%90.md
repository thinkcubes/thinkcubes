---
ID: 262
post_title: html 링크시 target의 차이점
author: ""
post_date: 2008-12-05 02:01:22
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2008/12/05/html-%eb%a7%81%ed%81%ac%ec%8b%9c-target%ec%9d%98-%ec%b0%a8%ec%9d%b4%ec%a0%90/'
published: true
---
a 태그로 html 문서를 호출할 때 새로운 창에 띄우는 방식은<BR><BR>target=_new 와 target=_blank 가 있다.<BR><BR>이 둘은 모두 현재창이 아닌 새로운 창에 해당 사이트를 띄우는 것이다.<BR><BR>_new는 현재창이 아닌 다른 창에 임의의 사이트가 로딩되어 있더라도 그 창에 사이트를 띄운다.<BR><BR>반면, _blank는 무조건 새로운 창(혹은 탭)에 해당 사이트를 띄우게 된다.<BR><BR>사소한 차이일지더라도, 신경써야할 점이다.<BR><BR>
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px">
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px; BACKGROUND-COLOR: #faffa9">
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px">&lt;<SPAN style="COLOR: #0000ff">a href</SPAN>="<SPAN style="COLOR: #999999">http://www.freeism.co.kr</SPAN>" <SPAN style="COLOR: #0000ff">target</SPAN>="<SPAN style="COLOR: #999999">_new</SPAN>"&gt;_new&lt;<SPAN style="COLOR: #0000ff">/a&gt;</SPAN><BR><BR>&lt;<SPAN style="COLOR: #0000ff">a href</SPAN>="<SPAN style="COLOR: #999999">http://www.freeism.co.kr</SPAN>" <SPAN style="COLOR: #0000ff">target</SPAN>="<SPAN style="COLOR: #999999">_blank</SPAN>"&gt;_blank&lt;<SPAN style="COLOR: #0000ff">/a</SPAN>&gt;</DIV></DIV></DIV>