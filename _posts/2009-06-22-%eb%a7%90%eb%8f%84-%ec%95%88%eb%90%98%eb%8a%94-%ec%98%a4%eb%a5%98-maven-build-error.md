---
ID: 373
post_title: '말도 안되는 오류 : maven build error'
author: ""
post_date: 2009-06-22 10:31:00
post_excerpt: ""
layout: post
permalink: 'http://52.78.225.187/2009/06/22/%eb%a7%90%eb%8f%84-%ec%95%88%eb%90%98%eb%8a%94-%ec%98%a4%eb%a5%98-maven-build-error/'
published: true
---
mavern에서 war:inplace 파라미터로 build를 하면,<BR><BR>target/classes에서 컴파일 후, 자동으로 webapp 하위폴더로 카피해준다.<BR><BR>위 파라미터를 쓰면 webapp 하위에 있는 jsp(view) 파일들은 그냥 사용할 수 있고<BR><BR>컴파일된 클래스만 복사하면 되니까 훨씬 효율적이다.<BR><BR><BR>그런데 왜 안되지?<BR><BR>if(false) { ... } else { ... } 와 같은 구문을 썼는데,<BR><BR>else문을 거치지 않는 오류가 발생했다.<BR><BR>디버거를 이용했는데, 도대체 왜 else 문을 거치지 않고 바로 빠져나가는지 몰랐다.<BR><BR>그런데, 수정된 소스 코드가 컴파일된 후 webapp 하위로 복사되지 않았다.<BR><BR>즉, 수정 백날해도 웹페이지에 적용이 되지 않은 것 이다.<BR><BR>maven goal을 local로 설정했는데, 이 부분 때문에 안 된 것이다.<BR><BR>goal 부분을 모두 삭제하고 빌드했더니 정상적으로 동작한다.<BR><BR>왜 안되지?<BR><BR>흑.. 모르겠다, maven build랑 properties에 대해서 공부 좀 해야겠다ㅠ.ㅠ