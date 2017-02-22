---
ID: 278
post_title: 'org.xml.sax.SAXParseException : Content is not allowed in prolog'
author: ""
post_date: 2008-12-30 00:28:49
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2008/12/30/orgxmlsaxsaxparseexception-content-is-not-allowed-in-prolog/
published: true
---
<DIV style="PADDING-RIGHT: 10px; PADDING-LEFT: 10px; PADDING-BOTTOM: 10px; PADDING-TOP: 10px; BACKGROUND-COLOR: #faffa9">정보: Starting Servlet Engine: Apache Tomcat/6.0.16<BR><BR>2008. 12. 30 오전 11:13:32 org.apache.tomcat.util.digester.Digester fatalError<BR><BR>심각: Parse Fatal Error at line 1 column 1: Content is not allowed in prolog.<BR><BR>org.xml.sax.SAXParseException : Content is not allowed in prolog.<BR><BR>at org.apache.xerces.util.ErrorHandlerWrapper.createSAXParseException(Unknown Source)<BR><BR>at org.apache.xerces.util.ErrorHandlerWrapper.fataError(Unknown Source)<BR></DIV><BR>해당 에러는 XML을 파싱하지 못해서 일어나는 에러이다.<BR><BR>에러가 발생했다면, 관련된 설정파일들(xml)의 코드를 확인해보아야 한다.<BR><BR>xml 문서는 <?xml version="1.0" ... ?>으로 시작해야만 한다.<BR><BR>첫 줄에 위의 태그가 들어있지 않은 xml 파일에 대한 오류이다.