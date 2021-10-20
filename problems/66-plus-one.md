## 题目

* 66. 加一

给定一个由 整数 组成的 非空 数组所表示的非负整数，在该数的基础上加一。

最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。


## 思路
先从最后一位加1；
若值比10大，则本位置仅保留个位上的数，进一位，倒数第二位上的数加1；
若值比10小，则本位置上的数直接为该值；
循环如上操作，若最终首位不为0，则说明最后一次计算，首位上没有进1，直接输出即可；
若最终首位为0，则说明最后一次计算，首位上进行了进1，估需要在前面补充一个1。
（因为本题中只是末尾加1，所有只要有进位，也仅会出现进1的情况，即仅会有9加1本位保持0，向前一位进1。）

## 代码

```php
class Solution {

    /**
     * @param Integer[] $digits
     * @return Integer[]
     */
    function plusOne($digits) {
        $length = sizeof($digits);
        // 分类讨论，第一种情况，最后一位小于9，则只需要将最后一位加1，然后就可以直接返回了。
        if ($digits[$length - 1] < 9) {
            $digits[$length - 1] += 1;
            return $digits;
        }
        /**
        * 分类讨论，第二种情况，就是最后一位为9，加1后需要向前进1的情况，
        * 此时依次向前，若需要进位，则判断前一位加1后是否需要进位，循环这个操作，
        * 当遇到不需要进位，则跳出，后面也都不需要在考虑进位问题了。
         */
        for ($i = $length - 1; $i>=0; $i--) {
            $temp = $digits[$i] + 1;
            if ($temp >= 10) {
                $digits[$i] = $temp - 10;
            } else {
                $digits[$i] = $temp;
                break;
            }
        }
        // 若新数组首位是0，是由于原来首位是9，由于前一位进1，9+1=10后，首位变成0了，此时需要在前面补上一个1，数组长度由n变成n+1。
        // 若新数组首位不是0，则无需多余处理，直接返回即可，数组长度还是n。
        if ($digits[0] == 0) {
            return array_merge([1], $digits);
        } else {
            return $digits;
        }

    }
}
```


```php
class Solution {

    /**
     * @param Integer[] $digits
     * @return Integer[]
     */
    function plusOne($digits) {
        $length = sizeof($digits);
        $ans = 0;
        $add = 1;
        for ($i = $length - 1; $i>=0; $i--) {
            $temp = $digits[$i] + $add;
            if ($temp >= 10) {
                $digits[$i] = $temp - 10;
                $add = 1;
            } else {
                $digits[$i] = $temp;
                $add = 0;
            }
        }
        if ($digits[0] == 0) {
            return array_merge([1], $digits);
        } else {
            return $digits;
        }

    }
}
```
