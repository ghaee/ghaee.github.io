---
layout: post
title: "suninatas.com Challenge WEB 05"
tags: [suninatas.com, web]
---

# WEB
## 05

Check Key Value라는 문구와 함께 입력하는 값이 보인다. 하지만 값을 입력해도 아무 변화도 일어나지 않았다. <br>
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-1.PNG)
그래서 소스를 봤더니 코드가 난독화 되어있어 알아볼 수 없었다. <br>
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-2.PNG)
난독화된 코드를 볼 수 있는 방법은 document.write()와 alert() 등이 있다. <br>
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-3.PNG)
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-4.PNG)
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-5.PNG)
콘솔창에서 document.write()를 이용해서 난독화를 풀었더니 원본 소스코드가 나타났다. 난독화 시키는 함수로 해석된다.  <br>
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-6.PNG)
콘솔창에서 PASS()함수에 소스를 읽었을 때 확인했던 힌트인 12342046413275659를 넣었더니 9c43c20c라는 코드가 나왔다. 이 코드를 값을 입력하는 창에 입력하면 플래그가 나타난다.
![_config.yml]({{ site.baseurl }}/images/suninatas.com/suninatas_5-7.PNG)


## flag : Unp@cking j@vaScript

