---
ID: 553
post_title: >
  ms-sql 에서 1시간 전 데이터를
  추출하기
author: ""
post_date: 2010-01-21 09:05:02
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/01/21/ms-sql-%ec%97%90%ec%84%9c-1%ec%8b%9c%ea%b0%84-%ec%a0%84-%eb%8d%b0%ec%9d%b4%ed%84%b0%eb%a5%bc-%ec%b6%94%ec%b6%9c%ed%95%98%ea%b8%b0/'
published: true
---
<P>MS-SQL 쿼리를 짜는 거 생각보다 어렵다.<BR><BR>1시간 전 데이터를 추출하는 쿼리하면, 쉬울 거 같은데 SQL 문법을 잘 몰라서 찾아봤다.<BR><BR><FONT color=#0000ff>SELECT<BR>&nbsp; &nbsp; CASE<BR>&nbsp; &nbsp; &nbsp; &nbsp; WHEN EXISTS (<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; SELECT<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 1<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; FROM<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; TEST_TABLE<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; WHERE<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; uploadDate &gt; dateadd(hh, -1, GETDATE())<BR>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; )<BR>&nbsp; &nbsp; &nbsp;&nbsp; THEN 'true'<BR>&nbsp; &nbsp; &nbsp; &nbsp;ELSE 'false'<BR>&nbsp; &nbsp; END isExist</FONT><BR><BR>dateadd() 라는 함수를 이용하면 된다.<BR><BR>저렇게 하면 1시간 이내의 데이터만 체크할 수 있다.<BR><BR>hh 는 시간을 나타내는 단어로<BR><BR>yy, yyyy (년)<BR>qq, q (분기)<BR>mm, m (월)<BR>dy, y (일)<BR>dd, d (요일)<BR>wk, ww (주)<BR>hh (시)<BR>mi, n (분)<BR>ss, s (초)<BR>ms (밀리세컨)<BR><BR>이런 것들이 있다고 한다^^</P>