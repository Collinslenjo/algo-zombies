## Valid Anagram
- Given two strings s and t, return true if t is an anagram of s, and false otherwise.

 
### Example 1:

Input: s = "anagram", t = "nagaram"

Output: true

### Example 2:

Input: s = "rat", t = "car"

Output: false

## Solutions
```py
def isAnagram(s: str, t: str) -> bool:
    if len(s) != len(t):
        return False
    
    char_count = {}
    
    for j in s:
        char_count[j] = char_count.get(j, 0) + 1

    for i in t:
        if i not in char_count:
            return False
        char_count[i] -= 1
        if char_count[i] < 0:
            return False

    return True

```

```py
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        setA = self.array_helper(s)
        setB = self.array_helper(t)
        
        print(s,t)
        if len(setA) != len(setB):
            return False
        else:
            return bool(setA == setB)

    def array_helper(self, string):
        setA = {}
        for i in string:
            if i in setA.keys():
                setA[i] = setA[i] + 1
            else:
                setA[i] = 1
        return setA
```