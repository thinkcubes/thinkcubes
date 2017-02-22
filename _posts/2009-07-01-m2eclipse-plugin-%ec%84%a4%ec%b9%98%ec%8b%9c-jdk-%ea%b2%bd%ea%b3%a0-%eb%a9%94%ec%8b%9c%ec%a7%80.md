---
ID: 404
post_title: >
  m2eclipse plugin 설치시 JDK 경고
  메시지
author: ""
post_date: 2009-07-01 08:43:20
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/07/01/m2eclipse-plugin-%ec%84%a4%ec%b9%98%ec%8b%9c-jdk-%ea%b2%bd%ea%b3%a0-%eb%a9%94%ec%8b%9c%ec%a7%80/'
published: true
---
<BLOCKQUOTE>The Maven Intergration requires that Eclipse be running in a JDK because a number of Maven core plugins are using jars from the JDK<BR>Please make the -vm option in eclipse.ini is pointing to a JDK and verify that Installed<BR>JREs are also using JDK installs. </BLOCKQUOTE>
<DIV class=autosourcing-stub>
<P style="PADDING-RIGHT: 0px; PADDING-LEFT: 0px; FONT-WEIGHT: normal; FONT-SIZE: 12px; PADDING-BOTTOM: 0px; MARGIN: 11px 0px 7px; PADDING-TOP: 0px; FONT-STYLE: normal; FONT-FAMILY: Dotum"><BR>위와 같은 경고 메시지가 나올 경우에는 eclipse.ini 에서 vm의 정확한 위치를 기록해야 한다.<BR><BR><FONT color=#177fcd>-vm<BR>D:\ProgramFiles\Java\jdk1.5.0_16\bin\javaw.exe</FONT><BR>-showsplash<BR>org.eclipse.platform<BR>--launcher.XXMaxPermSize<BR>256m<BR>-framework plugins\org.eclipse.osgi_3.4.2.R34x_v20080826-1230.jar<BR>-vmargs<BR>-Dosgi.requiredJavaVersion=1.5<BR>-Xms256m<BR>-Xmx512m<BR>-XX:PermSize=256m<BR>-XX:MaxNewSize=512m<BR><BR>참고 사이트 : <A href="http://www.myeclipseide.org/PNphpBB2-printview-t-20880-start-0.html">http://www.myeclipseide.org/PNphpBB2-printview-t-20880-start-0.html</A></P></DIV>