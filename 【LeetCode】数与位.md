# 【LeetCode】数与位



[toc]



## 7. 整数反转

相关题解：
[整数反转](https://leetcode.cn/problems/reverse-integer/solutions/755611/zheng-shu-fan-zhuan-by-leetcode-solution-bccn/)
[My accepted 15 lines of code for Java](https://leetcode.com/problems/reverse-integer/solutions/4060/my-accepted-15-lines-of-code-for-java/)

```java
class Solution {
    public int reverse(int x) {
        int ans = 0;
        while (x != 0) {
            if (ans * 10 / 10 != ans) {
                return 0;
            }
            ans = ans * 10 + x % 10;
            x = x / 10;
        }
        return ans;
    }
}
```



## 8. 字符串转换整数 (atoi)

相关题解：[来自 ChatGPT（已 AC）](https://leetcode.cn/problems/ba-zi-fu-chuan-zhuan-huan-cheng-zheng-shu-lcof/solutions/2156054/lai-zi-chatgptyi-ac-by-hsuanyeung-ibzu/)

AC代码（Java）：

```java
class Solution {
    public int myAtoi(String s) {
        char[] arr = s.toCharArray();
        int ans = 0;
        int sign = 1;
        int idx = 0;
        while (idx < arr.length && arr[idx] == ' ') {
            idx++;
        }
        if (idx < arr.length && (arr[idx] == '+' || arr[idx] == '-')) {
            sign = arr[idx] == '-' ? -1 : 1;
            idx++;
        }
        while (idx < arr.length && arr[idx] >= '0' && arr[idx] <= '9') {
            if ((ans * 10 + (arr[idx] - '0')) / 10 != ans) {
                return sign > 0 ? Integer.MAX_VALUE : Integer.MIN_VALUE;
            }
            ans = ans * 10 + (arr[idx] - '0');
            idx++;
        }
        return sign * ans;
    }
}
```



## 9. 回文数

AC代码（Java）：

```java
class Solution {
    public boolean isPalindrome(int x) {
        if (x < 0) {
            return false;
        }
        int x1 = x;
        int x2 = 0;
        while (x != 0) {
            x2 = x2 * 10 + x % 10;
            x = x / 10;
        }
        return x1 == x2;
    }
}
```

