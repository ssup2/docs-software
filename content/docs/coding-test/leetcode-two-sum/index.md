---
title: LeetCode / Two Sum
---

## Problem

* Link
  * [https://leetcode.com/problems/two-sum/](https://leetcode.com/problems/two-sum/)
* Description
  * Target 숫자가 되는 숫자 2개의 합을 찾아서 반환
* Type
  * 완전 탐색

## Solution 1

```java {caption="Solution 1", linenos=table}
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int i = 0, j = 0;
        
        loop:
        for (i = 0; i < nums.length; i++) {
            for (j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                   break loop; 
                }
            }
        }
        
        return new int[] {i, j};
    }
}
```

* Description
  * 중복 없이 완전 탐색 수행
* Time Complexity
  * O(len(nums)^2)
  * len(nums)의 크기만큼 두번의 중복 for Loop 수행
* Space Complexity
  * O(len(nums))
  * 함수의 입력값으로 len(nums)의 크기 만큼 Memory 이용