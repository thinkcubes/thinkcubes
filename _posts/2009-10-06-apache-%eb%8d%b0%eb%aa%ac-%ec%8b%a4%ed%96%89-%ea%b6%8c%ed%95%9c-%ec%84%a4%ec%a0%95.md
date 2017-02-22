---
ID: 490
post_title: apache 데몬 실행 권한 설정
author: ""
post_date: 2009-10-06 08:22:27
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/10/06/apache-%eb%8d%b0%eb%aa%ac-%ec%8b%a4%ed%96%89-%ea%b6%8c%ed%95%9c-%ec%84%a4%ec%a0%95/'
published: true
---
apachectl 은 httpd 데몬을 띄우는 일종의 alias로 작동한다.<BR><BR>apachectl 에서 옵션(-k)가 없을 경우 디폴트 옵션으로 적용한다.<BR><BR>그래서 apachectl start 를 실행하면 내부적으로는 httpd -k start 로 동작한다.<BR><BR>그런데 아래와 같은 오류가 발생한다.<BR><BR>
<BLOCKQUOTE><FONT color=#008000>Permission denied: make_sock: could not bind to address [::]:80<BR>Permission denied: make_sock: could not bind to address 0.0.0.0:80<BR>no listening sockets available, shutting down<BR>Unable to open logs</FONT></BLOCKQUOTE>apache 데몬을 root 권한이 아닌 사용자 계정으로 로딩하기 위해서 소유권을 바꿨더니 발생한다.<BR><BR>기본적으로 예약된 포트는 root 권한 이외의 계정으로는 오픈할 수 없기 때문이다.<BR><BR>이럴 때는,<BR><BR><FONT color=#0000ff>chown root.root httpd<BR>chmod +s httpd</FONT><BR><BR>를 해주면, httpd의 권한이 <FONT color=#0000ff>-rwsr-sr-x</FONT> 로 변경된다.<BR><BR>그리고 freeism(사용자 계정)으로 소유권이 지정된 ( 즉, <FONT color=#0000ff>chown freeism.freeism apachectl</FONT> )<BR><BR>apachectl 을 통해서 httpd 데몬을 로딩하면,<BR><BR>사용자 계정으로 마치 root 처럼 데몬을 띄워준다.