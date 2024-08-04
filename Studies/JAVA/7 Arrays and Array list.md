		 Primitives are stored in stack --- int char boolean (What are cant be broken down)
***Arrays***
		- Is collection of data type
		- String are immutable and arrays are mutable

int [] rnos = new int[5]
	[[7 Arrays and Array list]]
Int[] rnos - Type of data stored in array (Data Type) and Reference variable (Happens in compile time) Stack
new int[5]- Creating memory in heap memory (Dynamic memory allocation) and size

***Note***
- Arrays objects are in heaps
- Heap objects are not continuous
- DMA

-Arrays in java may not continues depends on JVM

Each particular element in arrays itself a object

```
public static void main (String[] args) {
Scanner in = new Scanner (System. in) ;
int[] arr = new int[5];
arr [0] = 23;
arr [1] = 45;
arr [2] = 233;
arr [3] = 543;
arr [4] = 3;
// [23, 45, 233, 543, 3]
* Pull up for |
System.out.println(arr[5])
// input using for loop
for (int i = 0; i‹ arr.length; i++){
arr[i] = in.nextint()
}
for(int i = 0; i< arr.length; i++){
	System.out.println(arr[i])
}
}
```

Enhanced for loop

```
for (int num : arr){ //for every element in array, print the element
	System.out print(num + ""); // here num represents element of the array
}
```

Internally converts array in to string
```
System.out println(Arrays.toString(arr));
```

###### **2D Arrays**

	Each particular index itself an array

![[Pasted image 20240121210703.png]]

Example program of 2D array

```
int[][] arr = new int[3][2];
System.out. println(arr.length); // no of rows
// input
for (int row = 0; row < arr. length; row++) { // for each col in every row
		for (int col = 0; col < arr[row].length; col++) {
		arr [row] [col] = in.nextInt();
}
for(int row = 0; row ‹ arr. length; row++) { //for each col in every row
	for (int col = 0; col < arr[row]. length; col++)
	System.out.print(arr[row][col] + " ");
}
System.out.println();
```

Enhanced for loop for printing
```
for (int[] a : arr) {
	System.out.println(Arrays.toString(a));
}
```

###### **Arraylist** 

> [!NOTE]
> 	-Size of arrays list is fixed internally
> 	-Arraylist fills by some amoubt, new list created double the size old elements are copied to new list and new elements added to it
> 	-Old list is deleted

![[Pasted image 20240122121518.png]]
```java
package com.kunal;

import java.util.ArrayList;
import java.util.Scanner;

public class ArrayListExample {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        // Syntax
        ArrayList<Integer> list = new ArrayList<>(5);

//        list.add(67);
//        list.add(234);
//        list.add(654);
//        list.add(43);
//        list.add(654);
//        list.add(8765);

//        System.out.println(list.contains(765432));
//        System.out.println(list);
//        list.set(0, 99);
//
//        list.remove(2);
//
//        System.out.println(list);

        // input
        for (int i = 0; i < 5; i++) {
            list.add(in.nextInt());
        }

        // get item at any index
        for (int i = 0; i < 5; i++) {
            System.out.println(list.get(i)); // pass index here, list[index] syntax will not work here
        }

        System.out.println(list);



    }
}
```

###### **Multi Dimensional Array**


```java
import java.util.ArrayList;
import java.util.Scanner;

public class MultiAL {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        ArrayList<ArrayList<Integer>> list = new ArrayList<>();

        // initialisation
        for (int i = 0; i < 3; i++) {
            list.add(new ArrayList<>());
        }

        // add elements
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                list.get(i).add(in.nextInt());
            }
        }

        System.out.println(list);
    }
}
```
Adding row and c in 2d
```java
import java.util.*;  
  
public class Main {  
    public static void main(String args[]) {  
        int n = 5;  
        int m = 5;  
        ArrayList<ArrayList<Integer>> list = new ArrayList<>();  
  
        int counter = 1; // Initialize counter  
  
        for (int i = 0; i < m; i++) {  
            ArrayList<Integer> row = new ArrayList<>();  
            for (int j = 0; j < n; j++) {  
                row.add(counter++); // Add the counter value to the row and increment it  
            }  
            list.add(row); // Add the row to the 2D ArrayList  
        }  
  
        // Print the 2D ArrayList  
        for (ArrayList<Integer> row : list) {  
            System.out.println(row);  
        }  
    }  
}
```


Temperature
```java
import java.util.*;
public class Solution {
    public static List<List<Integer>> fahrenheitToCelsius(int s, int e, int w) {
        List<List<Integer>> list = new ArrayList<>();
        for(int i = s; i <= e; i += w){
            ArrayList<Integer> row = new ArrayList<>();
            row.add(i);
            float c = ftoc(i); 
            row.add(Math.round(c)); // Round to nearest integer
            list.add(row);
        }
        return list;
    }
    public static float ftoc(int f){
        // Corrected the division to ensure floating-point division
        float c = (f - 32) * 5.0f / 9.0f;
        return c;
    }
}
```

XOR

```java
public class MaxXOR {
    public static int maxXOR(int[] arr) {
        int max_xor = 0;
        int n = arr.length;
        // Iterate through all pairs of integers
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                // Compute XOR of current pair
                int current_xor = arr[i] ^ arr[j];
                // Update max_xor if the current XOR is greater
                if (current_xor > max_xor) {
                    max_xor = current_xor;
                }
            }
        }
        return max_xor;
    }
    public static void main(String[] args) {
        int[] arr = {2, 5, 6};
        int result = maxXOR(arr);
        System.out.println("Maximum XOR value: " + result);
    }
}
```


Minimum difference in array in two subarray
import java.util.Scanner;
```java
public class MinAbsoluteDifference {
    public static int minAbsoluteDifference(int[] arr) {
        int totalSum = 0;
        for (int num : arr) {
            totalSum += num;
        }

        int leftSum = 0;
        int minDiff = Integer.MAX_VALUE;

        for (int num : arr) {
            leftSum += num;
            totalSum -= num;
            int diff = Math.abs(totalSum - leftSum);
            minDiff = Math.min(minDiff, diff);
        }

        return minDiff;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();
        for (int t = 0; t < T; t++) {
            int N = scanner.nextInt();
            int[] arr = new int[N];
            for (int i = 0; i < N; i++) {
                arr[i] = scanner.nextInt();
            }
            int result = minAbsoluteDifference(arr);
            System.out.println(result);
        }
        scanner.close();
    }
}

```