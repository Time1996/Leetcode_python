# Leetcode 面试题 43 1~n整数中1出现的次数
***
### 题目描述

输入一个整数 `n` ，求1～n这n个整数的十进制表示中1出现的次数。

例如，输入12，1～12这些整数中包含1 的数字有1、10、11和12，1一共出现了5次。

**示例1:**

	输入：n = 12
	输出：5


**示例2：**

	输入：n = 13
	输出：6
	
**说明：**

* `1 <= n < 2^31`


### 考点

数学


### 代码
执行用时: **28ms**, 内存消耗: **13MB**

```
class Solution:
    def countDigitOne(self, n: int) -> int:
        res = 0
        i = 1  # 个位开始
        while n // i != 0:
            high = n//(i*10) # 高位数
            current = (n//i) % 10  # 第i位数
            low = n - (n//i) * i  # 低位数
            if current == 0:
                res += high * i
            elif current == 1:
                res += high * i + low + 1
            else:
                res += (high+1) * i
            i *= 10
        return res
```



