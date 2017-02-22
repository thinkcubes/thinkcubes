---
ID: 506
post_title: 'Java Hotspot Garbage Collection #1'
author: ""
post_date: 2009-10-30 13:23:34
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2009/10/30/java-hotspot-garbage-collection-1/
published: true
---
<span class="Apple-style-span" style="font-family: dotum; color: rgb(102, 102, 102); ">

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>명시적 vs 자동적인 메모리 관리</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리 관리는 더 이상 사용하지 않는 객체에 할당된 메모리를 확인하고, </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;다른 객체가 사용할 수 있도록 메모리를 회수하는 일련의 과정을 말한다.</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리 관리는 개발자가 명시적으로 처리하는 경우와 머신에서 자동으로 처리하는 경우가 있다.</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 개발자가 명시적으로 처리하는 경우에는 예기치 못한 오류와 복잡한 로직에 의해</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 개발 및 수정하는 데에 많은 리소스가 사용된다.</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 명시적 메모리 관리에서 문제점으로는 복잡한 참조(dangling references)와</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리 누수(space leak)가 있다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 참조 : 메모리를 해제했는데 참조자가 호출하는 경우, 오류 혹은 예기치 못한 상황이 발생한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 누수 : 메모리를 모두 해제하지 않는 경우 (예, linked list에서 제일 처음 엘리먼트만 제거)</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 그래서 최근 OOP에서는 명시적 메모리 관리보다는 Garbage Collector 라는 프로그램에 의해</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 자동적으로 메모리 관리를 하는 추세이다. 이는 인터페이스의 추상화와 믿을 수 있는 코드에 대한</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;장점을 제공한다. (위의 참조 및 누수에 의한 단점을 보완)</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Garbage Collector 개요</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; Garbage Collection은 보통 할당된 메모리를 모두 사용하거나,</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 일정 이상의 threshold를 넘기면 동작한다.</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리를 회수하다보면 fragmentation(메모리 조각)이 많이 생겨서 재할당 시에 문제를 겪는</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;경우가 많은데, 할당 및 회수의 효율성을 지키는 범위에서 fragmentation을 피할 수 있는 동적</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리 할당에 대한 몇 가지 알고리즘이 나와 있다</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Garbage Collector의 역할</strong></p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 메모리 할당</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 메모리를 참조하는 객체가 있는지 확인</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 더이상 참조하지 않는 객체에 할당된 메모리의 회수</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Garbage Collection의 한계</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; Garbage Collector는 대부분의 메모리 할당 문제(위에서 언급한)를 해결하지만,</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 메모리가 모두 소진될 때까지 유효한 객체가 무한히 생성되면 무용지물이 된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;또한, Garbage Collector 자체가 시간 및 시스템 리소스를 일부 사용 한다.</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>원하는 Garbage Collection의 특성</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; Garbage Collection은 안전하고 이해하기 쉬워야 한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 즉, 사용하고 있는 메모리 영역에 대한 보호하고 사용하지 않는 메모리 영역을 남겨두어서는 안된다</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 그리고 application이 정지하는 시간을 최대한 줄일 수 있도록 해야한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; (그러나 대부분의 경우처럼 시간과 메모리와 실행빈도수는 trade-off 관계이다)</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 또한, 메모리 조각(fragmentation)을 많이 발생하지 않아야 한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 여러 부분의 메모리가 해제되었을 경우 서로 인접하지 않았기 때문에 메모리는 조각나고,</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 새로운 할당에 사용하기에 메모리 공간이 너무 작은 경우가 발생한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;(이를 해결하기 위해 압축(compaction)을 사용한다)</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 확장성(scalability)도 중요한 요소이다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 멀티스레드 혹은 멀티프로세서 시스템에서 서로 병목현상이 생기지 않도록 적절하게 조절해야 한다</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>디자인 비교</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 직렬 vs 병렬</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 직렬은 시간상의 문제점, 멀티프로세서 시스템에서 효율이 떨어짐 &nbsp;</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 병렬은 로직이 복잡하고, 메모리 조각 현상이 발생할 가능성이 있음</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 무정지 vs 정지</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - stop-the-world garbage collection은 실행중인 application의 동작을 멈춘 뒤, 동작한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;- 메모리가 정지된 상태(update가 일어나지 않는 상태)에서 메모리 관리가 동작하므로 간단하다. &nbsp;</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 무정지 garbage collection의 경우에도 약간의 멈춤이 있다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;- 무정지는 application의 퍼포먼스에 영향을 주고, 더 많은 메모리 사이즈를 요구한다.</p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 압축 vs 비압축 vs 복사</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 압축의 경우 메모리 재할당 시에 빠르고 편하다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 비압축은 빠르게 동작하지만 메모리조각의 문제가 발생할 수 있다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 복사의 경우추가적인 시간과 메모리가 소요된다.</p>

<br /><br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>퍼포먼스 측정 기준</strong></p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Throughput</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Overhead</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Pause Time</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Frequency</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Memory size</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Promptness</p>

</span>