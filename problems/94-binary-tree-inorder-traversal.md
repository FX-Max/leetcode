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

// 迭代法
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

        $res = []; // 存储结果
        $arr = []; // 栈
        $cur = $root;
        while ($cur != null || !empty($arr)) {
            if ($cur != null) { // 将左节点入栈
                array_push($arr, $cur); 
                $cur = $cur->left;
            } else { // 出栈，并处理其右节点
                $cur = array_pop($arr);
                $res[] = $cur->val;
                $cur = $cur->right;
            }
        }
        return $res;
    }
}

// 递归法
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

// 递归法2
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