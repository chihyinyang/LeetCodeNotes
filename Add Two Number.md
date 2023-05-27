# [Add Two Number](https://leetcode.com/problems/add-two-numbers/description/)

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

### 📌 My Solution

```
func removeDuplicates(_ nums: inout [Int]) -> Int {
    var temp = 0
    func addTwoNumbers(_ l1: ListNode?, _ l2: ListNode?) -> ListNode? {
        if l1 == nil && l2 == nil && temp == 0 { return nil }
        let sum = (l1?.val ?? 0) + (l2?.val ?? 0) + temp
        dig = sum / 10
        return .init(sum % 10, addTwoNumbers(l1?.next, l2?.next))
    }
 }
```
Runtime: 40ms (beats 65.17%) | Memory: 14.1 MB (beats 41.29%)

1. ListNode: a "list node" typically refers to a node in a linked list data structure. A linked list is a linear data structure where each element, called a node, contains a value and a reference (or link) to the next node in the list.

for example, this is how to make a listNode:
```
public class ListNode {
    public var val: Int
    public var next: ListNode?
    public init() { self.val = 0; self.next = nil; }
    public init(_ val: Int) { self.val = val; self.next = nil; }
    public init(_ val: Int, _ next: ListNode?) { self.val = val; self.next = next; }
}
```
