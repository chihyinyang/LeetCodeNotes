# [Roman to Integer](https://leetcode.com/problems/roman-to-integer/description/)

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given a roman numeral, convert it to an integer.



### 📌 My Solution

```
func romanToInt(_ s: String) -> Int {
            
            let arr = Array(s).map{ String($0) }
            var index = arr.count - 1
            var counter = 0
            
            while arr.indices.contains(index) {
                
                if arr.indices.contains(index - 1) {
                    let temp = arr[index - 1] + arr[index]
                    if temp == "IV" {
                        counter += 4
                        index -= 1
                    } else if temp == "IX"{
                        counter += 9
                        index -= 1
                    } else if temp == "XL"{
                        counter += 40
                        index -= 1
                    } else if temp == "XC"{
                        counter += 90
                        index -= 1
                    } else if temp == "CD"{
                        counter += 400
                        index -= 1
                    } else if temp == "CM"{
                        counter += 900
                        index -= 1
                    }  else if arr[index] == "I"{
                        counter += 1
                    } else if arr[index] == "V"{
                        counter += 5
                    } else if arr[index] == "X"{
                        counter += 10
                    } else if arr[index] == "L"{
                        counter += 50
                    } else if arr[index] == "C"{
                        counter += 100
                    } else if arr[index] == "D"{
                        counter += 500
                    } else if arr[index] == "M"{
                        counter += 1000
                    }
                } else {
                    if arr[index] == "I"{
                       counter += 1
                   } else if arr[index] == "V"{
                       counter += 5
                   } else if arr[index] == "X"{
                       counter += 10
                   } else if arr[index] == "L"{
                       counter += 50
                   } else if arr[index] == "C"{
                       counter += 100
                   } else if arr[index] == "D"{
                       counter += 500
                   } else if arr[index] == "M"{
                       counter += 1000
                   }
                }
                index -= 1
            }
            return counter
        }
```
