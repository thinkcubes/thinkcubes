---
ID: 570
post_title: 'java.lang.SecurityException : &#8220;org.hamcrest.Matchers&#8221;'
author: ""
post_date: 2010-03-18 02:24:50
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2010/03/18/javalangsecurityexception-orghamcrestmatchers/
published: true
---
<P>그동안 mockito만 사용하다가 harmcrest-library를 사용하게 되었다.<BR><BR>AssertThat(A, is(B)); 코드를 사용하려면 위 lib가 필요하더라.<BR><BR>그런데 아래와 같은 exception 발생했다.<BR><BR>[code]java.lang.SecurityException: <BR>class "org.hamcrest.Matchers"'s signer information does not match signer<BR>information of other classes in the same package<BR>&nbsp;at java.lang.ClassLoader.checkCerts(ClassLoader.java:769)<BR>&nbsp;at java.lang.ClassLoader.preDefineClass(ClassLoader.java:484)<BR>[/code]<BR>구글링 결과 두 개의 동일한 lib가 존재해서 충돌나는 것이라고 한다.<BR><BR><A href="http://emptylist.wordpress.com/2010/02/14/org-hamcrest-matchers-and-eclipse-java-lang-securityexception/" target=_blank>http://emptylist.wordpress.com/2010/02/14/org-hamcrest-matchers-and-eclipse-java-lang-securityexception/</A><BR><BR>알아봤더니 mockito에서 harmcrest core lib를 포함하고 있다. (mockito-all 버전)<BR><BR>그래서 mockito-core 버전을 받아서 쓰기로 했다.<BR><BR>추가 : 갈릴레오 eclipse에서 사용하는 기본 junit 4.4 버전에도 harmcrest core lib가 있다. 이것도 제거</P>