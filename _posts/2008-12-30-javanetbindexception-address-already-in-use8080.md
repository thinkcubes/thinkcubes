---
ID: 279
post_title: 'java.net.BindException: Address already in use:8080'
author: ""
post_date: 2008-12-30 00:46:29
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2008/12/30/javanetbindexception-address-already-in-use8080/
published: true
---
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px; BACKGROUND-COLOR: #e4e4e4">심각: Error initializing endpoint<BR><BR>java.net.BindException: Address already in use:8080<BR><BR>at org.apache.tomcat.util.net.JIoEndpoint.init(JIoEndpoint.java:501)<BR><BR>at org.apache.coyote.http11.Http11Protocol.init(Http11Protocol.java:176)<BR><BR>at org.apache.catalina.connector.Connector.initialize(Connector.java:1058)<BR><BR>at org.apache.catalina.core.StandardService.initialize(StandardService.java:677)<BR><BR>at org.apache.catalina.core.StandardServer.initialize(StandardServer.java.795)<BR><BR>at org.apache.catalina.startup.Catalina.load(Catalina.java:530)<BR><BR>at org.apache.catalina.startup.Catalina.load(Catalina.java:550)<BR><BR>at sun.reflect.NativeMethodAccessorImpl.invoke(Native Method)<BR><BR>at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:39)</DIV><BR>위와 같은 에러는 이미 8080 포트를 사용중일 때 나타난다.<BR><BR>이미 할당되어 사용되는 포트(21, 22, 25, 80 과 같은)를 톰캣이 사용하려고 할 때에도 나타나지만,<BR><BR>주로 개발중에 발생하는 경우는 이미 톰캣이 동작중인데, 다시 톰캣을 올리려고 할 때 발생하는 에러이다.<BR><BR>간혹, java.net.BindException: Address already in use: JVM_Bind 이라는 에러로 발생하기도 한다.<BR><BR>서버 포트가 이미 사용중이라니, 바로 포트를 비워주면 된다.<BR><BR>C:\&gt;netstat -a -n -o 를 실행하면,<BR><BR>TCP 127.0.0.1:8081 127.0.0.1:8080&nbsp; Listening 4 와 같은 문자열이 쭈욱 표시된다.<BR><BR>Local Address에서 포트를 확인한 후, 제일 오른쪽 PID를 확인한다.<BR><BR>PID에 해당하는 프로세스를 종료시키기 위해서는,<BR><BR>작업관리자 &gt; 프로세스 끝내기를 이용하면 된다.<BR><BR><BR>참고 : 작업관리자에서 보기 &gt; 열선택 &gt; PID 를 하면 PID를 볼 수 있게 된다.