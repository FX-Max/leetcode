## 题目

* 118. 杨辉三角

给定一个非负整数 numRows，生成「杨辉三角」的前 numRows 行。

在「杨辉三角」中，每个数是它左上方和右上方的数的和。

## 思路

dp[i][j] = dp[i-1][j-1] + dp[i-1][j]


## 代码

```
class Solution {

    /**
     * @param Integer $numRows
     * @return Integer[][]
     */
    function generate($numRows) {
    /**
    1
    1 1
    1 2 1
    
    dp[i][j] = dp[i-1][j-1] + dp[i-1][j]
     */
     $dp = [];
     for ($i = 0; $i < $numRows; $i++) {
         for ($j = 0; $j <= $i; $j++) {
             if ($j == 0 || $j == $i) {
                 $dp[$i][$j] = 1;
             } else {
                 $dp[$i][$j] = $dp[$i-1][$j-1] + $dp[$i-1][$j];
             }
         }
     }
     return $dp;
    }
}
```