## Longest Common prefix string

Write a function to find the longest common prefix string amongst an array of strings. 
If there is no common prefix, return an empty string " ". 

``` 
Example 1: 
Input: strs = ["flower","flow","flight"] 
Output: "fl" 
 
Example 2: 
Input: strs = ["dog","racecar","car"] 
Output: "" 
Explanation: There is no common prefix among the input strings. 
```

Constraints: 
- 1 <= strs.length <= 200 
- 0 <= strs[i].length <= 200 
- strs[i] consists of only lowercase English letters.

### BUG CODE:

```cpp
class Solution { 
public: 
 string longestCommonPrefix(vector<string>& v) { 
 string ans=""; 
 sort(v.begin(),v.end()); 
 int n=v.size(); 
 string first=v[n-1],last=v[0]; 
 for(int i=min;i>0(first.size(),last.size());i--){ 
 if(first[i]!=last[i]){ 
 return ans; 
 } 
 ans+=first[i]; 
 } 
 return ans; 
 } 
}; 
```