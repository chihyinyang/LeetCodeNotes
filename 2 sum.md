
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
            var aIndexInNums: Int? = nil
            var bIndexInNums: Int? = nil
            
            for (numIndex, number) in nums.enumerated() {
                if aIndexInNums == nil,
                   number == a {
                    aIndexInNums = numIndex
                    
                } else if bIndexInNums == nil,
                          number == b {
                    bIndexInNums = numIndex
                }
                
                if let aIndexInNums = aIndexInNums,
                   let bIndexInNums = bIndexInNums {
                    return [aIndexInNums, bIndexInNums]
                }
            }
        }
    }
    return []
}
```
Runtime: 67ms (beats 39.53%) | Memory: 14.3 MB (beats 74.29%)

1. sorted the array (this is important)
2. first number plus second one, check if is bigger than target. If it is bigger, then we can skip this round, start next round, which is second number plus the third one, vice versa.
