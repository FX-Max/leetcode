## 题目

## 思路

## 代码

```php
/**
 * Definition for a binary tree node.
 * class TreeNode {
 *     public $val = null;
 *     public $left = null;
 *     public $right = null;
 *     function __construct($val = 0, $left = null, $right = null) {
 *         $this->val = $val;
 *         $this->left = $left;
 *         $this->right = $right;
 *     }
 * }
 */
class Solution {

    /**
     * @param TreeNode $root
     * @return Integer[]
     */
    function preorderTraversal($root) {
        if (!$root) {
            return [];
        }

        $result[] = $root->val;
        $left = $this->preorderTraversal($root->left);
        $right = $this->preorderTraversal($root->right);
        
        return array_merge($result, $left, $right);
    }
}
```
