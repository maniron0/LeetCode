Rotate Array

Given an array, rotate the array to the right by k steps, where k is non-negative.

Example 1:

```python
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

Example 2:

```python
Input: nums = [-1,-100,3,99], k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

Solution:

```python
class Solution(object):
    def rotate(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        """
        Classical 3-step array rotation:
        1) reverse the first n - k elements
        2) reverse the rest of them
        3) reverse the entire array
        """
        if k == 0:
            return
        
        k, end = k % len(nums), len(nums)-1
        self.reverse(nums,0,end - k)
        self.reverse(nums,end - k + 1, end)
        self.reverse(nums,0,end)
        
    def reverse(self,arr,start,end):
        while start<end:
            arr[start],arr[end] = arr[end],arr[start]
            start,end = start +1, end -1
```
