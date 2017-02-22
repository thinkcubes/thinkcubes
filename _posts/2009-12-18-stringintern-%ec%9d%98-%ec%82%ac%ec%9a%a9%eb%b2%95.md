---
ID: 534
post_title: String.intern() 의 사용법
author: ""
post_date: 2009-12-18 10:09:37
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/12/18/stringintern-%ec%9d%98-%ec%82%ac%ec%9a%a9%eb%b2%95/'
published: true
---
<P><STRONG># String.intern()<BR></STRONG><BR>문자열을 생성하는 방법은 두 가지가 있다.<BR><FONT color=#3a32c3><BR>String a = "a"; &nbsp;&nbsp; // literal<BR>S</FONT><FONT color=#3a32c3>tring b = "a";<BR></FONT><FONT color=#3a32c3>String c = new String("a"); &nbsp;&nbsp; // constructor<BR></FONT><FONT color=#3a32c3>String d = new String("a");<BR></FONT><BR>JVM 에서 리터럴로 문자를 생성할 경우, 같은 내용의 문자열은 하나의 스트링 인스턴스를 참조한다.<BR><BR>즉, b 가 생성될 때, 값들을 비교해서 a와 같으므로 a를 참조하도록 참조값을 가진다.<BR><BR>생성자 방식으로 생성한 문자열은 String pool 에 보관되지 않고 별도의 인스턴스를 생성한다.<BR><BR>그래서 a == b 를 하면, 같은 참조값을 가지므로 true가 나오고,<BR><BR>c == d 를 하면, 다른 참조값을 가지므로 false가 나온다.<BR><BR>생성자로 만든 문자열을 리터럴 형식의 문자열과 비교하는 방법은 두 가지가 있다.<BR><FONT color=#3a32c3><BR>a.equals(c);<BR></FONT><BR>a와 c의 문자열 값을 비교하므로 true가 된다.<BR><FONT color=#3a32c3><BR>a == c.intern(); &nbsp;&nbsp; // true<BR></FONT><BR>intern() 메소드는 해당 문자열이 String pool에 등록된 문자열인지 확인하여<BR><BR>그 문자열의 주소를 리턴한다.<BR><BR><BR>그림 : <A href="http://blogfiles2.naver.net/data28/2007/11/30/289/javavm_xse01234.jpg" target=_blank>http://blogfiles2.naver.net/data28/2007/11/30/289/javavm_xse01234.jpg</A><BR><BR>출처 : Head First Java, Effective Java, 인터넷</P>