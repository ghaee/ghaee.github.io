---
layout: post
title: "webhacking.kr 06"
tags: [web, webhacking.kr, decode, base64]
---

### level 06

ID / PW가 주어지고 힌트는 base64인걸 보아 encoding / decoding과 관련이 있을 것.  

![_config.yml]({{ site.baseurl }}/images/webhacking.kr/06_encoding.png) 

***encodig***  
주어진 id / pw를 base64로 20번 인코딩하고 숫자는 특수 문자로 치환한다.  
그런 다음 user / password의 쿠키값으로 설정한다.  

![_config.yml]({{ site.baseurl }}/images/webhacking.kr/06_decoding.png) 

***decoding***  
위에서 설정한 쿠키값을 받아서 특수 문자 - > 숫자로 치환하고 base64로 20번 디코딩한다.    
즉 인코딩한 방법을 그대로 거꾸로 실행하면서 자연스럽게 디코딩된다.    

@solve를 실행시키려면 디코딩된 id /pw가 모두 admin이어야한다.  

하지만 이미 인코딩된 쿠키값을 그대로 받아오기 때문에 처음부터 인코딩할 때 **admin을 인코딩했어야한다.**  
그래서 쿠키 user / password의 값을 
(1) admin을 base64로 20번 인코딩하고   
(2) 숫자 -> 특수 문자로 치환한 값으로 설정해주면  
***decoding*** 부분에서 자연스레 admin을 뱉을 것이다.  
(근데 (2)는 필요없음 ; **쿠키값 변조해서 새로고침하면 바로 decoding 부분만 실행됨**, 외부에서 (1)만 했을 때 어차피 특수문자는 없어서 치환할 것도 없음)

![_config.yml]({{ site.baseurl }}/images/webhacking.kr/06_admin.png)

쿠키 user에 'admin'을 (1)한 값을 넣어주니 아이디가 admin으로 바뀐다.  
password도 같은 방법으로 했더니 문제가 풀림  

정답 : user / password에 'admin'을 base64로 20번 디코딩한 값을 넣어준다.