---
ID: 405
post_title: 'pom.xml 에서 properties 사용하기 : maven'
author: ""
post_date: 2009-07-01 10:05:01
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/07/01/pomxml-%ec%97%90%ec%84%9c-properties-%ec%82%ac%ec%9a%a9%ed%95%98%ea%b8%b0-maven/'
published: true
---
<img src="http://52.78.225.187/wp-content/uploads/1/8775578730.png" width="593" height="369" /><BR><BR>maven 빌드에 CheckStyle 과 PMD 같은 분석툴을 붙이다보니 pom.xml 이 지저분해지고 있다.<BR><BR>특히 RuleSet을 지정해야 하는 경우에 pom.xml 자체에 경로가 들어가게 되어 추후에 수정이 복잡할 거다.<BR><BR>이럴 때 위의 사항에서 5번 케이스를 적용하면 된다.<BR><BR>properties 태그에 해당 태그를 추가해서 ${ }로 불러다가 쓰면 좋다.<BR><BR>업데이트 해야될 내용이 properties에 모여 있으면, 탐색해서 수정하기 편할 것 같다.<BR><BR><FONT color=#177fcd>&lt;properties&gt;<BR>&nbsp; &lt;<FONT color=#0000ff>checkStyleRuleSet</FONT>&gt;${basedir}/CheckStyle_RuleSet_090512.xml&lt;/<FONT color=#0000ff>checkStyleRuleSet</FONT>&gt; <BR>&lt;/properties&gt;</FONT><BR><BR>이렇게 정해주면, pom.xml 내 어디서든지 <FONT color=#177fcd>${<FONT color=#0000ff>checkStyleRuleSet</FONT>}</FONT> 으로 value를 호출하여 사용할 수 있다.<BR><BR><BR>출처 : <A href="http://maven.apache.org/pom.html#Properties">http://maven.apache.org/pom.html#Properties</A>