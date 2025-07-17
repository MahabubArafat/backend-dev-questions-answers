# Loops and Recursion: Write a loop, then transform it into a recursive function (using only immutable structures)

## ELI5 (Explain Like I'm 5)
A loop is like walking up stairs one step at a time. Recursion is like asking a friend to walk up the stairs for you, and that friend asks another friend, and so on, until you reach the top!

---

## Example: Sum of a List
### Using a Loop
```python
def sum_list_loop(nums):
    total = 0
    for n in nums:
        total += n
    return total
```

### Using Recursion (Immutable)
```python
def sum_list_recursive(nums):
    if not nums:
        return 0
    return nums[0] + sum_list_recursive(nums[1:])
```
- No variables are changed; each call works with a new list.

---

## Discussion
- **Loops** are efficient and easy to understand for simple tasks.
- **Recursion** is elegant for problems that break down into similar subproblems (like trees, lists).
- **Immutability** (not changing variables) is common in functional programming and helps avoid bugs.
- Recursion can be less efficient in Python due to call stack limits.

---

## References
- [Python Docs: Recursion](https://docs.python.org/3/tutorial/datastructures.html#functional-programming-tools)
- [GeeksforGeeks: Recursion vs Loop](https://www.geeksforgeeks.org/recursion-vs-iteration/)
- [Stack Overflow: Recursion vs Iteration](https://stackoverflow.com/questions/19794739/recursion-vs-iteration-which-is-better) 