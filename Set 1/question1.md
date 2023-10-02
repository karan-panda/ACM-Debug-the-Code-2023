## Are Parenthesis Valid?  

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.    				
An input string is valid if: 
1.	Open brackets must be closed by the same type of brackets. 
2.	Open brackets must be closed in the correct order. 
3.	Every close bracket has a corresponding open bracket of the same type. 

Eg. 
```
Input: s = "()" 
Output: true 
```

```
Input: s = "()[]{}" 
Output: true 
```

```
Input: s = "(]" 
Output: false 
```

Constraints: 
- 1 <= s.length <= 104 
- s consists of parentheses only '()[]{}'

### Bug code:

```cpp
class Solution { 
    public boolean isValid(String s) { 
        Stack<Character> stack = new Stack<Character>();  
        for (char c : s.toCharArray()) {  
            if (c != '(')  
                stack.push(')');  
            else if (c == '{') 
                stack.push('}');  
            else if (c == '[')  
                stack.push(']');  
            else if (stack.isEmpty() && stack.pop() != c)  
               
                return false; 
        } 
        return stack.isEmpty(); 
    } 
} 
```
