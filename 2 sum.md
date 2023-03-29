
# [2 sum](https://leetcode.com/problems/two-sum/description/)

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have ***exactly* one solution**, and you may not use the *same*element twice.

You can return the answer in any order.

### 📌 My Solution

```
func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
    let sorted = nums.sorted()
    for (aIndex, number) in sorted.enumerated() {
        var bIndex = aIndex
        
        while sorted.indices.contains(bIndex) && number + sorted[bIndex] < target {
            bIndex += 1
        }
        
        if sorted.indices.contains(bIndex),
           number + sorted[bIndex] == target {
            let a = number
            let b = sorted[bIndex]
            let aIndexInNums = nums.firstIndex{ $0 == a }
            let bIndexInNums = nums.lastIndex{ $0 == b }
            
            if let aIndexInNums = aIndexInNums,
               let bIndexInNums = bIndexInNums {
                return [aIndexInNums, bIndexInNums]
            }
        }
    }
    return []
}
```

> __Note__

1. sorted the array (this is important)
2. first number plus second one, check if is bigger than target. If it is bigger, then we can skip this round, start next round, which is second number plus the third one, vice versa.
3. get index using both `firstIndex` and `lastIndex`, because once we get the number we want, we have to get the order from the original array, and prevent from the number is duplicated, so we get the firstIndex and lastIndex.
