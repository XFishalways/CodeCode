## [34]Find First and Last Position of Element in Sorted Array

Given an array of integers `nums` sorted in non-decreasing order, find the starting and ending position of a given `target` value.

If `target` is not found in the array, return `[-1, -1]`.

You must write an algorithm with `O(log n)` runtime complexity.

不单调递增数组求左右边界

### 左边界

```
if (nums[mid] == target) {
    ans = mid;
    right = mid - 1;
}
```
while循环外部int ans

相等时继续尝试，若左侧无相等的ans也就不变，有相等的值继续更新

### 右边界

```
if (nums[mid] == target) {
    ans = mid;
    left = mid + 1;
}
```
右边界同理
