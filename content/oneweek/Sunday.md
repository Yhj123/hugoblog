---
title: "KMP、BM、KR、Sunday算法"
date: 2020-12-27T10:48:10+08:00
draft: false
---
### 周日笔记
### KMP算法
```
#define _CRT_SECURE_NO_DEPRECATE
#include <iostream>
#include <string>
using namespace std;
void Violentmatch(char *p, char *s)
{
     //s与p的长度
     int sLen = strlen(s);
     int pLen = strlen(p);
     //匹配过程
     int i = 0;
     int j = 0;
     while (i < sLen&&j < pLen)
     {
         if (s[i] == p[j])
         {
              i++;
              j++;
         }
         else
         {
              i = i - j + 1;
              j = 0;
         }
     }
     //匹配结果不同,返回结果不同
     if (j == pLen)
         cout << "匹配成功" << endl;
     else
         cout << "匹配失败" << endl;
}
int main()
{
     char* p = "ABCDABD";
     char* s = "BBCABCDABABCDABCDABDE";
     Violentmatch(p, s);
}
```

