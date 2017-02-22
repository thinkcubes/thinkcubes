---
ID: 535
post_title: for-each 루프문
author: ""
post_date: 2009-12-18 10:11:32
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/12/18/for-each-%eb%a3%a8%ed%94%84%eb%ac%b8/'
published: true
---
<P><STRONG># for-each 루프문<BR><BR></STRONG>자바 1.5 배포판 이후에 제공하는 for-each 루프는 순환자나 인덱스 변수를 감춤으로써<BR><BR>에러의 가능성을 제거시켜준다.<BR><BR>// AS-IS :<BR>f<FONT color=#3a32c3>or (int i = 0; i &lt; a.length; i++) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; doSomething(a[i]);<BR></FONT><FONT color=#3a32c3>}<BR></FONT><BR>// TO-BE :<BR><FONT color=#3a32c3>for (Element e : elements) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; doSomething(e);<BR></FONT><FONT color=#3a32c3>}<BR></FONT><BR>성능의 저하는 없고, 코드가 깔끔하게 바뀌기 때문에 가독성이 좋아진다.<BR><BR>for-each 루프는 컬렉션과 배열에 대한 반복 처리는 물론 모든 iterator 객체에서 사용 가능하다.<BR><BR>하지만 인덱스를 반드시 써야 하는 상황에서는 for-each를 사용할 수 없다. <BR><BR>(예 : 필터링, 변환, 병행반복처리)<BR><FONT color=#3a32c3><BR>public Map createMapForMock(String ... keys) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; Map resultMap = new HashMap();<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; Map exampleMap = getExampleMap();<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; for (String key : keys) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; &nbsp; &nbsp; resultMap.put(key, exampleMap.get(key));<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; }<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; return resultMap;<BR></FONT><FONT color=#3a32c3>}<BR><BR></FONT><BR>출처 : Head First Java, Effective Java, 인터넷</P>