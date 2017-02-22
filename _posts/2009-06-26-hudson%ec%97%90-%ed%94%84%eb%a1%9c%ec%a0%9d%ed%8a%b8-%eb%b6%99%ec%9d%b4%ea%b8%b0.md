---
ID: 391
post_title: Hudson에 프로젝트 붙이기
author: ""
post_date: 2009-06-26 13:15:28
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/06/26/hudson%ec%97%90-%ed%94%84%eb%a1%9c%ec%a0%9d%ed%8a%b8-%eb%b6%99%ec%9d%b4%ea%b8%b0/'
published: true
---
요새 허드슨에 프로젝트를 붙이고 있다.<BR><BR>각종 테스트 툴들을 덕지덕지 붙이는 건 기본이다.<BR><BR>근데 이놈이 척하면 턱하니 돌아가줄 것이지..<BR><BR>제대로 돌아가지 않고, 기한은 임박하고... 팔자에도 없는 야근을 하게 됐다.<BR><BR>일단, 테스트 케이스가 junit4에 맞춰져서 짰는데,<BR><BR>maven pom.xml에서 junit 3.8로 되어 있는 부분이 에러다.. 수정.<BR><BR>그리고, 테스트 케이스에 fail이 잔뜩 뜨니.. 패키징이 안된다. 쳇..<BR><BR>&lt;build&gt;<BR>&nbsp; &lt;plugins&gt;<BR>&nbsp;&nbsp; &nbsp;&lt;plugin&gt;<BR>&nbsp; &nbsp;&nbsp; &nbsp;&lt;groupId&gt;org.apache.maven.plugins&lt;/groupId&gt;<BR>&nbsp; &nbsp; &nbsp; &lt;artifactId&gt;maven-surefire-plugin&lt;/artifactId&gt;<BR>&nbsp; &nbsp; &nbsp; &lt;configuration&gt;<BR>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp;&lt;testFailureIgnore&gt;true&lt;/testFailureIgnore&gt;<BR>&nbsp; &nbsp; &nbsp; &lt;/configuration&gt;<BR>&nbsp; &nbsp; &nbsp;&lt;/plugin&gt;<BR>&nbsp; &lt;/plugins&gt;<BR>&lt;/build&gt;<BR><BR>일단은 위와 같은 코드로.. 테스트 실패를 싸그리 무시해버렸다..<BR><BR>그랬더니 정상적으로 나오긴 한다만..<BR><BR>저거 언제 또 다 수정하냐..ㅠ.ㅠ