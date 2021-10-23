## 题目

* 328. 奇偶链表

给定一个单链表，把所有的奇数节点和偶数节点分别排在一起。请注意，这里的奇数节点和偶数节点指的是节点编号的奇偶性，而不是节点的值的奇偶性。

请尝试使用原地算法完成。你的算法的空间复杂度应为 O(1)，时间复杂度应为 O(nodes)，nodes 为节点总数。

## 思路

## 代码

```php

class Solution {

    /**
     * @param ListNode $head
     * @return ListNode
     */
    function oddEvenList($head) {
        if (!$head || !$head->next || !$head->next->next) {
            return $head;
        }

        $oddLast = $head;
        $evenHead = $head->next;
        $eventLast = $head->next;

        while ($oddLast->next && $eventLast->next) {
            $oddLast->next = $oddLast->next->next;
            $eventLast->next = $eventLast->next->next;
            $oddLast = $oddLast->next;
            $eventLast = $eventLast->next;
        }

        $oddLast->next = $evenHead;
        return $head;
    }
}

```
