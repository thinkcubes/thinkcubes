---
ID: 569
post_title: NGINX와 Connection 오류
author: ""
post_date: 2010-03-12 10:11:27
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/03/12/nginx%ec%99%80-connection-%ec%98%a4%eb%a5%98/'
published: true
---
nginx 라는 초경량화된 웹서버가 있다. 뭐, 아파치랑 비슷한 역할을 하는데, 좀 가볍다는 정도인 듯 하다.<BR><BR>그런데 해당 웹서버를 쓰는 서버에 자바로 http client를 물리니 소켓 커넥션 시에<BR><BR>"Software caused connection abort" 라는 오류 메시지가 나타난다.<BR><BR>구글링을 해보니, ACK가 도달 안하고 어쩌고.. @%#$!!... 대충보니, 네트워크 핸드쉐이킹할 때 쳐내는 것 같다.<BR><BR>똑같은 프로그램인데, 아파치로 구동시에는 정상 응답이 오고.. nginx로 구동시에는 에러 응답이 온다.<BR><BR>
<P class=MsoNormal style="MARGIN: 0cm 0cm 0pt">[code]HTTP/1.1 200 OK<BR>Date: Wed, 10 Mar 2010 16:41:07 GMT<BR>Server: Apache/2.2.0 (Unix) mod_jk/1.2.15<BR>Cache-Control: no-cache<BR>[/code]<BR>[code]&lt;?xml version="1.0" encoding="utf-8" ?&gt;<BR>&lt;response&gt;<BR>&lt;/response&gt;<BR>[/code]<BR>[code]HTTP/1.1 200 OK<BR>Server: nginx/0.7.61<BR>Date: Wed, 10 Mar 2010 16:41:34 GMT<BR>Content-Type: text/xml;charset=UTF-8<BR>Connection: close<BR>Pragma: no-cache<BR>[/code]<BR>[code]&lt;html&gt;<BR>&lt;head&gt;&lt;title&gt;400 Bad Request&lt;/title&gt;&lt;/head&gt;<BR>&lt;body bgcolor="white"&gt;<BR>&lt;center&gt;&lt;h1&gt;400 Bad Request&lt;/h1&gt;&lt;/center&gt;<BR>&lt;hr&gt;&lt;center&gt;nginx/0.7.61&lt;/center&gt;<BR>&lt;/body&gt;<BR>&lt;/html&gt;<BR>[/code]<BR>도대체 이유를 잘 모르겠다. 뭔가 내가 쓰고 있는 라이브러리에서 request header를 조금 가공시키나?<BR><BR>좀 더 고민해봐야할 문제인 듯 하다^^</P>