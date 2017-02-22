---
ID: 260
post_title: >
  파이썬에서 한글 출력 문제
  해결
author: ""
post_date: 2008-12-03 08:51:44
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2008/12/03/%ed%8c%8c%ec%9d%b4%ec%8d%ac%ec%97%90%ec%84%9c-%ed%95%9c%ea%b8%80-%ec%b6%9c%eb%a0%a5-%eb%ac%b8%ec%a0%9c-%ed%95%b4%ea%b2%b0/'
published: true
---
파이썬을 CGI로 작동해서 웹페이지에 내용을 뿌릴 때는 한글을 사용하게 된다.<BR><BR>웹페이지를 한글로 쓸 수 없다면, 거의 무용지물이다..-_-<BR><BR>파이썬에서 print "한글"을 하면 정상적으로 한글이 출력되지만,<BR><BR>웹페이지로 넘기게 되면, 중간에 euc-kr이나 utf-8이나 이렇게 저렇게 인코딩되다 보면<BR><BR>결국 출력에는 한글이 깨져서 출력된다.<BR><BR>이때, 인코딩 방식을 아래와 같이 지정해주면 한글은 웹에서도 정상적으로 출력된다.<BR><BR><BR><img src="http://52.78.225.187/wp-content/uploads/1/5151826647.png" width="228" height="33" />