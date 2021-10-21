## 题目

* 19. 删除链表的倒数第 N 个结点

给你一个链表，删除链表的倒数第 n 个结点，并且返回链表的头结点。

## 思路
快慢指针，快指针先走n步，然后双指针一起走，当快指针到达尾部时，此时慢指针的下一个元素正好是需要删除的元素。

## 代码

```php

class Solution {

    /**
     * @param ListNode $head
     * @param Integer $n
     * @return ListNode
     */
    function removeNthFromEnd($head, $n) {
        $dummy = new ListNode(null);
        $dummy->next = $head;

        $fast = $slow = $dummy;
        for ($i = 0; $i <= $n; $i++) {
            $fast = $fast->next;
        }

        while ($fast !== null) {
            $fast = $fast->next;
            $slow = $slow->next;
        }

        $slow->next = $slow->next->next;

        return $dummy->next;
    }
}

```
