
### 🔗Question link [https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

### 📕Content

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have ***exactly* one solution**, and you may not use the *same*element twice.

You can return the answer in any order.

### 📌My Solution

```
func twoSum(_ nums: [Int], _ target: Int) -> [Int] {
		// 先把nums從小到大排序
    let sorted = nums.sorted()
		// 從小的開始for-in
    for (aIndex, number) in sorted.enumerated() {
        var bIndex = aIndex
        // 用while迴圈，加移動b的位子
				// (確保加1後的b index是存在的) && (兩個數字相加 小於目標數字)
        while (sorted.indices.contains(bIndex)) && (number + sorted[bIndex] < target) {
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
