## Two Sum


Given an integer array `nums` and an integer `target`, please find two integers in the array that sum up to the target value and return their array indices.

### 三种map
- std::unordered_map 底层实现为哈希表
- std::map & std::multimap 底层实现为红黑树

### 思路

BF: O(n^2)

no need to place key in order，using unordered map  

(key, value) = (target value, index) 

