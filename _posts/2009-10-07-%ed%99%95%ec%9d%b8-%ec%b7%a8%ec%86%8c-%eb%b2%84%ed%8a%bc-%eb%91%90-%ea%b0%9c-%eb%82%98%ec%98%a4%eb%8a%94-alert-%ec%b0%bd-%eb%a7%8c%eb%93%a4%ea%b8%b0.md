---
ID: 491
post_title: >
  확인, 취소 버튼 두 개 나오는
  alert 창 만들기
author: ""
post_date: 2009-10-07 05:52:21
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/10/07/%ed%99%95%ec%9d%b8-%ec%b7%a8%ec%86%8c-%eb%b2%84%ed%8a%bc-%eb%91%90-%ea%b0%9c-%eb%82%98%ec%98%a4%eb%8a%94-alert-%ec%b0%bd-%eb%a7%8c%eb%93%a4%ea%b8%b0/'
published: true
---
<P>보통 alert 경고 메시지를 띄우면 "확인" 버튼 하나만 나온다.<BR><BR>그런데, "예", "아니오" 에 따라서 분기를 하고 싶다면 아래 명령어를 쓰면 된다.<BR><BR><FONT color=#0000ff>&lt;script language="javascript"&gt;<BR>&nbsp; &nbsp; if(confirm('진짜?')) {<BR>&nbsp; &nbsp; &nbsp; &nbsp; document.write("네")<BR>&nbsp; &nbsp; } else {<BR>&nbsp; &nbsp; &nbsp; &nbsp; document.write("아니오")<BR>&nbsp; &nbsp; }<BR>&lt;/script&gt;<BR></FONT><BR>confirm 창이라고 말하는 게 정확할 것 같으나..<BR><BR>무조건 띵~ 소리 내면서 뜨는 창은 alert 창이라는 고정관념이 있어서 (나도 그렇고..)<BR><BR>버튼 두 개 짜리 alert 창이라고 하는 게 낫겠다..^^</P>