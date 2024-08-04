
Steps: 
	1. Selecting the maximum number in the array.
	2. Swapping the maximum number to last index.

Time complexity - 
$$
						O(n^2)
$$

```java
import java.util.Arrays;  
public class selection {  
    public static void main(String[] args) {  
        int[] nums = {2, 4, 23, 6, 8, 5};  
        seletc(nums);  
    }  
  
    static void seletc(int[] nums) {  
        for (int i = 0; i < nums.length; i++) {  
            int last = nums.length - i - 1;  
            int max = getmax(nums,last);  
            swap(nums,max,last);  
        }  
        System.out.println(Arrays.toString(nums));  
    }  
    static void swap(int[] nums,int first,int second){  
        int temp = nums[first];  
        nums[first] = nums[second];  
        nums[second] = temp;  
    }  
    static int getmax(int[] nums,int last){  
        int max = 0;  
        int maxindex = 0;  
        for(int i =0;i<=last;i++){  
            if(nums[i]> max){  
                max = nums[i];  
                maxindex = i;  
            }  
        }  
        return maxindex;  
    }  
}
```
find all index
```java
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		int[] nums = {1,2,3,4,4,5,6,7,8};
		int target = 4;
		int index =0;
		ArrayList<Integer> list = new ArrayList<>();
		indexnu(nums,target,index,list);
		for(int i=0;i<list.size();i++){
		    System.out.print(list.get(i)+",");
		}
		
	}
	static  ArrayList<Integer> indexnu(int[] nums,int target,int index,ArrayList<Integer> list){
	    if(index == nums.length){
	        return list;
	    }
	    if(target == nums[index]){
	        list.add(index);
	    }
	    return indexnu(nums,target,index + 1,list);
	}
}

```