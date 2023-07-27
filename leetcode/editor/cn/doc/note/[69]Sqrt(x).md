## mySqrt

Given a non-negative integer `x`, return the square root of x rounded down to the nearest integer. The returned integer should be non-negative as well.

You must not use any built-in exponent function or operator.

For example, do not use `pow(x, 0.5)` in c++ or `x ** 0.5` in python.

### 数学计算

可以用 `exp` 和 `log` 来计算平方根

因为会直接省略小数部分 所以要再次判断 `ans+1` 和 `ans` 的哪个正确

时间和空间复杂度都是 O(1)

### 二分

$mid^2$ <= x 作为判断条件，整体相当于查找右边界

要特别注意平方的时候要开 `long long`