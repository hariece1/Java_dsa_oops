
BINARY TO DECIMAL

```java
public class bin2 {  
    public static void main(String[] args) {  
        long bin =101010111110L;  
        int dec = 0;  
        int base =1;  
        while(bin!=0){  
            int rem = (int)(bin%10);  
            bin = bin/10;  
            dec += base*rem;  
            base= base*2;  
        }  
        System.out.println(dec);  
    
    int dec=10;  
	int result1 = 0;  
	int position = 1;  
	while(dec>0){  
    int rem1 = dec%2;  
    result1 += rem1 * position; // Multiply the remainder by the position (1, 10, 100, etc.)  
    dec /= 2;  
    position *= 10;  
}  
System.out.println(result1);
    }  
}
```

AUTOMORPHIC NUMBER
```java
Scanner in = new Scanner(System.in);  
int n = in.nextInt();  
if(n>0){  
  int sq = n*n;  
  int q = String.valueOf(n).length();  
  int last2 = sq%(int)Math.pow(10,q);  
  if(n==last2){  
      System.out.println("Auto");  
  }  
  else {  
      System.out.println("NO");  
  }  
}
```
ninjas test
import java.util.* ;

import java.io.*; 

import java.lang.Math;

public class Solution {

  

    public static int maxDifference(int n, int arr[]) {

        int[] left_small = new int[n];

        Arrays.fill(left_small, 0);

        int[] right_small = new int[n];

        Arrays.fill(right_small, 0);

        Stack<Integer> stack = new Stack<>();

        for(int i=0;i<n;i++){

            while(!stack.isEmpty() && arr[stack.peek()]>=arr[i]){

                stack.pop();

            }

            if(stack.isEmpty()){

                left_small[i] = 0;

            }else{

                left_small[i] = arr[stack.peek()];

            }

            stack.push(i);

        }

        stack.clear();

        for(int i= n-1;i>=0;i--){

            while(!stack.isEmpty() && arr[stack.peek()]>=arr[i]){

                stack.pop();

            }

            if(stack.isEmpty()){

                right_small[i] = 0;

            }else{

                right_small[i] = arr[stack.peek()];

            }

            stack.push(i);

        }

        stack.clear();

        int maxdiff = 0;

        for(int i=0;i<n;i++){

            maxdiff = Math.max(maxdiff,Math.abs(left_small[i] - right_small[i]));

        }

        return maxdiff;

    }

  

}



3 or 4

add string
jump

28