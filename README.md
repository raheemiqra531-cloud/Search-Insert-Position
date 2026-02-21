Search Insert Position

Problem Description:
Given a sorted array of distinct integers and a target value, return the index if the target is found.  
If not, return the index where it would be inserted in order.  

You must design an algorithm with O(log n) runtime complexity.

Examples:
Example 1:
Input: nums = [1,3,5,6], target = 5  
Output: 2

Example 2:
Input: nums = [1,3,5,6], target = 2  
Output: 1

Example 3:
Input: nums = [1,3,5,6], target = 7  
Output: 4

Example 4:
Input: nums = [1,3,5,6], target = 0  
Output: 0

Approach:
We use Binary Search because the array is sorted:
1. Start with two pointers: `left = 0` and `right = len(nums) - 1`.
2. While `left <= right`:
   - Find the middle index: `mid = (left + right) // 2`.
   - If `nums[mid] == target`, return `mid`.
   - If `nums[mid] < target`, move `left = mid + 1`.
   - Else, move `right = mid - 1`.
3. If the target is not found, return `left`.  
   This is the correct insertion position.
