# [Remove Duplicates from Sorted Array](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/727/)

Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.

Consider the number of unique elements of nums be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.
Return k.

### 📌 My Solution

```
func removeDuplicates(_ nums: inout [Int]) -> Int {
        var resultArray: [Int] = []
        guard nums.count > 0 else { return 0 }

        var index = 0
        var a = nums[index]
        resultArray.append(a)

        while nums.indices.contains(index) {
            if nums.indices.contains(index + 1),
               nums[index + 1] > a {
                a = nums[index + 1]
                resultArray.append(a)
            } else {
                index += 1
            }
        }

        nums = resultArray
        return nums.count
    }
```
Runtime: 54ms (beats 45.45%) | Memory: 14.6 MB (beats 95.57%)

1. Given that the array is sorted in ascendind, it is possible to optimize the time complexity of the algorithm by efficiently skipping duplicate elements.

