---
ID: 501
post_title: >
  SQL 쿼리 작성시 퍼포먼스를
  올리는 팁
author: ""
post_date: 2009-10-29 01:47:00
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/10/29/sql-%ec%bf%bc%eb%a6%ac-%ec%9e%91%ec%84%b1%ec%8b%9c-%ed%8d%bc%ed%8f%ac%eb%a8%bc%ec%8a%a4%eb%a5%bc-%ec%98%ac%eb%a6%ac%eb%8a%94-%ed%8c%81/'
published: true
---
<span lang="EN-US" style="FONT-SIZE: 9pt; FONT-FAMILY: 나눔고딕; mso-bidi-font-family: 'Times New Roman'; mso-ansi-language: EN-US; mso-fareast-language: KO; mso-bidi-language: AR-SA"><font color="#0000ff">

<div><font class="Apple-style-span" color="#000000">DB담당자에게서 몇 가지 배운 것이 있어서 기록해본다.</font></div>

<div><br></div>

<div><br></div>

SELECT</font><br><font color="#0000ff">&nbsp; &nbsp; CONVERT</font>(<font color="#0000ff">bigint</font>, createDate) <font color="#0000ff">AS</font> createDate<br><font color="#0000ff">FROM <br></font>&nbsp; &nbsp; MEMBER<br><font color="#0000ff">WHERE</font><br>&nbsp; &nbsp; memberId = <font color="#d41a01"><font color="#ff0000">'freeism'</font><br></font><font color="#8e8e8e">&nbsp; &nbsp; AND</font> memberSex =<font color="#ff0000"> 'male'</font></span>

<div><font class="Apple-style-span" color="#FF0000" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" color="#FF0000" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">위와 같은 예제 쿼리가 있다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">여기서 search할 때 where절에서 unique한 데이터를 먼저 찾는 것이 퍼포먼스에 좋다고 한다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">예를 들면, 남자인 사람은 여럿있다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">하지만 저런 아이디를 가지는 사람은 유일할 것 이다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">결국 A &amp;&amp; B 에서 A가 false이면 B는 점검하지 않는 이유이다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">역으로, OR 구문에서는 많은 데이터를 먼저 찾는 것이 좋다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">역시, A || B 에서 A가 true이면 B는 체크하지 않는다.</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>

<div><font class="Apple-style-span" face="나눔고딕">생각해보면, 당연한 것도.. 때론 전혀 생각조차 못하는 경우가 있다^^</font></div>

<div><font class="Apple-style-span" face="나눔고딕"><br></font></div>