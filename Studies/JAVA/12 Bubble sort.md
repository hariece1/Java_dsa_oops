x
**Space complexity** 
			O(1)       --Constant -- no extra space required

**Time complexity** 
			Best case      -  ==O(n)==        -- Arrays is sorted
			Worst case    - ==O(n^2)    ==-- Sorted in opposite (descending)

**Note :**
		***When j never swaps for a particular value of i then it means the array is sorted***


**1st step**

![[Pasted image 20240125120120.png]]

2n step
1 3 4 2 5
1 3 2 4 5

3rd step
1 3 2 4 5
1 2 3 4 5



***With first pass/step the largest element came to end***

***With second pass/step the second largest element is 2nd from last index***
