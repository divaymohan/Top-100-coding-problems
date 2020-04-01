[All Problems](../README.md)
## Problem:- 
>Given two strings s and t , write a function to determine if t is an anagram of s.

>### Example 1:
> #### Input: s = "anagram", t = "nagaram"
> #### Output: true

> ### Example 2:
> #### Input: s = "rat", t = "car"
> #### Output: false

> ### Note:
>You may assume the string contains only lowercase alphabets.

## Solution:-

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if(s.size() != t.size()){
            return false;
        }
        int map[26] = {0};
        for(int i=0;i<s.size();i++){
            map[s[i]-'a']++;
            map[t[i]-'a']--;
        }
        for(int i=0;i<26;i++){
            if(map[i]!=0)
                return false;
        }
        return true;
    }
};

```
