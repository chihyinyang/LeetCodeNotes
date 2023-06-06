# [Palindrome Number](https://leetcode.com/problems/palindrome-number/description/)

Given an integer x, return true if x is a palindrome, and false otherwise.

### 📌 My Solution

```
func isPalindrome(_ x: Int) -> Bool {
        let str = String(x)
        let halfCount: Int = Int(ceil(Float(str.count / 2)))
        
        let rHalf = str.prefix(halfCount)
        let lHalf = String(str.suffix(halfCount).reversed())
        
        return rHalf == lHalf
    }
```

Solution by Soft-n-Wet

```
func isPalindrome(_ x: Int) -> Bool {
        return String(String(x).reversed()) == String(x)
    }
```
