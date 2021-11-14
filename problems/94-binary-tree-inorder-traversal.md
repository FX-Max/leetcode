## 题目

* 94. 二叉树的中序遍历

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
    function inorderTraversal($root) {
        if (!$root) {
            return [];
        }

        $left = $this->inorderTraversal($root->left);
        $result[] = $root->val;
        $right = $this->inorderTraversal($root->right);
        
        return array_merge($left, $result, $right);
    }
}

class Solution {

    private $res = [];
    /**
     * @param TreeNode $root
     * @return Integer[]
     */
    function inorderTraversal($root) {
        if (!$root) {
            return [];
        }
        $this->inorderTraversal($root->left);
        array_push($this->res, $root->val);
        $this->inorderTraversal($root->right);
        return $this->res;
    }
}
```