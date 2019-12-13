---
layout: post
title: "NACTF2019 Vyom's Soggy Croutons"
tags: [nactf2019, cipher, crypto, caesar]
---
기본적인 카이사르(시저) 암호다.  

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main()
{
    char s[10000];
    gets(s);
    for(int n=1; n<=26; n++)
    {
        for(int i=0; i<strlen(s); i++)
        {
            if(i<strlen(s)){
                if(isalpha(s[i]))
                {
                    if(s[i]==90)
                        s[i]=65;
                    else if(s[i]==122)
                        s[i]=97;
                    else
                        s[i]++;
                }
            }
        }
        printf("%d번째: %s\n",n,s);
    }
}
```
![_config.yml]({{ site.baseurl }}/images/nactf2019/caesar.png)

