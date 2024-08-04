	
```java

class Solution {
    public boolean isPalindrome(String s) {
        s=s.toLowerCase();
        s=s.strip();
        StringBuilder sb = new StringBuilder();
        for(int j = 0;j<s.length();j++){
            if(Character.isLetterOrDigit(s.charAt(j))){
                sb.append(s.charAt(j));
            }
        }
        for(int i = 0;i<sb.length();i++){
        int start = sb.charAt(i);
        int last = sb.charAt(sb.length() - 1 - i);
        if(last != start){
            return false;
        }    
        }
        return true;
    }
}
```

Make capital of first letter

```java
public class Solution{
    public static String convertString(String str) {
            StringBuilder sb = new StringBuilder();
            char first = str.charAt(0);
            first = f.toUpperCase(first);
            sb.append(first);
            for(int i=1;i<str.length();i++){
                char curr = str.charAt(i);
               if(str.charAt(i-1)==' '){
                   sb.append(Character.toUpperCase(curr));
               }else{
                   sb.append(curr);
               }
            }
                String result = sb.toString();
                return result;
        }
```


Checking upper case
```java
import java.util.* ;
import java.io.*; 
public class Solution {
    public static String editSentence(String str){
        StringBuilder sb = new StringBuilder();
        char f = str.charAt(0);
        f = Character.toLowerCase(f);
        sb.append(f);
        for(int i=1;i<str.length();i++){
            char c = str.charAt(i);
            if(Character.isUpperCase(c)){
                sb.append(' ');
                c=Character.toLowerCase(c);
                sb.append(c);
            }else{
                sb.append(c);
            }
        }
        String result = sb.toString();
        return result;
}
```

String.valueof(i);
Tommypang04