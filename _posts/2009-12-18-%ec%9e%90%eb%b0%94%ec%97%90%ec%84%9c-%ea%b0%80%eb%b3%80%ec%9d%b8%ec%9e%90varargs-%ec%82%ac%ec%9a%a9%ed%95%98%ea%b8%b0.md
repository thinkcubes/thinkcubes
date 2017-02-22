---
ID: 536
post_title: >
  자바에서 가변인자(varargs)
  사용하기
author: ""
post_date: 2009-12-18 10:14:29
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/12/18/%ec%9e%90%eb%b0%94%ec%97%90%ec%84%9c-%ea%b0%80%eb%b3%80%ec%9d%b8%ec%9e%90varargs-%ec%82%ac%ec%9a%a9%ed%95%98%ea%b8%b0/'
published: true
---
<P><STRONG># 가변 인자<BR></STRONG><BR>자바 1.5 배포판부터 "가변 아리티 메소드" 라는 가변 인자 메소드가 추가 되었다.<BR><BR>메소드 호출 시 전달된 인자의 개수를 자신의 크기로 하는 배열을 생성하여,<BR><BR>그 배열을 파라미터로 호출된 메소드로 전달한다.<BR><FONT color=#3a32c3><BR>private void setParams(Object ... params) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; Map dummyParams = new HashMap();<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; for (int i = 0; i &lt; params.length; i++) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; &nbsp; &nbsp; dummyParams.put(keys[i], params[i]);<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; }<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; action.setParams(dummyParams);<BR></FONT><FONT color=#3a32c3>}<BR></FONT><BR>최소한 1개 이상의 파라미터가 필요한 경우<BR><BR>// AS-IS : 런타임 오류<BR><FONT color=#3a32c3>if ( params.length == 0 ) {<BR></FONT><FONT color=#3a32c3>&nbsp; &nbsp; throw new IllegalArgumentException("Error");<BR></FONT><FONT color=#3a32c3>}<BR></FONT><BR>// TO-BE :<BR><FONT color=#3a32c3>private void setParams(Object firstParam, Object ... remainingParam) { ...<BR></FONT><BR>성능이 중요한 상황에서 가변 인자를 사용할 때는 주의하자.<BR><BR>가변 인자 메소드를 호출할 때마다 배열 생성과 초기화가 일어난다.<BR><BR>예제) 사용 빈도가 많은 것들은 그냥 선언하고, 적은 것은 가변 인자를 사용함<BR><FONT color=#7820b9>public void foo() { }<BR></FONT><FONT color=#7820b9>public void foo(int a1) { }<BR></FONT><FONT color=#7820b9>public void foo(int a1, int a2) { }<BR></FONT><FONT color=#7820b9>public void foo(int a1, int a2, int ... rest) { }<BR><BR><BR></FONT><FONT color=#000000>출처 : Head First Java, Effective Java, 인터넷</FONT></P>