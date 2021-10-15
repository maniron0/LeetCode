Move Zeroes

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

Example 1:

```python
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

Example 2:

```python
Input: nums = [0]
Output: [0]
```

Solution:

```python
class Solution(object):
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        z = 0
        for i in range(0,len(nums)):
            if nums[i] != 0 and nums[z] == 0:
                nums[i], nums[z] = nums[z], nums[i]
                
            if nums[z] != 0:
                z += 1
```
