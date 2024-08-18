---
title: 浅析NC20241 [SCOI2005] 扫雷MINE
summary: Easily learn Algorithms in C/C++ with detailed example !!!
date: 2021-02-16
type: docs
math: false
tags:
  - C/C++
image:
  caption: 'game'
---

**题目：**
[https://ac.nowcoder.com/acm/problem/20241](http://www.nowcoder.com) 
- 万圣节到了 ，“余”人国流行起了一种简单的扫雷游戏，这个游戏规则和扫雷一样，如果某个格子没有雷，那么它里面的数字 表示和它8连通的格子里面雷的数目。
- 现在棋盘是n×2的，第一列里面某些格子是雷，而第二列没有雷，由于第一列的雷可能有多种方案满足第二列的数的限制，你的任务即根据第二列的信息确定第一列雷有多少种摆放方案。
- N &lt;= 1e5

**思路：**
只要确定了第一列第一格是否有雷的状态，第一列后面的状态可以根据上一行第二列的状态判定。
所以只要判断当第一列第一个有雷情况和无雷情况下方案是否成立（最终可能方案数只有0，1，2）
因此采用枚举。

初始代码————通过率30%

```
#include<stdio.h>
const int INF = 0x3f3f3f3f;
const int maxn = 1e4+7;
int a[maxn] = {0};  //存储第二列的初始数据
int judge[maxn] = {0};  //储存第一列的数据
 
int main () {
    //数据初始化
    int n;
    scanf("%d", &amp;n);
    for (int i = 1; i &lt;= n; i++) {
        scanf("%d", &amp;a[i]);
    }
    int ans = 0;
    int temp = a[0];  //temp 动态地存三个数
    
    //枚举情况一
    //第一列第一格有雷
    int i;
    temp = 1;  
    judge[1] = 1;
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
            temp -= judge[i-1];
        }
        if (a[i] &lt; temp) {
            break;
        }
    }
    if (i &gt; n) {
        ans++;
    }
     
    memset(judge, 0, sizeof(int)*man
    //枚举情况二
    //第一列第一格无雷
    temp = 0;
    judge[1] = 0;
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
            temp -= judge[i-1];
        }
        if (a[i] &lt; temp) {
            break;
        }
    }
    if (i &gt; n) {
        ans++;
    }
     
    printf("%d", ans);
}
```
初始代码的问题及修改方法：
- 每次 i++，都应该执行 temp -= judge[i-1]; 所以应该放在 if 判断的外面 

即把下面的代码片段：
```
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
            temp -= judge[i-1];
        }
        if (a[i] &lt; temp) {
            break;
        }
    }
```
修改为：
```
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
        }
        temp -= judge[i-1];
        if (a[i] &lt; temp) {
            break;
        }
    }
```
通过率提升到30%
- 在每次判断 if (a[i] &gt; temp) 后，temp 已经动态存了当前 i 下 a [ i ] 所对应的第一列的三个格 ( i - 1 , i , i + 1 ) 中的雷数（前两个是上一次for循环保存在temp中的，第三个是当前for循环保存在temp中的），应该加上判断语句判断雷数是否符合。
再次修改上面的代码片段并调整代码顺序：
```
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &lt; temp) {
            break;
        }      
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
        }
        if (a[i] != temp) {
            break;
        }
        temp -= judge[i-1];

    }
```
通过率提升为90%

- ans判定的时候加强判断末尾的边界条件
  //注意上面的 for 循环最后出来的时候有 temp -= judge[i-1];  和  i++；
AC代码：

```
#include<stdio.h>
#include<string.h>
const int INF = 0x3f3f3f3f;
const int maxn = 1e4+7;
int a[maxn] = {0};
int judge[maxn] = {0};
int main () {
    int n;
    scanf("%d", &amp;n);
    for (int i = 1; i &lt;= n; i++) {
        scanf("%d", &amp;a[i]);
    }
    int ans = 0;
    int temp = a[0];  //temp 动态地存三个数
 
    //枚举情况一
    //第一列第一格有雷
    int i;
    temp = 1; 
    judge[1] = 1;
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &lt; temp) {
            break;
        }
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
        }
        if (a[i] != temp) {
        	break;
	}	 
        temp -= judge[i-1];
    }
    //判断此方案是否成立 
    //注意末尾边界条件（ temp == judge[i-1]）
    if (i &gt; n &amp;&amp; temp == judge[i-1]) {
        ans++;
    }
 
    memset(judge, 0, sizeof(int)*maxn);
    //枚举情况二
    //第一列第一格无雷
    temp = 0;
    judge[1] = 0;
    for (i = 1; i &lt;= n; i++) {
        if (a[i] &lt; temp) {
            break;
        }
        if (a[i] &gt; temp) {
            temp += 1;
            judge[i+1] = 1;
        }
        if (a[i] != temp) {
        	break;
	} 	
        temp -= judge[i-1];
    }
    if (i &gt; n &amp;&amp; temp == judge[i-1]) {
        ans++;
    }
 
    printf("%d", ans);
}
```

## Inline Images

```go
{{</* icon name="python" */>}} Python
```

renders as

{{< icon name="C" >}} C

## Did you find this page helpful? Consider sharing it 🙌
