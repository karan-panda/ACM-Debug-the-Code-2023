## Smallest missing positive using SET
Given an unsorted integer array nums, return the smallest missing positive integer. 
You must implement an algorithm that runs in O(n) time and uses O(1) auxiliary space. 

Example:
```
Input: nums = [1,2,0] 
Output: 3 
Explanation: The numbers in the range [1,2] are all in the array. 
```
```
Input: nums = [3,4,-1,1] 
Output: 2 
Explanation: 1 is in the array but 2 is missing. 
```
```
Input: nums = [7,8,9,11,12] 
Output: 1 
Explanation: The smallest positive integer 1 is missing. 
```

Constraints:
-	1 <= nums.length <= 105 
-	-231 <= nums[i] <= 231 - 1 
 
### Bug code
```cpp
class Solution { 
public: 
 int firstMissingPositive(vector<int>& nums) { 
 int i; 
 set<int> st; 
 for(i=0;i<=nums.size();i++) st.insert(nums[i]); 
 
 i=0; 
 while(i<=st.size()){ 
 if(st.find(i)==st.end())i++; 
 else return i; 
 } 
 return i; 
 } 
}; 
```