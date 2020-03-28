[All Problems](../README.md)
## Problem:- 
>Given two arrays `A1[]` and `A2[]` of size `N` and `M` respectively. The task is to sort A1 in such a way that the relative order among the elements will be same as those in `A2`. For the elements not present in `A2`, append them at last in sorted order. It is also given that the number of elements in `A2[]` are smaller than or equal to number of elements in `A1[]` and `A2[]` has all distinct elements.
`Note: Expected time complexity is O(N log(N))`.
>## Input:
>First line of input contains number of testcases. For each testcase, first line of input contains length of arrays `N` and `M` and next two line contains `N` and `M` elements respectively.
>## Output: 
>Print the relatively sorted array.

## Solution:-

```cpp
#include <iostream>
#include <bits/stdc++.h>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--){
	    int n;
	    cin>>n;
	    int m;
	    cin>>m;
	    vector<int> arr1;
	    vector<int> arr2;
	    int max=-99999;
	    for(int i=0;i<n;i++){
	        int temp;
	        cin>>temp;
	        if(max<temp){
	            max = temp;
	        }
	        arr1.push_back(temp);
	    }
	    for(int i=0;i<m;i++){
	        int temp;
	        cin>>temp;
	        arr2.push_back(temp);
	    }
	    int hashMap[max+1]={0};
	    for(int i=0;i<n;i++){
            hashMap[arr1[i]]++;
        }
        int k = 0;
        for(int i=0;i<m;i++){
            
            if(hashMap[arr2[i]]){
                for(int j=0;j<hashMap[arr2[i]];j++){
                    arr1[k++]=arr2[i];
                    hashMap[arr2[i]];
                }
                hashMap[arr2[i]]=0;
                
            }
        }
        for(int i=0;i<=max;i++){
            if(hashMap[i]){
                for(int j=0;j<hashMap[i];j++){
                    arr1[k++] = i;
                   
                }
                 hashMap[i]=0;
            }
        }
        for(int i=0;i<n;i++){
            cout<<arr1[i]<<" ";
        }
        cout<<endl;
	    
	}
	return 0;
}
```
