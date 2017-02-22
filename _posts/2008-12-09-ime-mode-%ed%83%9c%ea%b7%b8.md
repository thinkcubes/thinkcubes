---
ID: 267
post_title: ime-mode 태그
author: ""
post_date: 2008-12-09 13:32:51
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2008/12/09/ime-mode-%ed%83%9c%ea%b7%b8/'
published: true
---
style 태그는 4가지 속성(attribution)을 가질 수 있다.<BR><BR>auto 는 default값이면서, 속성값이 지정되지 않은 것과 같은 효과이다.<BR><BR>active 는 한글 기본 설정이면서, 한영 전환이 가능하다.<BR><BR>inactive 는 영문 기본 설정이면서, 한영 전환이 가능하다.<BR><BR>disabled 는 IME가 불활성화되어 전환이 불가능하다.<BR><BR>이 속성은 태그로 쓰이면 <INPUT style="IME-MODE: active"> 과 같이 쓰이지만,<BR><BR>javascript 내에서는 속성으로 표현한다. 즉, inputname.style.imeMode="active" 로 표현한다.<BR><BR>ime-mode 태그는 ie에서만 사용된다.<BR><BR>예제)<BR><BR>한글모드 <INPUT style="IME-MODE: active" maxLength=10><BR><BR>영문모드 <INPUT style="IME-MODE: inactive" maxLength=10><BR>