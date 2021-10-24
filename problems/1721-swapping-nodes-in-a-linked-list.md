## 题目

* 1721. 交换链表中的节点

给你链表的头节点 head 和一个整数 k 。

交换 链表正数第 k 个节点和倒数第 k 个节点的值后，返回链表的头节点（链表 从 1 开始索引）。

## 思路

注意，仅需要交换值即可。

## 代码

```php

class Solution {

    /**
     * @param ListNode $head
     * @param Integer $k
     * @return ListNode
     */
    function swapNodes($head, $k) {
        $swap1 = $head;
        $swap2 = $head;

        $pos = 1;
        while ($pos < $k) {
            $swap1 = $swap1->next;
            $pos ++;
        }
        $temp = $swap1;
        while ($temp->next) {
            $swap2 = $swap2->next;
            $temp = $temp->next;
        }

        // 交换
        $tVal = $swap1->val;
        $swap1->val = $swap2->val;
        $swap2->val = $tVal;

        return $head;
    }
}

```
