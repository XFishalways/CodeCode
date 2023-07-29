## Remove Element

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in nums in-place. The order of the elements may be changed. Then return the number of elements in `nums` which are not equal to `val`.

Consider the number of elements in `nums` which are not equal to `val` be `k`, to get accepted, you need to do the following things:

- Change the array `nums` such that the first `k` elements of `nums` contain the elements which are not equal to `val`. The remaining elements of `nums` are not important as well as the size of `nums`. 
- Return `k`.

## 双指针

暴力肯定是 O(n^2)
双指针一个定位最远的错误点，一个定位最近的修改位
```c++
int slowIndex = 0;
for (int fastIndex = 0; fastIndex <= nums.size() - 1; fastIndex++) {
    if (nums[fastIndex] != val) {
        nums[slowIndex++] = nums[fastIndex];
    }
}
return slowIndex;
```

## 拓展 —— 相向双指针

```c++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int leftIndex = 0;
        int rightIndex = nums.size() - 1;
        while (leftIndex <= rightIndex) {
            // 找左边等于val的元素
            while (leftIndex <= rightIndex && nums[leftIndex] != val){
                ++leftIndex;
            }
            // 找右边不等于val的元素
            while (leftIndex <= rightIndex && nums[rightIndex] == val) {
                -- rightIndex;
            }
            // 将右边不等于val的元素覆盖左边等于val的元素
            if (leftIndex < rightIndex) {
                nums[leftIndex++] = nums[rightIndex--];
            }
        }
        return leftIndex;   // leftIndex一定指向了最终数组末尾的下一个元素
    }
};
```

改变了元素相对位置，但能确保移动最少元素