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

