---
ID: 554
post_title: >
  쉘스크립트(리눅스)에서 하루
  전 날짜 표시하기
author: ""
post_date: 2010-01-21 10:09:00
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/01/21/%ec%89%98%ec%8a%a4%ed%81%ac%eb%a6%bd%ed%8a%b8%eb%a6%ac%eb%88%85%ec%8a%a4%ec%97%90%ec%84%9c-%ed%95%98%eb%a3%a8-%ec%a0%84-%eb%82%a0%ec%a7%9c-%ed%91%9c%ec%8b%9c%ed%95%98%ea%b8%b0/'
published: true
---
프로그래밍 언어에서는 day + 1 처럼 뭔가 연산식을 사용하게 되는데,<BR><BR>리눅스 서버에서는 통하지 않는다.<BR><BR><FONT color=#0000ff>/bin/date +1</FONT> 을 하게 되면 <FONT color=#9b18c1>1<BR><BR></FONT><FONT color=#0000ff>/bin/date +%Y.%m.%d+1</FONT> 을 하게 되면 <FONT color=#9b18c1>2010.01.21+1</FONT><BR><BR>로 출력된다.<BR><BR><FONT color=#0000ff>date --date '1 days ago'</FONT> 라고 하면 <FONT color=#9b18c1>2010.01.20</FONT> 으로 하루 전 날짜가 잘 표현된다.<BR><BR>뭔가 연산식이 아니라, 말로 표현된 명령어 옵션이라니.. 조금 당황;;<BR><BR>근데 1day ago 나 1days ago 나 같은 결과를 갖는다.<BR><BR>사람의 언어 문법을 몰라도 쓸 수 있도록 배려한 걸까^^