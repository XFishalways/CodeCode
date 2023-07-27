## Search Insert Position

Given a sorted array of distinct integers and a `target` value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

简单的二分查找

根据其他return要求 在算法中添加适当判断&输出 不必完全将算法和实际逻辑判断分离开

注意二分查找的终止状态 两种不同情况（最后一步是left或right变化） 但结果都是left>right