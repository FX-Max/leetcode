## 题目


* 141. 环形链表

给定一个链表，判断链表中是否有环。

## 思路


## 代码

```php
class Solution {
    /**
     * @param ListNode $head
     * @return Boolean
     */
    function hasCycle($head) {
        $fast = $head;
        $slow = $head;
        while($fast->next) {
            $slow = $slow->next;
            $fast = $fast->next->next;
            if ($slow == $fast) {
                return true;
            }
        }
        return false;
    }
}
```
