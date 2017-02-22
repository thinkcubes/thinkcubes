---
ID: 520
post_title: >
  자바에서 가변인자(여러
  파라미터) 사용하기
author: ""
post_date: 2009-11-03 10:41:09
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/11/03/%ec%9e%90%eb%b0%94%ec%97%90%ec%84%9c-%ea%b0%80%eb%b3%80%ec%9d%b8%ec%9e%90%ec%97%ac%eb%9f%ac-%ed%8c%8c%eb%9d%bc%eb%af%b8%ed%84%b0-%ec%82%ac%ec%9a%a9%ed%95%98%ea%b8%b0/'
published: true
---
<P>요즘 테스트케이스를 작성하는데, 예상되는 값 또는 입력되는 값에 대한 map 설정이 복잡하다.<BR><BR>코드의 난이도가 높은 것이 아니라..<BR><BR>예를 들면,<BR><BR>Map&lt;String, Object&gt;<FONT color=#0000ff>&nbsp;inputMap</FONT> = <FONT color=#9b18c1>new</FONT> HashMap&lt;String, Object&gt;();<BR>inputMap.put(<FONT color=#0000ff>"name"</FONT>, <FONT color=#0000ff>"freeism"</FONT>);<BR>inputMap.put(<FONT color=#0000ff>"sex"</FONT>, <FONT color=#0000ff>"male"</FONT>);<BR>inputMap.put(<FONT color=#0000ff>"job"</FONT>, <FONT color=#0000ff>"programmer"</FONT>);<BR>...<BR><BR>이렇게 많은 대입값을 일일이 넣으려니 아무리 테스트케이스지만 너무 지저분하다.<BR><BR>그래서 따로 공통으로 쓸 수 있는 클래스로 뽑아내려하다보니,<BR><BR>가변 파라미터(인자)를 사용하는 것이 좋을 것 같다.<BR><BR>간단하다. 인자를 넘기는 부분에 ... 만 찍어주면 된다.<BR><BR><FONT color=#9b18c1>public static void main</FONT>(String[] args) {<BR>&nbsp; &nbsp; printString(<FONT color=#0000ff>"name"</FONT>);<BR>&nbsp; &nbsp; printString(<FONT color=#0000ff>"name"</FONT>, <FONT color=#0000ff>"sex"</FONT>);<BR>&nbsp; &nbsp; printString(<FONT color=#0000ff>"name"</FONT>, <FONT color=#0000ff>"sex"</FONT>, <FONT color=#0000ff>"job"</FONT>);<BR>}<BR><BR><FONT color=#9b18c1>public void printString</FONT>(String ... strings) {<BR>&nbsp; &nbsp;<FONT color=#9b18c1> for</FONT>(String str : strings) {<BR>&nbsp; &nbsp; &nbsp; &nbsp; System.out.println(str);<BR>&nbsp; &nbsp; }<BR>}<BR><BR>이렇게 하면, 인자가 몇 개가 되던지 알아서 판단해준다.<BR><BR>미리 만든 클래스에서 값을 모두 정해놓고, 인자를 넘겨서 해당 값을 map에 담아서 리턴하도록 해야겠다.<BR><BR>참조한 블로그에 보면, 글쓴이의 윗분이 안정성 문제로 쓰지 말라고 했다고 적혀있지만..<BR><BR>테스트 케이스니까 내 맘대로 하겠어.. 난 쓰지 말란 얘긴 못 들었음..-ㅅ-<BR><BR><BR>참조사이트 : <A href="http://entireboy.egloos.com/3783699">http://entireboy.egloos.com/3783699</A></P>