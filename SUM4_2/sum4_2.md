[All Problems](../README.md)
## Problem:- 
>Given four lists A, B, C, D of integer values, compute how many tuples (i, j, k, l) there are such that A[i] + B[j] + C[k] + D[l] is zero.

## Solution:-

```cpp
class Solution {
public:
    int fourSumCount(vector<int>& A, vector<int>& B, vector<int>& C, vector<int>& D) {
        long long count = 0;
        int i,j;
        std::unordered_map<int,int> umap;
        for (auto i:A)
	    {
            for(auto j:B){
                int sum = i+j;
                // check if key 'c' exists in the map or not
                std::unordered_map<int,int>::iterator it = umap.find(sum);
                // key already present in the map
                if (it != umap.end()) {
                    it->second++;	// increment map's value for key 'c'
                }
                 // key not found
                else {
                    umap.insert(std::make_pair(sum, 1));
                }   
                
            }
		
	    }
        for (auto i:C)
	    {
            for(auto j:D){
                int sum = i+j;
                // check if key 'c' exists in the map or not
                std::unordered_map<int,int>::iterator it = umap.find((-sum));

                 // key already present in the map
                if (it != umap.end()) {
                    count = count+(it->second);	
                    // increment map's value for key 'count'
                }
            }
	    }
        return count;
    }
};

```
