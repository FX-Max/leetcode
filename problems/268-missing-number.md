## 题目


* 268. 丢失的数字

给定一个包含 [0, n] 中 n 个数的数组 nums ，找出 [0, n] 这个范围内没有出现在数组中的那个数。

## 思路

## 代码

```php
class Solution {

    /**
     * @param Integer[] $nums
     * @return Integer
     */
    function missingNumber($nums) {

        // 方法1，异或方式
        //0和任意数异或的结果为那个数 相同的两个数异或为0
        $res = sizeof($nums);
        for ($i = 0; $i < sizeof($nums); ++$i) {
            $res ^= $nums[$i];
            $res ^= $i;
        }
        return $res;

/*
        // 方法2，hash表
        $arr = [];
        for ($i = 0; $i < sizeof($nums); $i++) {
            $arr[$nums[$i]] = $nums[$i];
        }
        for ($i = 0; $i < sizeof($nums)+1; $i++) {
            if (!isset($arr[$i])) {
                return $i;
            }
        }
        return -1;
*/
/*
        // 方法3，数学计算
        $indexSum = $sum = 0;
        for($i = 0; $i < sizeof($nums); $i++){
            $indexSum += ($i+1);
            $sum += $nums[$i];
        }
        return $indexSum - $sum;
*/
    }
}
```

