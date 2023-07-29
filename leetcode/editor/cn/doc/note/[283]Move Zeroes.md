## Move Zeroes

Given an integer array `nums`, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

### 普通双指针

删去重复的之后接着指针的位置继续填充0就可以了

```c++
if (nums.size() > 1) {
    for (fastIndex = 0; fastIndex <= nums.size() - 1; fastIndex++) {
        if (nums[fastIndex] != 0) {
            nums[slowIndex++] = nums[fastIndex];
        }
    }
    for (int i = slowIndex; i <= fastIndex - 1; i++) {
        nums[i] = 0;
    }
}
```

### 前后交换

把前面的0换到后面

都从前往后，slowIndex指向每个0，fastIndex指向非零的

```c++
int slowIndex = 0;
int fastIndex = 0;

while (fastIndex < nums.size()) {
    if (nums[fastIndex] != 0) {
        swap(nums[slowIndex], nums[fastIndex]);
        slowIndex++;
    }
    fastIndex++;
}
```

