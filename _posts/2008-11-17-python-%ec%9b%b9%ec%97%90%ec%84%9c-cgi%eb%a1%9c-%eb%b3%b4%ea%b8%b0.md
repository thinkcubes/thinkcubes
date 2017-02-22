---
ID: 249
post_title: python 웹에서 cgi로 보기
author: ""
post_date: 2008-11-17 04:39:51
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2008/11/17/python-%ec%9b%b9%ec%97%90%ec%84%9c-cgi%eb%a1%9c-%eb%b3%b4%ea%b8%b0/'
published: true
---
<SPAN style="COLOR: #008000">
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px; BACKGROUND-COLOR: #faffa9"><SPAN style="COLOR: #008000">#!/usr/bin/python</SPAN><BR><BR><SPAN style="COLOR: #0000ff">print</SPAN><SPAN style="COLOR: #808080"> "Content-type: text/html; charset=utf-8"</SPAN><BR><BR><SPAN style="COLOR: #0000ff">print</SPAN><SPAN style="COLOR: #808080"> "Pragma: no-cache\n"</SPAN><BR><BR><SPAN style="COLOR: #0000ff">print</SPAN><SPAN style="COLOR: #808080"> "Test, Python CGI"</SPAN></DIV></SPAN></TD><BR></TR>#!/usr/bin/python 은 파이썬 실행 파일이 있는 path를 설정하는 부분입니다.<BR><BR>html 로 표현하기 위해서는 이 소스의 결과물이 html 형식으로 표현된다는 것을 알려줘야 하는데,<BR><BR>이것이 바로 http 구조에서 말하는 헤더입니다.<BR><BR>http 프로토콜의 구조는 <STRONG>시작행-헤더-빈공백-본문</STRONG> 으로 이루어져 있습니다.<BR><BR>Content-type 과 charset을 적어주는 것은 http 헤더이고, no-cache는 캐시없이 로딩하겠다는 의미입니다.<BR><BR>그런데 가장 중요한 것은 \n (공백행)인데,<BR><BR>http 헤더와 본문 사이는 반드시 \n 이라는 공백행이 있어야 한다는군요.<BR><BR><BR>결국 python 가지고 놀아보자고 cgi 띄울 때 했던 실수 두가지.<BR><BR>1) py 확장자가 아니라 cgi 확장자를 이용할 것. (서버 관리자가 그렇게 설정해놨음..)<BR><BR>2) html 문서의 헤더와 본문 사이에 \n 공백행 문자를 삽입할 것.