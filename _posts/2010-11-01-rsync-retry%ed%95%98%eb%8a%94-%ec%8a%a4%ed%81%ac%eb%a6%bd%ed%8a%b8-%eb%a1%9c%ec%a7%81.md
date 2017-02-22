---
ID: 577
post_title: rsync retry하는 스크립트 로직
author: ""
post_date: 2010-11-01 09:19:40
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2010/11/01/rsync-retry%ed%95%98%eb%8a%94-%ec%8a%a4%ed%81%ac%eb%a6%bd%ed%8a%b8-%eb%a1%9c%ec%a7%81/'
published: true
---
[code]#!/bin/sh
yesterday=<code>date -d "1 day ago" "+%Y%m%d"</code>
target="/home/$yesterday/"

rsync -av (REMOTE) $target
sleep 1

if [ ! -d "$target" ]; then
    rsync -av (REMOTE2) $target
fi[/code]

<div><br></div>

<div>-d 라는 인자가 해당 디렉토리의 존재 여부에 따라 boolean 값을 리턴해주게 된다.</div>

<div><br></div>

<div>즉, 해당 디렉토리를 확인해보고 rsync가 실패해서 신규 디렉토리가 생성되지 않았다면</div>

<div><br></div>

<div>백업 서버로 연결해서 rsync를 1회 retry하는 스크립이다.</div>

<div><br></div>

<div>(주. REMOTE는 remote 서버의 rsync 저장소를 의미합니다)</div>