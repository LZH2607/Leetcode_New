# 【LeetCode】队列



[toc]



## 933. 最近的请求次数

相关题解：[最近的请求次数](https://leetcode.cn/problems/number-of-recent-calls/solutions/1467662/zui-jin-de-qing-qiu-ci-shu-by-leetcode-s-ncm1/)

AC代码（Java）：

```java
import java.util.ArrayDeque;
import java.util.Deque;

class RecentCounter {
    Deque<Integer> deque = new ArrayDeque<>();

    public RecentCounter() {
    }

    public int ping(int t) {
        deque.addLast(t);
        while (deque.getFirst() < t - 3000) {
            deque.removeFirst();
        }
        return deque.size();
    }
}
```

