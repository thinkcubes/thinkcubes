---
ID: 544
post_title: >
  javascript 에서 특정 문자열
  개수세기
author: ""
post_date: 2010-01-06 03:01:26
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/01/06/javascript-%ec%97%90%ec%84%9c-%ed%8a%b9%ec%a0%95-%eb%ac%b8%ec%9e%90%ec%97%b4-%ea%b0%9c%ec%88%98%ec%84%b8%ea%b8%b0/'
published: true
---
<P>정규표현식을 이용해서 match로 찾은 다음에 배열 사이즈를 구해보면 된다.<BR><BR><FONT color=#0000ff>&lt;script language='JavaScript'&gt;<BR>&nbsp;&nbsp; &nbsp;var str_value = "&lt;iframe src=test&gt;iframe&lt;/iframe&gt;\n&lt;iframe src=test2&gt;iframe&lt;/iframe&gt;";<BR>&nbsp; &nbsp; var re = new RegExp("iframe", "ig");<BR>&nbsp; &nbsp; var resultArray = str_value.match(re);<BR></FONT><FONT color=#0000ff><BR>&nbsp; &nbsp; alert(resultArray.length);<BR>&lt;/script&gt; <BR></FONT><BR>예전에 C언어에서 쌩코딩했던 것에 비하면, 정말 좋아졌다.</P>