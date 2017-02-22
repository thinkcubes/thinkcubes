---
ID: 468
post_title: 우분투 블루투스 마우스 설정
author: ""
post_date: 2009-09-07 09:46:01
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/09/07/ubuntu-%eb%b8%94%eb%a3%a8%ed%88%ac%ec%8a%a4-%eb%a7%88%ec%9a%b0%ec%8a%a4-%ec%84%a4%ec%a0%95/'
published: true
---
<P>먼저 마우스에서 초기화 단추(?)를 눌러서 램프가 깜빡깜빡 점등하게 한다.<BR><BR>1) 장치가 제대로 잡히는지 스캐닝 하고,<BR><BR><FONT color=#0000ff>$ hcitool scan<BR></FONT>Scanning ...<BR>xx:xx:xx:xx:xx:xx Microsoft Wireless Notebook Presenter Mouse 5000<BR><BR>2) 설정 파일에 해당 기기에 대한 정보를 추가해준다.<BR><BR><FONT color=#0000ff>$ sudo vi /etc/bluetooth/hcid.conf</FONT><BR><BR>device MOUSE_ADDR {<BR>&nbsp; &nbsp; name "Microsoft Wireless Notebook Presenter Mouse 5000";<BR>}<BR><BR>3) 장치 페어링을 하면 완료<BR><FONT color=#0000ff>$ sudo hidd --search</FONT><BR><BR>4) 매번 부팅 때마다 동일한 작업하기 귀찮으므로 데몬에 설정해준다.<BR><FONT color=#0000ff>$ sudo vi /etc/default/bluetooth</FONT><BR><BR>HIDD_OPTIONS="--master --connect MOUSE_ADDR --server"<BR><BR>5) 제대로 설정되었는지 확인<BR><FONT color=#0000ff>$ sudo /etc/init.d/bluetooth restart<BR><BR><BR></FONT><FONT color=#000000>윈도우는 딱!! 하면 턱!! 다 되는데, 이노무 리눅스 하나하나 다 설정해줘야 되는 게 귀찮다.<BR><BR>뭐, 그게 매력일까나..-ㅅ-a</FONT></P>