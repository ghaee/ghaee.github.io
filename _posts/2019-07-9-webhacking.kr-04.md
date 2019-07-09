---
layout: post
title: "webhacking.kr 04"
tags: [web, webhacking.kr, decode, sha]
---

### level 04

![_config.yml]({{ site.baseurl }}/images/webhacking.kr/04_prob.png)  

==로 끝나는걸 보아 bas64다.  
디코드 해보니 c4033bff94 b567a190e3 3faa551f41 1caef444f2가 나왔다.  
저 문자열의 길이는 40이고 f 이상의 문자가 없는 것을 보아 16진수가 아닐까 생각한다.  
SHA-1 해시값이 40바이트의 16진수로 저장되니 SHA-1으로 디코드 했다.  
첫 번째 decoded value -> a94a8fe5ccb19ba61c4c0873d391e987982fbbd3  
두번째 decoded value -> test  

정답 : test  