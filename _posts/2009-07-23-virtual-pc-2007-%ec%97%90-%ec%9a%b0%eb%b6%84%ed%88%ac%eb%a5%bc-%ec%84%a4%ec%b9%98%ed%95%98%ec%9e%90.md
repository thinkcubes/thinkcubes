---
ID: 425
post_title: >
  Virtual PC 2007 에 우분투를
  설치하자
author: ""
post_date: 2009-07-23 10:41:00
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/07/23/virtual-pc-2007-%ec%97%90-%ec%9a%b0%eb%b6%84%ed%88%ac%eb%a5%bc-%ec%84%a4%ec%b9%98%ed%95%98%ec%9e%90/'
published: true
---
<P>최근 서버 활용 능력에 대한 필요성을 크게 느끼고<BR><BR>그동안 100% 사용률을 보이던 윈도우의 비중을 줄이고,<BR><BR>우분투로 일부 portion을 나누려고 했다.<BR><BR>이미 개발 테스트용으로 비스타를 사용하기 위해 무료인<BR><BR>virtual pc 2007을 컴퓨터에 설치해두었으므로, 최대한 활용해보려고 했으나<BR><BR>왠일인지 설치가 제대로 되지 않는다.<BR><BR>그냥 까만 화면에 오류 메시지 나오고 먹통이다.<BR><BR>검색을 통해 알아낸 방법으로 현재 정상 설치중이다^-^<BR><BR><BR>
<BLOCKQUOTE>
<P>To get the CD to load,<BR>Press F4 to select an alternate starting mode. When it pops up, change to Safe graphics mode and press Enter.<BR>Select F6 and add “noreplace-paravirt” to the end of the command line and press Enter.<BR>Now pick “Try Ubuntu…” (should already be selected) and press enter. Do NOT pick the Install Ubuntu option, 
<P>Once Ubuntu is loaded from CD, select install from the desktop and it’ll build the system on the VPC disk.<BR>After you press restart, it just kind of hangs there. I shut the VPC session down and told it to save state, then started it again and it booted fine. </P></BLOCKQUOTE>
<P><BR><BR>출처 : <A href="http://blogs.technet.com/seanearp/archive/2008/05/13/installing-ubuntu-8-04-hardy-heron-in-virtual-pc-2007.aspx" target=_blank>http://blogs.technet.com/seanearp/archive/2008/05/13/installing-ubuntu-8-04-hardy-heron-in-virtual-pc-2007.aspx</A></P>