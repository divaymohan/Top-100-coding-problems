[All Problems](../README.md)
## Problem:- 
>Given an unsorted array A of size N of non-negative integers, find a continuous sub-array which adds to a given number S.
>## Input:
>The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case consists of two lines. The first line of each test case is N and S, where N is the size of array and S is the sum. The second line of each test case contains N space separated integers denoting the array elements.
>## Output:
>For each testcase, in a new line, print the starting and ending positions(1 indexing) of first such occuring subarray from the left if sum equals to subarray, else print -1.

## Solution(c):-

```c
int main() {
	int t;
	scanf("%d",&t);
	while(t--){
	    int n;
	    scanf("%d",&n);
	    int sum;
	    scanf("%d",&sum);
	    int in[n];
	    for(int i=0;i<n;i++){
	        scanf("%d",&in[i]);
	    }
	    int i=0;
	    int j=0;
	    while(sum!=0 && i<n && j<=n){
	        if(sum>0){
	            sum = sum-in[j];
	            j++;
	        }
	        else{
	            sum = sum+in[i];
	            i++;
	        }
	    }
	    if(sum==0){
	        printf("%d %d\n",i+1,j);
	    }
	    else{
	        printf("-1\n");
	    }
	    
	}
	return 0;
}


```

## Solution(cpp):-

```cpp
using namespace std;
#define ll long long

int main() {
	int t;
	cin>>t;
	while(t--){
	    ll n,sum;
	    cin>>n;
	    cin>>sum;
	    ll *arr = new ll[n];
	    for(ll i=0;i<n;i++){
	        cin>>arr[i];
	    }
	    ll start = 0;
	    ll end = 0;
	    ll cusum = arr[0];
	    int sts = 0;
	    while(end < n && sts != 1){
	        if(sum>cusum){
	            cusum += arr[++end];
	            if(cusum==sum){
	                cout<<start+1<<" "<<end+1<<endl;
	               sts = 1;
	            }
	        }
	        else if(sum<cusum){
	            cusum -= arr[start++];
	            if(cusum==sum){
	                cout<<start+1<<" "<<end+1<<endl;
	                sts = 1;  
	            }
	        }
	    }
	    if(sts==0){
	        cout<<-1<<endl;
	    }
	  
	}
	
	return 0;
}
```
