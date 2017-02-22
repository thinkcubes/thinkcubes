---
ID: 573
post_title: jetty:run 에서 out of memory 발생
author: ""
post_date: 2010-08-24 07:03:56
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/08/24/jettyrun-%ec%97%90%ec%84%9c-out-of-memory-%eb%b0%9c%ec%83%9d/'
published: true
---
Invocation of init method failed; nested exception is java.lang.OutOfMemoryError: Java heap space

<div><br></div>

<div>jetty를 이용해서 웹서버를 구동하는데, 위와 같은 오류가 발생했다.</div>

<div><br></div>

<div>구글링을 해보니, jetty 옵션으로 메모리 용량을 설정하는 내용이 많이 나온다.</div>

<div><br></div>

<div>하지만 난 maven 플러그인으로 사용하고 있다.</div>

<div><br></div>

<div>다시 구글링을 해보니,</div>

<div><br></div>

<div>mvn 옵션으로 메모리 용량을 설정하면 된다고 한다.</div>

<div><br></div>

<div>Linux : "export MAVEN_OPTS=-Xmx1024m"</div>

<div>Windows : "set MAVEN_OPTS=-Xmx1024m"</div>

<div><br></div>

<div>물론 시스템 변수에 미리 등록해둬도 된다.</div>

<div><br></div>

<div><br></div>

<div>출처 : <a href="http://stackoverflow.com/questions/2007192/maven-jetty-plugin-how-to-control-vm-arguments">http://stackoverflow.com/questions/2007192/maven-jetty-plugin-how-to-control-vm-arguments</a></div>