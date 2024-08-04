
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

Adding 2 numbers in string
```java
public class Solution {
    public static String multiplyStrings(String a, String b) {
        int[] result = new int[a.length() + b.length()]; // Initialize an array to store the result
        
        // Iterate through the digits of both numbers
        for (int i = a.length() - 1; i >= 0; i--) {
            for (int j = b.length() - 1; j >= 0; j--) {
                int digitA = a.charAt(i) - '0'; // Convert char to int
                int digitB = b.charAt(j) - '0'; // Convert char to int
                result[i + j + 1] += digitA * digitB; // Add the product to the corresponding position in the result array
            }
        }
        // Process carry
        int carry = 0;
        for (int i = result.length - 1; i >= 0; i--) {
            int sum = result[i] + carry;
            result[i] = sum % 10; // Store the last digit
            carry = sum / 10; // Update the carry
        }
        
        // Convert the result array to a string
        StringBuilder sb = new StringBuilder();
        for (int num : result) {
            sb.append(num);
        }
        
        // Remove leading zeros
        while (sb.length() > 1 && sb.charAt(0) == '0') {
            sb.deleteCharAt(0);
        }
        
        return sb.toString();
    }
}
```
BASE CONVERSION
```java
import java.util.* ;
import java.io.*; 
public class Solution {

    public static int baseConversion(String num, int base) {
        int decimal =0;
        for(int i=0;i<num.length();i++){
            char digit = num.charAt(i);
            int value;
            if(Character.isDigit(digit)){
                value = digit - '0';
            }
            else{
                value =  10+digit-'A';
            }
            if(value>=base){
                return -1;
            }
            decimal = decimal*base+value;
        }
        return decimal;
    }
}
```

https://chat.openai.com/share/a102d9a4-e7a3-4b05-8731-16b54e3cd161
https://chat.openai.com/share/8e80b55e-ef26-44dc-a9b3-ebc79f137057
```java
import java.util.* ;
import java.io.*; 
public class Solution {
    public static boolean isPossible(int[] arr, int n) {
        int count =0;
        for(int i=1;i<arr.length;i++){
            if(arr[i]<arr[i-1]){
                count++;
                if(count>1){
                    return false;
                }
                if(i==1 || arr[i]>=arr[i-2]){
                    arr[i-1]= arr[i];
                }else{
                    arr[i] = arr[i-1];
                }
            }
        }
        return true;
    }
}
```
Set matrix zero
```java
import java.util.*;  
  hdfjjjjjjdd
public class Main {  
    static ArrayList<ArrayList<Integer>> zeroMatrix(ArrayList<ArrayList<Integer>> matrix, int n, int m) {  
        int[] row = new int[n]; // row array  
        int[] col = new int[m]; // col array  
  
        // Traverse the matrix:        for (int i = 0; i < n; i++) {  
            for (int j = 0; j < m; j++) {  
                if (matrix.get(i).get(j) == 0) {  
                    // mark ith index of row wih 1:  
                    row[i] = 1;  
                    // mark jth index of col wih 1:  
                    col[j] = 1;  
                }  
            }  
        }  
  
            for (int i = 0; i < n; i++) {  
            for (int j = 0; j < m; j++) {  
                if (row[i] == 1 || col[j] == 1) {  
                    matrix.get(i).set(j, 0);  
                }  
            }  
        }  
        return matrix;  
    }  
    public static void main(String[] args) {  
        ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();  
        matrix.add(new ArrayList<>(Arrays.asList(1, 1, 0)));  
        matrix.add(new ArrayList<>(Arrays.asList(1, 0, 1)));  
        matrix.add(new ArrayList<>(Arrays.asList(1, 1, 1)));  
  
        int n = matrix.size();  
        int m = matrix.get(0).size();  
  
        ArrayList<ArrayList<Integer>> ans = zeroMatrix(matrix, n, m);  
  
        System.out.println("The Final matrix is: ");  
        for (ArrayList<Integer> row : ans) {  
            for (Integer ele : row) {  
                System.out.print(ele + " ");  
            }  
            System.out.println();  
        }  
    }  
}
```
Isometric array
```java
public class Main  
{
    public static void main(String[] args) {  
  
        System.out.println(isometric("abc","xxz"));  
    }  
    static boolean isometric(String str1,String str2){  
        if(str1.length() != str2.length()){  
            return false;  
        }  
        int[] map1 = new int[256];  
        int[] map2 = new int[256];  
        for(int i=0;i<str1.length();i++){  
            int char1 = str1.charAt(i);  
            int char2 = str2.charAt(i);  
            if(map1[char1]==0 && map2[char2]==0){  
                map1[char1] = char2;  
                map2[char2] = char1;  
            }else if(map1[char1] != char2 && map2[char2] != char1){  
                return false;  
            }  
        }  
        return true;  
    }  
}
```
Reverser a word in sentence
```java

class Solution {
    public String reverseWords(String s) {
        s=s.trim();
        String[] word = s.split("\\s+");
        reverseword(word);
        return String.join(" ",word);
    }
    static void reverseword(String[] word){
        int left = 0,right = word.length - 1;
        while(left<right){
            String temp = word[left];
            word[left] = word[right];
            word[right]= temp;
            left++;
            right--;
        }
    }
}
```
String and goal
```java
import java.util.*;  
public class Main  
{  
    public static void main(String[] args) {  
        String word = "abcdefkj";  
        String goal = "cdefab";  
        int[] goala = new int[goal.length()];  
        int[] worda = new int[word.length()];  
        for(int i=0;i<word.length();i++){  
            worda[i] = word.charAt(i);  
        }  
        for(int i=0;i<goal.length();i++){  
            goala[i] = goal.charAt(i);  
        }  
        boolean flag = true;  
        if(worda.length != goala.length){  
            flag = false;  
            System.out.println(flag);  
            return;  
        }  
        System.out.println(Arrays.toString(worda));  
        int count = 0;  
        while(count<2) {  
            rotate(worda);  
            count++;  
        }  
       // System.out.println(Arrays.toString(worda));  
        for(int i=0;i<worda.length;i++){  
            if(worda[i]!=goala[i]){  
                flag = false;  
                System.out.println(flag);  
                return;  
            }  
        }  
        System.out.println(flag);  
    }  
    static void rotate(int[] worda){  
        char temp = (char)worda[0];  
        for(int i=1;i<worda.length;i++){  
            worda[i - 1] = worda[i];  
        }  
        worda[worda.length - 1] = temp;  
    }  
}
```

square root without using inbuilt function
```java
class Solution {
    public int mySqrt(int x) {
        if( x == 0 || x == 1){
            return x;
        }
        int start  = 0;
        int end = x;
        int mid = -1;
        while(start<=end){
            mid = start +(end -start)/2;
            if((long)mid*mid > (long)x){
                end = mid - 1;
            }else if(mid*mid == x){
                return mid;
            }else{
                start = mid + 1;
            }
        }
        return Math.round(end);
    }
}
```

Single number in array using xor
```java
class Solution {
    public int singleNumber(int[] nums) {
        int result = 0;
        for(int num : nums){
            result ^= num;
        } 
       return result;
    }
}
```

       