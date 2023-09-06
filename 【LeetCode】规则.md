# 【LeetCode】规则



[toc]



## 14. 最长公共前缀

AC代码（Java）：

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        int idx = 0;
        while (true) {
            boolean flag = false;
            for (String str : strs) {
                if (str.length() <= idx || str.charAt(idx) != strs[0].charAt(idx)) {
                    flag = true;
                    break;
                }
            }
            if (flag) {
                break;
            }
            idx++;
        }
        return strs[0].substring(0, idx);
    }
}
```

