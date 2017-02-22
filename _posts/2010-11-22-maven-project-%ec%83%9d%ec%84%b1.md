---
ID: 578
post_title: maven project 생성
author: ""
post_date: 2010-11-22 09:19:54
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/11/22/maven-project-%ec%83%9d%ec%84%b1/'
published: true
---
매번 남이 만들어 놓은 코드 수정만 하다보니,

<div><br></div>

<div>처음 이클립스에서 프로젝트를 생성하려면 막막한 경우가 많다.</div>

<div><br></div>

<div>workspace에서...</div>

<div><br></div>

<div>[code]mvn archetype:create -DgroupId=kr.co.freeism.app -DartifactId=sample-app -DarchetypeArtifactId=maven-archetype-webapp[/code]</div>

<div><br></div>

<div>위와 같이 입력하면, maven 프로젝트가 생성되고.. 기본 pom.xml 파일이 생성된다.</div>

<div><br></div>

<div>[code]mvn eclipse:clean eclipse:eclipse[/code]</div>

<div><br></div>

<div>이렇게 해주면, 이클립스에서 작업하기 좋도록 프로젝트 정보를 수정해준다.</div>

<div><br></div>

<div><br></div>

<div>이제, 내가 평소에 자주 보던 소스 구조를 이용해서 코딩을 시작할 수 있다^^b</div>

<div><br></div>