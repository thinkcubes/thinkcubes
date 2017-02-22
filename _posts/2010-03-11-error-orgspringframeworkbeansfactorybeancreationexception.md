---
ID: 567
post_title: '[ERROR] org.springframework.beans.factory.BeanCreationException'
author: ""
post_date: 2010-03-11 09:06:55
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2010/03/11/error-orgspringframeworkbeansfactorybeancreationexception/
published: true
---
<P>[code][ERROR][2010/03/11 18:03:05] Context initialization failed - ContextLoader::initWebApplicationContext()<BR>org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'xxDAO' defined in class path resource<BR>[/code]<BR>방금 전까지 잘 돌아가던 이클립스+톰캣이었는데,<BR>&nbsp;<BR>아무런 이유없이 위같은 exception을 뱉어내면서 톰캣이 뜨지를 않는다.<BR><BR>완전 삽질하다가 결국 톰캣 옵션이 문제인 것을 알았다.<BR><BR><img src="http://52.78.225.187/wp-content/uploads/1/9361237677.png" width="529" height="132" /><BR><BR>저기에서 Enable security 옵션이 체크되어 있네... -_- (원래 체크 안되어 있었다)<BR><BR>무슨 옵션인지 정확하게는 모르겠지만, 나도 모르는 사이에 실수로 클릭을 했나보다.<BR><BR>일단은, 바쁜고로 넘어가고.. 저 옵션에 대해서는 다음번에 연구해보기로 한다.</P>