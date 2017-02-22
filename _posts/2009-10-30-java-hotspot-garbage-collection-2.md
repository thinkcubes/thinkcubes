---
ID: 507
post_title: 'Java Hotspot Garbage Collection #2'
author: ""
post_date: 2009-10-30 13:26:00
post_excerpt: ""
layout: post
permalink: >
  http://52.78.225.187/2009/10/30/java-hotspot-garbage-collection-2/
published: true
---
<span style="font-family: dotum; color: rgb(102, 102, 102); ">

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Generational Collection</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 이 기술은 각가의 메모리를 나이(generation)으로 나눈다. (보통 young과 old 2단계로 나눈다)</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 여기서는 2가지 가정을 한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 대부분의 객체는 오랫동안 참조되지 않고 죽는다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 더 오래되었거나 더 새 객체에 대한 참조는 거의 없다.</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; YG(young generation)은 상대적으로 더 자주 실행되고 효율적이며 빠르다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; YG중에서 살아남은 객체들은 진화하여 OG(old generation)이 된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; OG영역은 천천히 사용되며, GC가 적게 동작하고 한번 동작시 더 오래 걸리기도 한다.</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; YG는 자주 실행되기 때문에 속도, OG는 메모리 용량 면에서 유리한 GC 알고리즘을 선택하게 된다</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp; &nbsp; <img src="http://blogfiles.naver.net/20090925_198/xegal_1253854138978BVqbk_png/k-20090925-439913_xegal.png" id="userImg423114" onload="settimeout(&quot;resizeimage(423114)&quot;,200)" =""="" onclick="popview(this.src)" name="cafeuserimg" style="border-top-style: none; border-right-style: none; border-bottom-style: none; border-left-style: none; border-width: initial; border-color: initial; width: 400px; height: 323px; "></p>

<br><br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Java 5.0 HotSpot Garbage Collector</strong></p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>HotSpot Generations</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - young generation : 처음 생성된 객체들</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - old generation : 진화한 객체, 혹은 YG에 배정되기에는 큰 용량의 객체들</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - permanent generation : GC를 진행하는데 사용하는 자원들</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; young generation </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - Eden + 2개의 survivor spaces 으로 구성</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 처음 생성되는 객체는 모두 Eden에 할당된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - 적어도 1번 이상 collection에서 살아 남으면 survivor space에 옮겨지게 된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; - OG에 들어가기에는 아직 충분하지 않은 경우 한 번 더 collection 되도록 기회를 준다)</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp; &nbsp; <img src="http://blogfiles.naver.net/20090925_122/xegal_12538553079301us4k_png/k-20090925-508988_xegal.png" id="userImg1758461" onload="settimeout(&quot;resizeimage(1758461)&quot;,200)" =""="" onclick="popview(this.src)" name="cafeuserimg" style="border-top-style: none; border-right-style: none; border-bottom-style: none; border-left-style: none; border-width: initial; border-color: initial; width: 533px; height: 308px; "></p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 각 generation 영역이 가득차게 되면, 각 영역에 대한 collection이 수행된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 만약 YG에서 진화해서 OG로 올라와야 할 객체들이 OG의 수용량 보다 많은 경우,</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;YGC은 수행되지 않는다. 대신, OGC이 전체 Heap 영역에 대해서 수행된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; (CMS collector는 예외)</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Fast Allocation</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 간단한 bump-the-pointer 기술을 이용해서 사용가능한 메모리의 인접 블럭에 할당한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 최근에 메모리 할당한 객체의 끝에 포인터로 표시해두고, 새로운 메모리 할당이 필요할 경우에 해당</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;영역에 적절한지 검토한 뒤 할당하고 포인터를 업데이트 한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 멀티스레드 환경에서 동작할 때에는 병목현상이 생기고 퍼포먼스가 떨어진다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 그래서 HotSpot JVM 에서는 Thread-Local Allocation Buffers(TLABs)라는 기술을 적용한다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp;이 기술은 각각의 스레드에 버퍼를 적용하여 퍼포먼스를 향상시킨다. </p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; TLABs의 소모 용량을 최소화하는 것이 필요한데, 평균적으로 Eden의 1%내외로 적용한다.</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><strong>Serial Collector</strong></p>

<br />

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 직렬방식은 YG, OG에 대한 GC를 모두 직렬로 처리한다.</p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; YG Collector</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp; &nbsp; &nbsp;<img src="http://blogfiles.naver.net/20090925_128/xegal_12538578454700Ropz_png/k-20090925-532248_xegal.png" id="userImg6640574" onload="settimeout(&quot;resizeimage(6640574)&quot;,200)" =""="" onclick="popview(this.src)" name="cafeuserimg" style="border-top-style: none; border-right-style: none; border-bottom-style: none; border-left-style: none; border-width: initial; border-color: initial; width: 495px; height: 308px; "></p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp; &nbsp; <img src="http://blogfiles.naver.net/20090925_78/xegal_1253857910232sNdQw_png/k-20090925-532310_xegal.png" id="userImg2321695" onload="settimeout(&quot;resizeimage(2321695)&quot;,200)" =""="" onclick="popview(this.src)" name="cafeuserimg" style="border-top-style: none; border-right-style: none; border-bottom-style: none; border-left-style: none; border-width: initial; border-color: initial; width: 495px; height: 308px; "></p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; OG collection</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp; &nbsp; &nbsp; &nbsp;<img src="http://blogfiles.naver.net/20090925_230/xegal_1253858050033lfVNa_png/k-20090925-532491_xegal.png" id="userImg9081143" onload="settimeout(&quot;resizeimage(9081143)&quot;,200)" =""="" onclick="popview(this.src)" name="cafeuserimg" style="border-top-style: none; border-right-style: none; border-bottom-style: none; border-left-style: none; border-width: initial; border-color: initial; width: 495px; height: 308px; "></p>

<br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 직렬방식은 클라이언트에서만 실행되면서, pause time이 허용되는 프로그램에서 사용된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; J2SE5.0에서 직렬방식은 server-class 머신이 아닌 방식에서 디폴트로 선택된다.</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">&nbsp;&nbsp; 명시적으로 사용하려면 -XX:+UseSerialGC 를 추가하면 된다.</p>

<br><br><br>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">참고 문서 출처:</p>

<p style="list-style-type: none; list-style-position: initial; list-style-image: initial; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; "><a target="_blank" href="http://java.sun.com/javase/technologies/hotspot/gc/memorymanagement_whitepaper.pdf" style="text-decoration: none; ">http://java.sun.com/javase/technologies/hotspot/gc/memorymanagement_whitepaper.pdf</a></p>

</span>