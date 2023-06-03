
# [Longest Common Prefix]([https://leetcode.com/problems/add-two-numbers/description/](https://leetcode.com/problems/longest-common-prefix/description/))

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

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
