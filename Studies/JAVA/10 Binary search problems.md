

***Ceiling of number***
		 **The least integer number greater than or equal to the Target**.

> 			*==**Return Start**==*

***Flooring of number***

> 		**The greatest integer number Lesser than or Equal to Target**

> 			*==**Return end***==
TO check
```java
class Solution {

    public int[] searchRange(int[] nums, int target) {

        int ans[] = {-1,-1};

        ans[0] = search(nums, target, true);

        if(ans[0] != -1)

            ans[1] = search(nums, target, false);

        return ans;

    }

    int search(int[] nums, int target,boolean firstindex){

        int ans = -1;
        int start = 0;
        int end = nums.length - 1;
        while(start<=end){
            int mid = start + (end-  start) / 2;
            if(target < nums[mid])
                end = mid - 1;
            else if(target > nums[mid])
                start = mid + 1;
            else{
                ans = mid;
                if(firstindex){
                    end = mid - 1;
                } else{
                    start = mid + 1;
                }
            }
        }
        return ans;
    }
}

```
