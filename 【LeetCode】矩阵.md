# 【LeetCode】矩阵



[toc]



## 矩阵遍历

```java
public class Main {
    public static void main(String[] args) {
        int len = 7;
        for (int i0 = 0, j0 = 2; i0 >= 0 && i0 < len && j0 >= 0 && j0 < len; i0++, j0++) {
            for (int i = i0, j = j0; i >= 0 && i < len && j >= 0 && j < len; i--, j++) {
                System.out.println(String.format("[%s][%s]", i, j));
            }
        }
    }
}
```

