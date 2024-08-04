*Array should be sorted (Ascending or Descending)*

**Steps :**
	 1 . Find the middle element
	 2 . Check :
			 If target > middle -- search right
			 if target < middle -- search left
	3 . If middle == target           -- search element found

**Formulas:**
$$
				mid = start + (end - start)/ 2     
$$

**Time complexity :**
		==***Best case : O(1)***==
		==***Worst case : O(log n)***==

**If *start > end* Element not found**



**Order agnostic binary search**
> 		
> 		***Start > end       ---Descending order***
> 		***Start < end       ---Ascending order***

```java
public class BinarySearch {

    public static void main(String[] args) {
        int[] arr = {-18, -12, -4, 0, 2, 3, 4, 15, 16, 18, 22, 45, 89};
        int target = 22;
        int ans = binarySearch(arr, target);
        System.out.println(ans);
    }

    // return the index
    // return -1 if it does not exist
    static int binarySearch(int[] arr, int target) {
        int start = 0;
        int end = arr.length - 1;

        while(start <= end) {
            // find the middle element
//            int mid = (start + end) / 2; // might be possible that (start + end) exceeds the range of int in java
            int mid = start + (end - start) / 2;

            if (target < arr[mid]) {
                end = mid - 1;
            } else if (target > arr[mid]) {
                start = mid + 1;
            } else {
                // ans found
                return mid;
            }
        }
        return -1;
    }
}
```