## Valid Parentheses
- Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:
- Open brackets must be closed by the same type of brackets.
- Open brackets must be closed in the correct order.
- Every close bracket has a corresponding open bracket of the same type.
 

### Example 1:

Input: s = "()"

Output: true

### Example 2:

Input: s = "()[]{}"

Output: true

### Example 3:

Input: s = "(]"

Output: false

### Example 4:

Input: s = "([])"

Output: true

### Example 5:

Input: s = "([)]"

Output: false

## Solution:
```py
def isValid(s: str) -> bool:
    if len(s) < 2:
        return False
    
    parentheses = {")":"(", "}":"{", "]":"["}
    stack = []
    
    for i in s:
        if i in ["[","{","("]:
            stack.append(i)
        elif i in ["]","}",")"]:
            if len(stack) <= 0:
                return False
            top = stack.pop()
            if parentheses[i] != top:
                return False
    return not stack
```