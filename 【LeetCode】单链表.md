# 【LeetCode】单链表



[toc]



## 2. 两数相加

AC代码（Java）：

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * int val;
 * ListNode next;
 * ListNode() {}
 * ListNode(int val) { this.val = val; }
 * ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode head = new ListNode();
        ListNode tail = head;
        int carry = 0;
        while (l1 != null && l2 != null) {
            tail.next = new ListNode((l1.val + l2.val + carry) % 10, null);
            carry = (l1.val + l2.val + carry) / 10;
            l1 = l1.next;
            l2 = l2.next;
            tail = tail.next;
        }
        while (l1 != null) {
            tail.next = new ListNode((l1.val + carry) % 10, null);
            carry = (l1.val + carry) / 10;
            l1 = l1.next;
            tail = tail.next;
        }
        while (l2 != null) {
            tail.next = new ListNode((l2.val + carry) % 10, null);
            carry = (l2.val + carry) / 10;
            l2 = l2.next;
            tail = tail.next;
        }
        if (carry != 0) {
            tail.next = new ListNode(carry, null);
        }
        return head.next;
    }
}
```

