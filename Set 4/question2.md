## Product except self
Given an array of integers 'nums', calculate a new array 'answer' where each element 'answer[i]' is equal to the product of all elements in 'nums' except for 'nums[i]'. It is guaranteed that the product of any subset of 'nums' will not exceed a 32-bit integer.
You must write an algorithm that runs in O(n) time and without using the division operation.
```
Example 1:
Input: nums = [1,2,3,4]
Output: [24,12,8,6]

Example 2:
Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
 ```
Constraints:
- 2 <= nums.length <= 105
- -30 <= nums[i] <= 30
The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

***Note: Can you solve the problem in O(1) extra space complexity? (The output array does not count as extra space for space complexity analysis.)***

BUG CODE:

```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        vector<int> ans;
        int prod = 1, flag = 1;

        for(auto el : nums){
            if(el == 0){
                flag = 1;
                break;
            } 
            else prod += el;
        }

        for(int i = 0; i < nums.length(); i++){
            if(nums[i] == 0 && flag == 0) ans.insert(prod);
            else if(flag >= 1 && nums[i] != 0) ans.insert(0);
            else ans.insert();
        }
        return ans;
    }
};

```
