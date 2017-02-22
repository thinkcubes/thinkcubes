---
ID: 487
post_title: >
  virtual box 에서 usb 메모리
  인식하는 법
author: ""
post_date: 2009-09-21 07:57:52
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/09/21/virtual-box-%ec%97%90%ec%84%9c-usb-%eb%a9%94%eb%aa%a8%eb%a6%ac-%ec%9d%b8%ec%8b%9d%ed%95%98%eb%8a%94-%eb%b2%95/'
published: true
---
1) virtual box 사용자 그룹에 계정을 추가함 <BR><BR><FONT color=#0000ff><FONT color=#000000># </FONT>usermod -G vboxusers -a USERID</FONT><BR><BR><FONT color=#0000ff><FONT color=#000000>#</FONT> grep vboxusers /etc/group<BR></FONT><FONT color=#000000>vboxusers:x:123:USERID</FONT><BR><BR>2) /etc/fstab 파일에 추가함<BR><BR><FONT color=#0000ff>none /sys/bus/usb/drivers usbfs devgid=123,devmode=664 0 0<BR></FONT>(devgid는 위에서 grep 결과에 나온 값이다)<BR><BR>3) 재부팅 후 다시 virtual box를 실행하면 해당 내용이 적용되어 있음<BR><BR><BR>이거 뭐, virtual box도 그렇고 리눅스도 그렇고 자기가 좀 알아서 인식하는 법이 없어-ㅅ-<BR><BR>아우 귀찮게시리 하나하나 다 설정해줘야 하는.. 쩝쩝