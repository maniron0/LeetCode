Single Number

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

Example 1:

```python
Input: nums = [2,2,1]
Output: 1
```

Example 2:

```python
Input: nums = [4,1,2,1,2]
Output: 4
```

Example 3:

```python
Input: nums = [1]
Output: 1
```

Solution:

```python
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        for i in range(1,len(nums)):
            nums[0] ^= nums[i]
        return nums[0]
```
