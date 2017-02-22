---
ID: 530
post_title: >
  eclipse에서 junit 테스트가
  auto-build 되지 않음
author: ""
post_date: 2009-12-14 16:42:43
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/12/14/eclipse%ec%97%90%ec%84%9c-junit-%ed%85%8c%ec%8a%a4%ed%8a%b8%ea%b0%80-auto-build-%eb%90%98%ec%a7%80-%ec%95%8a%ec%9d%8c/'
published: true
---
eclipse에서 junit 테스트를 작성하면 우측 하단에 잠깐 메시지가 나오면서

<div><br></div>

<div>별다른 컴파일 작업없이 auto-build 되어 바로 적용된다.</div>

<div><br></div>

<div>그래서 우리는 ctrl + F11 이나 alt + x + t 를 하면 바로 테스트 결과를 볼 수 있다.</div>

<div><br></div>

<div>그런데 어느 순간부터 컴파일을 따로 해줘야만 적용된다.</div>

<div><br></div>

<div>무슨 얘긴고하니,</div>

<div><br></div>

<div>테스트 실패를 확인하고, 내용을 수정했는데 이전 내용으로 테스트가 진행된다.</div>

<div><br></div>

<div>이클립스가 꼬였나 싶어서 새로 깔았는데도 여전하다.</div>

<div><br></div>

<div>결국 엄청난 삽질 후에..</div>

<div><br></div>

<div>junit library를 새로 설치했더니 정상 동작한다.</div>

<div><br></div>

<div>정확한 원인은 모르겠다.</div>

<div><br></div>

<div>하지만 eclipse에 내장되어 있는 junit 패키지와 maven repository에서 가져온 junit 패키지 사이에서</div>

<div><br></div>

<div>뭔가 꼬여서 제대로 동작하지 않았던 것은 아닌가 조심스레 추측해볼 뿐이다..-_-</div>