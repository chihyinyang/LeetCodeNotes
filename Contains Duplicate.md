# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.



### 📌 My Solution

```
func containsDuplicate(_ nums: [Int]) -> Bool {
        let sorted = nums.sorted()
    let count = sorted.count
    for (index, num) in sorted.enumerated() {
        if (index + 1) < count,
           sorted[index] == sorted[index + 1] {
            return true
        }
    }
    return false
    }
```

```
func containsDuplicate(_ nums: [Int]) -> Bool {
        nums.count != Set(nums).count
    }
```
