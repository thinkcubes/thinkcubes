---
ID: 556
post_title: L4/L7 스위치 개요 (로드밸런서)
author: ""
post_date: 2010-02-01 05:05:21
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/02/01/l4l7-%ec%8a%a4%ec%9c%84%ec%b9%98-%ea%b0%9c%ec%9a%94-%eb%a1%9c%eb%93%9c%eb%b0%b8%eb%9f%b0%ec%84%9c/'
published: true
---
<SPAN class=Apple-style-span style="WORD-SPACING: 0px; FONT: medium Gulim; TEXT-TRANSFORM: none; COLOR: rgb(0,0,0); TEXT-INDENT: 0px; WHITE-SPACE: normal; LETTER-SPACING: normal; BORDER-COLLAPSE: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px"><SPAN class=Apple-style-span style="FONT-SIZE: 12px; LINE-HEIGHT: 18px; FONT-FAMILY: Dotum">
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">스위치의 분류 :<BR><BR></P>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">L2 : OSI 레이어 2에 속하는 MAC 어드레스를 참조하여 스위칭하는 장비<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">L3 : OSI 레이어 3에 속하는 IP주소를 참조하여 스위칭하는 장비<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">L4 : OSI 레이어 3~4에 속하는 IP 주소 및 TCP/UDP 포트 정보를 참조하여 스위칭하는 장비<BR></P>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px"><BR>L7 : OSI 레이어 3~7에 속하는 IP 주소, TCP/UDP 포트 정보 및 패킷 내용까지 참조하여 스위칭함<BR></P><BR><img src="http://52.78.225.187/wp-content/uploads/1/7162159243.png" width="549" height="113" /><BR><BR><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">L4/L7 스위치의 용도 :<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">일반적으로 서버들의 로드밸런싱을 위해 사용됨<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">복수개의 웹서버가 있을 때, 임의의 웹서버에 접속을 시도하면, 스위치가 각 서버의 부하를 고려하여<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">적당한 서버와 연결시켜준다.<BR></P><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">설정에 따라 순차적 연결 또는 접속이 가장 적은 서버에 연결하는 방식 등이 있다.<BR></P><BR><BR>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; PADDING-BOTTOM: 0px; MARGIN: 0px; PADDING-TOP: 0px">L4 스위치 :<BR></P>
<DIV><BR>Layer 4에서 패킷을 확인하고 세션을 관리하며, 로드밸런싱을 제공하는 스위치</DIV>
<DIV><BR>TCP/UDP 패킷 정보를 분석해서 해당 패킷이 사용하는 서비스 종류 별로 처리(HTTP, FTP, SMTP...)</DIV>
<DIV><BR>세션관리, 서버/방화벽 로드밸런싱, 네트워크 서비스 품질 보장<BR><BR><img src="http://52.78.225.187/wp-content/uploads/1/2185554435.png" width="320" height="264" /><BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp;</DIV>
<DIV>L7 스위치 :<BR></DIV>
<DIV><BR>L4 스위치의 서비스 단위 로드밸런싱을 극복하기 위해 포트 + 데이터 페이로드 패턴을 이용한 패킷 스위치<BR><BR>(e-mail 내용/제목, URL ...)<BR><BR>connection pooling(시스템 부하 감소), Traffic Compression (컨텐츠 압축 전송), 보안 기능<BR><BR><img src="http://52.78.225.187/wp-content/uploads/1/4626108567.png" width="320" height="264" /><BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>L4 vs L7 :<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>공통점 : 스위치로 들어온 패킷을 적절한 목적지로 전송해줌 (불필요한 패킷은 drop시킴)<BR></DIV>
<DIV><BR>차이점 : <BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; 기능과 역할은 동일하나 패킷을 분석하는 인텔리전스가 다름<BR></DIV>
<DIV><BR>&nbsp; L7은 보안 기능 강화</DIV>
<DIV><BR>&nbsp; (DOS/SYN 공격 방어, CodeRed/Nimda 등 감염 패킷 필터링, 네트워크 자원 독점 방지 등)<BR></DIV>
<DIV><BR><SPAN class=Apple-style-span style="WORD-SPACING: 0px; FONT: medium Gulim; TEXT-TRANSFORM: none; COLOR: rgb(0,0,0); TEXT-INDENT: 0px; WHITE-SPACE: normal; LETTER-SPACING: normal; BORDER-COLLAPSE: separate; orphans: 2; widows: 2; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px"><SPAN class=Apple-style-span style="FONT-SIZE: 12px; LINE-HEIGHT: 18px; FONT-FAMILY: Dotum">L7 스위치에 대한 오해 :</SPAN></SPAN></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; L7 스위치는 레이어 7 계층을 위한 스위치이다.<BR></DIV>
<DIV><BR>&nbsp; &nbsp;&nbsp; : 기본적으로 L2, L3 및 부분적으로 L4 스위치를 지원한다. 레이어5 세션 계층 위주이다.</DIV>
<DIV><BR>&nbsp; L7 스위치는 URL 기반 스위치다.<BR><BR>&nbsp; &nbsp;&nbsp; : L7 스위치 기능에 대한 일부분을 말한 것이다.</DIV>
<DIV><BR>&nbsp; L7 스위치는 모든 TCP/UDP 포트(0-65535)에 대한 인지가 가능하다.<BR><BR></DIV>
<DIV>&nbsp; &nbsp;&nbsp; : 알려진 일반 포트에 대한 세션처리는 가능하지만, 순간적으로 사용하는 임시 포트는 제한적이다.</DIV>
<DIV><BR>&nbsp;</DIV>
<DIV>sticky session :<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>L4 스위치를 통해 분배된 서비스 세션은 하나의 연결 요청에 1~n 중에 한 대의 서버에 분배된다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>여러 번 시도해도 그 때마다 1~n 중에 한 대에 분배되므로, 같은 서버에 접속될 확률은 1/n이 된다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>그러나 처음에 접속했던 서버와 같은 서버에 계속 연결시킬 수 있다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>바로&nbsp; sticky 옵션이다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>(일반적인 상태)<BR></DIV>
<DIV>사용자A -&gt; L4 -&gt; 1번서버<BR></DIV>
<DIV>사용자A -&gt; L4 -&gt; 3번서버<BR></DIV>
<DIV><BR>(sticky 상태)<BR>사용자A -&gt; L4 -&gt; 1번서버<BR>사용자A -&gt; L4 -&gt; 1번서버<BR><BR>기존 사용자의 세션 상태를 timeout 시간 내에는 계속 유지시켜주는 것이 sticky session이다.<BR><BR></DIV>
<DIV>timeout 시간은 60분 이내로 조절 가능하다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp;</DIV>
<DIV>sticky session의 문제점 :<BR><BR></DIV>
<DIV>L4 스위치의 가장 큰 목적(?)인 로드밸런싱이 제대로 동작하지 않을 수 있다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>개별 사용자가 사용할 경우에는 세션 timeout이 있으므로 어느 정도 로드밸런싱을 충족시킨다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>하지만 프록시서버를 사용하는 경우 문제가 된다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>예를 들어 회사에서 외부로 나가는 경우 각 PC의 IP가 아니라 프록시서버의 IP를 달고 나간다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>여러 사람이 timeout 시간 내에 접속하는 경우, 계속해서 한 서버에만 로드가 집중된다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>(외부에서 보기에는 동일한 사람으로 보이므로)<BR></DIV>
<DIV><BR><img src="http://52.78.225.187/wp-content/uploads/1/6713936024.png" width="415" height="187" /></DIV>
<DIV><BR>대안 :<BR><BR></DIV>
<DIV>SSL이나 기타 다른 보안모듈을 이용해서 인증된 특정 사용자에 대해서 Cookie/DB에 기록 후<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>해당 사용자에 대해서만 세션을 유지하도록 한다. (단점 : performance 저하 및 기타 cost)<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>그래서 L7 스위치를 사용한다.<BR></DIV>
<DIV><BR>&nbsp;</DIV>
<DIV>&lt; L7 스위칭 방식 &gt;</DIV>
<DIV><BR>URL 스위칭 :<BR><BR></DIV>
<DIV>URL 주소에서 특정 String을 검사하고, 검색된 문자열을 기준으로 부하를 분산시키는 방식이다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV><A class=con_link href="http://www.test.com/test.html" target=_blank>http://www.test.com/test.html</A><SPAN class=Apple-converted-space>&nbsp;</SPAN>이라는 주소로 사용자들이 웹페이지를 요청한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>해당 페이지는 이미지가 빈번히 변경되고, 이미지 크기도 크다. (전체적으로 로딩이 느리다)<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>이런 경우, client의 http request 내용에 html이 들어가면, 메인 웹서버로 전송하고..<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>해당 request에 jpg 등의 이미지를 요청하는 경우 이미지 웹서버로 분산할 수 있다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV><img src="http://52.78.225.187/wp-content/uploads/1/9125808847.png" width="366" height="222" /><BR></DIV>
<DIV>Cookie 스위칭 :<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>Http header의 cookie 값에 따른 특정 String을 기준으로 부하를 분산하는 방식이다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>Cookie 값 필드를 보고 설정된 분류 기준에 따라 어느 서버로 보낼지 결정한다.<BR></DIV>
<DIV><BR><img src="http://52.78.225.187/wp-content/uploads/1/7730045379.png" width="452" height="193" /></DIV>
<DIV><BR>&nbsp;</DIV>
<DIV>Content 스위칭 :<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>legacy한 L7 스위칭은 URL/Cookie 스위칭을 사용했으나,<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>최근 L7 스위칭은 Content 스위칭 방식을 이용한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>기존에는 제한적인 기능, 즉 호스트네임, URL, Cookie 를 기준으로 로드밸런싱을 하였으나,<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>L7 content 스위칭은 추가적인 기능을 지원한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; Http header 의 모든 필드를 기반으로 한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; XML content를 기반으로 한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; XML tags 나 multiple Http header를 기준으로 복잡한 로드밸런싱을 구현한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; Cookie 와 http header의 insertion과 deletion을 포함한 contents-rewrite 기능을 지원한다.<BR></DIV>
<DIV>&nbsp;</DIV>
<DIV>&nbsp; alternate한 url이나 도메인의 redirecting request를 지원한다.<BR><BR><BR>* 이미지출처 : 인터넷에 떠도는 것을 긁어왔습니다(마땅히 출처를 알 수가 없어요) 문제가 되면 연락주세요^^</DIV></SPAN></SPAN>