## 题目

## 思路

## 代码

```php
/**
 * Definition for a singly-linked list.
 * class ListNode {
 *     public $val = 0;
 *     public $next = null;
 *     function __construct($val = 0, $next = null) {
 *         $this->val = $val;
 *         $this->next = $next;
 *     }
 * }
 */
class Solution {

    /**
     * @param ListNode $head
     * @return ListNode
     */
    function deleteDuplicates($head) {
        if (!$head) {
            return null;
        }
        $cur = $head;
        while ($cur->next) {
            if ($cur->val == $cur->next->val) {
                $cur->next = $cur->next->next;
            } else {
                $cur = $cur->next;
            }
        }
        return $head;
    }
}
```

