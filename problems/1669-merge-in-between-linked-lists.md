## 题目

* 1669. 合并两个链表

给你两个链表 list1 和 list2 ，它们包含的元素分别为 n 个和 m 个。

请你将 list1 中下标从 a 到 b 的全部节点都删除，并将list2 接在被删除节点的位置。

## 思路


## 代码

```php

class Solution {

    /**
     * @param ListNode $list1
     * @param Integer $a
     * @param Integer $b
     * @param ListNode $list2
     * @return ListNode
     */
    function mergeInBetween($list1, $a, $b, $list2) {
        $n = 1;
        $left = $list1;
        $right = $list1;
        $dumyRight = null;
        $dumyRight->next = $right;
        while ($n <= $b) {
            $dumyRight->next = $right->next->next;
            if ($n < $a) {
                $left = $left->next; 
            }
            $right = $right->next;
            
            $n++;
        }
        $left->next = $list2;
        $cur = $list2;
        while ($cur->next) {
            $cur = $cur->next;
        }
        $cur->next = $dumyRight->next;
        return $list1;
    }
}

```
