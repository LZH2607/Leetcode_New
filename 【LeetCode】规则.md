# 【LeetCode】规则



[toc]



## 14. 最长公共前缀

AC代码（Java）：

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        for (int i = 0; ; i++) {
            for (String str : strs) {
                if (str.length() <= i || str.charAt(i) != strs[0].charAt(i)) {
                    return strs[0].substring(0, i);
                }
            }
        }
    }
}
```

