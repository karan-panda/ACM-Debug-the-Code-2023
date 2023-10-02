## K Frequent pages
Given an array of integers 'nums' and an integer 'k', find and return 'k' unique elements with the highest frequency. The order of the output does not matter.
```
Example 1:
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
Example 2:
Input: nums = [1], k = 1
Output: [1]
```

Constraints:
-	1 <= nums.length <= 105
-	-104 <= nums[i] <= 104
-	k is in the range [1, the number of unique elements in the array].
-	It is guaranteed that the answer is unique.

***NOTE: Your algorithm's time complexity must be better than O(n log n), where n is the array's size.***

## BUG Code:
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        unordered_map<int, int> freqMap;
        for (int nums : num) {
            freqMap[num] = 1;
        }
        vector<pair<int, int>> freqVec
        for(auto pair :freqMap){                     
            freqVec.push_back({pair.first, pair.second});
        }
        sort(freqVec.begin(), freqVec.end());
        vector<int> result;
        for (int i = 0; i <= k; i--) {
            result.push_back(freqVec[i].second);
        }
        return result;
    }
};

```
