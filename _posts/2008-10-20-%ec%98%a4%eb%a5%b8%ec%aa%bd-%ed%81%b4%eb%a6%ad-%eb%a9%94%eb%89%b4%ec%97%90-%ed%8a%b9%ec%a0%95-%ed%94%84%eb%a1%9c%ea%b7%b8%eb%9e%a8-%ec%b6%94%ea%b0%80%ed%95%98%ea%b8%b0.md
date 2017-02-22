---
ID: 241
post_title: >
  오른쪽 클릭 메뉴에 특정
  프로그램 추가하기
author: ""
post_date: 2008-10-20 09:23:16
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2008/10/20/%ec%98%a4%eb%a5%b8%ec%aa%bd-%ed%81%b4%eb%a6%ad-%eb%a9%94%eb%89%b4%ec%97%90-%ed%8a%b9%ec%a0%95-%ed%94%84%eb%a1%9c%ea%b7%b8%eb%9e%a8-%ec%b6%94%ea%b0%80%ed%95%98%ea%b8%b0/'
published: true
---
<ol>
<li>시작 &gt; 실행 &gt; Regedit 실행<BR><BR>2. HKET_CLASSES_ROOT&#42; 로 이동<BR><BR>3. shellex와 동일한 레벨 트리에 Shell 키를 추가<BR><BR>4. Shell 키 아래에 "표시되기 원하는 이름" 에 대한 키 추가 (ex, Notepad )<BR><BR>5. 해당 키 아래에 Command 키를 추가<BR><BR>6. Command 키 안에 (기본값) 이라는 문자열 값이 표시된다. 클릭해서 "실행 원하는 명령어" 를 입력<BR><BR>7. Regedit를 종료하고 실행되는지 테스트한다.<BR><BR>정확한 루트 : 아래 그림에서 HKEY_CLASSES_ROOT&#42;\Shell\Notepad++\Command 이다.<BR><BR>노트패드와 같은 경우 "경로\notepad.exe" "%1" 을 해주면 %1은 해당 파일에 대한 파라미터이고,<BR><BR>필수적으로 쌍따옴표(" ")를 해야 한글이나 띄어쓰기 있는 경로를 제대로 인식할 수 있다.<BR><BR><img src="http://52.78.225.187/wp-content/uploads/1/9019883622.png" width="223" height="286" /></li>
</ol>