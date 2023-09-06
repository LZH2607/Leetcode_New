# 【LeetCode】双指针



[toc]



## 11. 盛最多水的容器

相关视频：
[五分钟力扣 Leetcode 第11题 盛最多水的容器 Python入门算法刷题 解法 80%](https://www.bilibili.com/video/BV1uc411h7XA)
[「双指针」的魅力！图解 LeetCode 第 11 号问题：盛最多水的容器](https://www.bilibili.com/video/BV1mJ411M7gE/)

AC代码（Java）：

```java
class Solution {
    public int maxArea(int[] height) {
        int left = 0;
        int right = height.length - 1;
        int maxArea = 0;
        while (left < right) {
            int area = Math.min(height[left], height[right]) * (right - left);
            maxArea = Math.max(maxArea, area);
            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }
        return maxArea;
    }
}
```

