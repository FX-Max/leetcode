## 题目

326. 3的幂

给定一个整数，写一个函数来判断它是否是 3 的幂次方。如果是，返回 true ；否则，返回 false 。

整数 n 是 3 的幂次方需满足：存在整数 x 使得 n == 3x

* 进阶：你能不使用循环或者递归来完成本题吗？

## 思路

## 代码

```php

class Solution {

    /**
     * @param Integer $n
     * @return Boolean
     */
    function isPowerOfThree($n) {
        // 方法1，递归
        if ($n <= 0) {
            return false;
        }
        if ($n == 1) {
            return true;
        }
        if (($n % 3) !== 0) {
            return false;
        }
        return $this->isPowerOfThree($n/3);
/*
        // 方法2：循环取余
        while ($n && $n % 3 == 0) {
            $n = $n / 3;
        }
        return $n == 1;
 */

/*
        // 方法3：乘法
        $a = 1;
        while($a <= $n){
            if ($a == $n) {
                return true;
            }
            $a *= 3;
        }
        return false;
*/

    }
}

```