# 【LeetCode】哈希表



[toc]



## 1. 两数之和

相关视频：
[二数之和题解分析](https://www.bilibili.com/video/BV1hV411e7MW)
[二数之和代码解析](https://www.bilibili.com/video/BV1si4y1P7Eg)

AC代码（Java）：

```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            if (map.containsKey(target - nums[i])) {
                return new int[]{map.get(target - nums[i]), i};
            }
            map.put(nums[i], i);
        }
        return null;
    }
}
```

