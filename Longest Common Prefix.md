
# [Add Two Number](https://leetcode.com/problems/add-two-numbers/description/)

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

### 📌 My Solution

```
func longestCommonPrefix(_ strs: [String]) -> String {
    let minCount = strs.map{ $0.count }.min()!
    guard minCount > 0 else { return "" }
    guard strs.count != 1 else { return strs.first! }
    for count in stride(from: minCount, to: 0, by: -1) {
        let prefixs = strs.map{ $0.prefix(count) }
        
        var index = 1
        var hasDiff = false
        while !hasDiff {
            hasDiff = prefixs[0] != prefixs[index]
            index += 1
            if index >= prefixs.count {
                break
            }
        }
        
        if !hasDiff {
            return String(strs.first!.prefix(count))
        }
    }
    return ""
}
```
solution from AsahiOcean
```
class Solution {
    func longestCommonPrefix(_ strs: [String]) -> String {
        
        if strs.isEmpty { return "" }
        var common = strs[0]
        
        for ch in strs {
            while !ch.hasPrefix(common) {
                common = String(common.dropLast())
            }
        }
        return common
    }
}
```
