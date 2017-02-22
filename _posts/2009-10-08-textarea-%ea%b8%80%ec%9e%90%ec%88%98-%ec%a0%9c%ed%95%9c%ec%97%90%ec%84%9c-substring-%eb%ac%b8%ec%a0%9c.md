---
ID: 494
post_title: >
  textarea 글자수 제한에서
  substring() 문제
author: ""
post_date: 2009-10-08 07:59:33
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/10/08/textarea-%ea%b8%80%ec%9e%90%ec%88%98-%ec%a0%9c%ed%95%9c%ec%97%90%ec%84%9c-substring-%eb%ac%b8%ec%a0%9c/'
published: true
---
textarea 에서 글자수를 제한할 일이 생겼다.<BR><BR>그런데 해당 내용이 submit() 할 때 체크하는 것이 아니라, 사용자의 입력에 따라 계속 체크되어야 한다.<BR><BR>그래서..<BR><BR><FONT color=#0000ff><FONT color=#ff7635>&lt;textarea id="comment" name="comment" <FONT color=#0000ff>onKeyUp="checkLength(this);"</FONT>&gt;&lt;/textarea&gt;</FONT><BR></FONT><BR>로 onKeyUp 이벤트를 잡아본다. 사용자가 입력할 때마다 체크하겠다는 얘기다.<BR><BR>그리고 자바스크립트로<BR><BR><FONT color=#0000ff>function checkLength(comment) {<BR>&nbsp; &nbsp; if (comment.value.length &gt; 100 ) {<BR>&nbsp; &nbsp; &nbsp; &nbsp; comment.value = comment.value.substring(0, 10);<BR>&nbsp; &nbsp; &nbsp; &nbsp; alert('10자 이내로 입력');<BR>&nbsp; &nbsp; &nbsp; &nbsp; return false;<BR>&nbsp; &nbsp; }<BR>}</FONT><BR><BR>10자까지 입력받고, 11자를 입력하면 마지막 글자가 삭제되면서 alert 창을 띄워주는 함수이다.<BR><BR>이렇게 만들었더니.. 영문과 숫자, 특수문자에서는 잘 동작한다.<BR><BR>그랬는데, 문제가 있다.<BR><BR>한글에서 11번째 글자를 입력하면 1~10번째 글자는 모두 지워지고, 11번째 글자가 남게된다.<BR><BR>내가 원하는 건 1~10번째 글자가 남고, 11번째 글자가 지워지는 것인데 말이다.<BR><BR>그러던 중 포커스 문제라는 것을 알게 되었다.<BR><BR>그래서 아래와 같이 포커스 노가다를 해주면 해결된다.<BR><BR><FONT color=#ff7635>function checkLength(comment) {<BR>&nbsp; &nbsp; if (comment.value.length &gt; 100 ) {<BR>&nbsp; &nbsp; &nbsp; &nbsp; <FONT color=#0000ff>comment.blur();</FONT><BR>&nbsp; &nbsp; &nbsp; &nbsp; comment.value = comment.value.substring(0, 10);<BR>&nbsp; &nbsp; &nbsp; &nbsp; alert('10자 이내로 입력');<BR>&nbsp; &nbsp; &nbsp; &nbsp; <FONT color=#0000ff>comment.focus();</FONT><BR>&nbsp; &nbsp; &nbsp; &nbsp; <FONT color=#ff7635>return false;</FONT><BR>&nbsp; &nbsp; }<BR>}</FONT><BR><BR>에휴.. 코드가 점점 더러워지는 듯한 느낌이 든다..ㅠ.ㅠ<BR><BR><BR>도움을 얻은 사이트 : <A href="http://ani2life.egloos.com/3676779">http://ani2life.egloos.com/3676779</A>