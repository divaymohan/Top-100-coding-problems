[All Problems](../README.md)
## Problem:- 
>Given a non-empty array of integers, every element appears twice except for one. Find that single one.

> ### Note:
>Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

> ### Example 1:
> #### Input: [2,2,1]
> #### Output: 1

> ### Example 2:
> #### Input: [4,1,2,1,2]
> #### Output: 4



## Solution 1:-

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int sol=-1;
        std::unordered_map<int,int> umap;
        for(auto i:nums){
            std::unordered_map<int,int>::iterator it = umap.find(i);
            if(it != umap.end()){
                it->second++;
            }
            else{
                umap.insert(std::make_pair(i,1));
            }
        
        }
        for(auto i:umap){
            if(i.second==1){
                sol = i.first;
            }
        }
        return sol;
        
        
    }
};

```
## Solution 2:-
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int solution=0;
        for(const auto n:nums)
            solution^=n;
        return solution;
        
    }
};
```