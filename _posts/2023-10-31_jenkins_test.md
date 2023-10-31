---
layout: post
title: =Jenkins= 원격지에서 Maven 빌드를 할때
---


Jenkins 세팅에서 원격지 서버에서 Maven을 빌드 해서 적용하고 싶을 경우가 있다 

기본적으로 Ubuntu 터미널에서 Maven 사용할때는

```
mvn clean package
```

하면 ./target 폴더가 생성되면서 완료 되지만 

Jenkins에서 Build Steps 에서 

Send files or execute commands over SSH 하위에

Exec command 에서 사용하려면 

```
ERROR: Exception when publishing, exception message [Exec exit status not zero. Status [127]]
Build step 'Send files or execute commands over SSH' changed build result to UNSTABLE
```

해당 에러처럼 완료가 되지 않고 에러로 끝난다 

이럴 경우는 해결방법은 maven의 full path를 넣어주고 하면 된다 

```
/opt/maven/bin/mvn clean package

maven의 full path를 입력해준다
```

[##_Image|kage@cLWeWT/btshiEr12rF/x89n8ZXfGiQE2AUD6ZAOrK/img.png|CDM|1.3|{"originWidth":1055,"originHeight":1562,"style":"alignCenter","filename":"제목 없음.png"}_##]
