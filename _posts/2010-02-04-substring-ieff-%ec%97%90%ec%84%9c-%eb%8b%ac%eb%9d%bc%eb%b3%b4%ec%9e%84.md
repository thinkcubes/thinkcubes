---
ID: 563
post_title: substring IE/FF 에서 달라보임
author: ""
post_date: 2010-02-04 05:33:08
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/02/04/substring-ieff-%ec%97%90%ec%84%9c-%eb%8b%ac%eb%9d%bc%eb%b3%b4%ec%9e%84/'
published: true
---
custom 태그를 이용해서 보이는 글자수 이상이 되면 ... 으로 잘라내도록 되어 있다.<BR><BR>그런데 거기에 css로 영역을 넘어가는 것에 대해서는 <FONT color=#9b18c1>text-overflow:ellipsis</FONT> 로 잘라내도록 되어 있다.<BR><BR>어떻게 보면 중복 적용인가?<BR><BR>여튼 그런 경우에 css 영역에는 6자 제한을 두고, tag 에는 7자 제한을 두게 되었다.<BR><BR>이 때, IE 와 FF에서 서로 다른 반응을 보인다.<BR><BR>IE에서는 <BR>&nbsp; <img src="http://52.78.225.187/wp-content/uploads/1/7949235520.png" width="69" height="19" /><BR><BR>FF에서는<BR>&nbsp; <img src="http://52.78.225.187/wp-content/uploads/1/4147662568.png" width="76" height="18" /><BR><BR>IE에서는 tag가 우선되어 먼저 글자수를 잘라내고 ...으로 표현되었고,<BR><BR>FF에서는 css가 우선되어 먼저 ellipsis로 잘라내서 7번째 글자가 살짝 잘려서 표현됐다.<BR><BR><BR>코드 상에 크게 문제가 없으니 웹페이지 렌더링하는 방식이 다른 것 같다.. 면서<BR><BR>그냥 둘 다 같은 6자 제한으로 맞췄다.. -ㅅ- <BR><BR>(굳이 우주에서 쓸 수 있는 볼펜 만들 필요없잔아, 그냥 연필쓰면 되는데...)