## 题目


* 171. Excel 表列序号

给你一个字符串 columnTitle ，表示 Excel 表格中的列名称。返回该列名称对应的列序号。

## 思路
简单的26进制问题

## 代码

```php
class Solution {

    /**
     * @param String $columnTitle
     * @return Integer
     */
    function titleToNumber($columnTitle) {

        $hash = [
            'A' => 1,
            'B' => 2,
            'C' => 3,
            'D' => 4,
            'E' => 5,
            'F' => 6,
            'G' => 7,
            'H' => 8,
            'I' => 9,
            'J' => 10,
            'K' => 11,
            'L' => 12,
            'M' => 13,
            'N' => 14,
            'O' => 15,
            'P' => 16,
            'Q' => 17,
            'R' => 18,
            'S' => 19,
            'T' => 20,
            'U' => 21,
            'V' => 22,
            'W' => 23,
            'X' => 24,
            'Y' => 25,
            'Z' => 26,
        ];
        $len = strlen($columnTitle);
        $ans = 0;
        for ($i = 0; $i <= $len - 1; $i++) {
            $ans = $hash[$columnTitle[$i]] * pow(26, $len - 1 - $i) + $ans;
        }
        return $ans;
    }
}

```

