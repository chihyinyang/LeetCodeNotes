# [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

### 📌 My Solution

```
func isValid(_ s: String) -> Bool {
        let lefts = ["(","[", "{"]
        let rights = [")", "]", "}"]
        var temp: [String] = []

        let arr = Array(s).map{ String($0) }
        for a in arr {
            if lefts.contains(a) {
                if let index = lefts.firstIndex(of: a) {
                    temp.append(rights[index])
                }
            } else if let last = temp.last,
                      last == a {
                temp.removeLast()
            } else {
                return false
            }
        }
        return temp.isEmpty
    }
```
Runtime: 5ms (beats 43.32%) | Memory: 14.4 MB (beats 29.19%)
