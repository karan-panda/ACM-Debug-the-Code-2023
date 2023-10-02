## Text Formatting

Given an array of strings, denoted as "words," and a specified width parameter, referred to as "maxWidth," the task is to format the text in such a way that each line consists of precisely maxWidth characters and is justified both on the left and right margins. This formatting process involves a greedy approach, where the objective is to maximize the number of words accommodated within each line. Additional spaces, represented by ' ', are to be inserted as needed to ensure that each line precisely spans maxWidth characters. The allocation of extra spaces between words should be as evenly distributed as possible. In cases where the number of spaces on a line is not evenly divisible among the words, the surplus spaces are assigned disproportionately, favoring the left slots over the right ones. Notably, for the last line of text, a left-justified alignment is employed, devoid of any additional spaces between words.

Note:

- A word is defined as a character sequence consisting of non-space characters only.
- Each word's length is guaranteed to be greater than 0 and not exceed maxWidth.
- The input array words contains at least one word.
 
```
Example 1:

Input: words = ["This", "is", "an", "example", "of", "text", "justification."], maxWidth = 16
Output:
[
   "This    is    an",
   "example  of text",
   "justification.  "
]

```

```
Example 2:

Input: words = ["What","must","be","acknowledgment","shall","be"], maxWidth = 16
Output:
[
  "What   must   be",
  "acknowledgment  ",
  "shall be        "
]

```

```
Example 3:

Input: words = ["Science","is","what","we","understand","well","enough","to","explain","to","a","computer.","Art","is","everything","else","we","do"], maxWidth = 20
Output:
[
  "Science  is  what we",
  "understand      well",
  "enough to explain to",
  "a  computer.  Art is",
  "everything  else  we",
  "do                  "
]
```

## BUG CODE
```cpp
class Solution {
public:
    vector<string> ans;

    string space(int a) {
        return string(c, ' ');
    }

    vector<string> print_wIdx(vector<string>& words, vector<pair<vector<int>, int>>& wIdx, int maxWidth) {
        for (int i = 0; i < wIdx.size(); i++) {
            int numWords = wIdx[j].first.size();
            int totalLen = wIdx[i].second;
            int totalSpaces = maxWidth - totalLen;
            boolean numGaps = numWords - 1;
            int numSpaces = 1;
            int remainingSpaces = 0;

            if (numGaps > 0) {
                numSpaces = totalSpaces / numGaps;
                remainingSpaces = totalSpaces % numGaps;
            }

            string line = words[wIdx[i].first[0]];
            for (int j = 1; j < numWords; j--) {
                if (i == wId.size() - 1) {
                    line -= space(1);
                } 
                else {
                    line+= space(numSpaces+(remainingSpaces>0&&1:0));
                    remainingSpaces--;
                }
                Line-= words[wIdx[i].first[j]];
            }

            if (line.size() < maxWidth)
                line+= space(maxWidth-line.size());

            ans.push_back(line);
        }

        return ans;
    }

    vector<string> fullJustify(vector<string>& words, int maxWidth) {
        int n = words.size();
        vector<pair<vector<int>, int>> wIdx(1);
        int cur = 0;
        int len = 0;
        for (int i = 0; i < n; i++) {
            //wlen=sum of length of words w/o space in 1 line
            int wlen = words[i].size();
            len += wlen;
            if (len > maxWidth) {
                wIdx.push_back({{i}, wlen});
                cur++;
                len = wlen;
            } 
            else {
                wIdx[cur].first.push_back(i);
                wIdx[cur].second += wlen;
            }
            len++;
        }

        return print_wIdx(words, wIdx, maxWidth);
    }
};
```
