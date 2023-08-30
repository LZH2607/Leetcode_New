# 【LeetCode】滑动窗口



[toc]



**“滑动窗口”为“双指针”的一个特例。**



## 3. 无重复字符的最长子串

相关视频：[一道算法题理解滑动窗思想！【趣刷Leetcode】 No.3 无重复字符的最长子串](https://www.bilibili.com/video/BV113411v7Ak/)

AC代码（Java）：

```java
import java.util.HashSet;
import java.util.Set;

class Solution {
    public int lengthOfLongestSubstring(String s) {
        char[] arr = s.toCharArray();
        if (arr.length == 0) {
            return 0;
        }
        Set<Character> set = new HashSet<>();
        int maxLen = 1;
        for (int i = 0; i < arr.length; i++) {
            set.add(arr[i]);
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[j] == arr[j - 1] || set.contains(arr[j])) {
                    set.clear();
                    break;
                }
                set.add(arr[j]);
                maxLen = Math.max(maxLen, j - i + 1);
            }
        }
        return maxLen;
    }
}
```

