###### **if-else** 

```
Syntax of if statements:
if (condition) {
			// body
}
else if(condition){
	//do this
}
else {
			// do this
}
```

###### **For loop**

```
Syntax of for loops:
for (initialisation;  condition; increment/decrement) {
				// body
}
```

*Printing number 1 to n*
```
Scanner in = new Scanner(System.in);
int i = in.nextInt();
for (int num = 1; num <= i; num += 1) {
		System.out.println(num);
		}
```

###### **While loop**

Syntax:
```
while (condition) {
	//body
	}
```


*For printing 0 to n using while*
```
Scanner in = new Scanner(System.in);
int i = in.nextInt();
int n = 0;
While(n<i){
	System.out.println(n);
		n++;
}
```

###### ***Do while loop***

*It run the program atleast one time if condtion is false*

Syntax
```
do{

}while(condition){

}
```


*Printing 1 to 5 using do while loop*
```

int n=1;
do{
 System.out.println(n);
	 n++
}while(n<=5);
```


***Largest of three numbers***

```
Scanner in = new Scanner (System.in) ;
int a = in.nextInt) ;
int b = in.nextInt() ;
int c = in.nextInt);
// Q: Find the largest of the 3 numbers
int max = a;
if (b > max) {
	max = b;
}
if (c › max) {
	max = c;
}
System.out.println(max);

**Another method**

int max = Math.max (c, Math.maxa, b));
System.out.println(Math.max (34, 57)) ;


```

***Alphabets case check***
```
public class CaseCheck {
public static void main(String[] args) {
		Scanner in = new Scanner (System.in);
		char ch = in.next().trim().charAt(0);
		System.out.println(ch);
}
}
```

==*trim() -*  Used to remove space in front of string==

==*charat(0) - print the character at this index of the string*==

```
if (ch >= 'a' && ch <= 'z') {
		System.out.println ("Lowercase");
} 
else {
		System.out.println ("Uppercase");
}
```

**Fibonacc number**

```
public class Fibe {
	public static void main (String[] args) {
		Scanner in = new Scanner (System. in) ;
			int n = in. nextInto ;
			int a = 0;
			int b = 1;
			int count = 2;
			while (count <= n) {
			int temp = b;
			b = b + a;
			a = temp;
			count++;
		}
	System.out.println(b) ;
}
}
```
==INPUT - 7==
==OUTPUT - 13== 

***Counting occurence of a number***
```

public class CountNums {
	public static void main (String[] args) {
	int n = 45536;
	int count = 0;|
	while (n > 0) {
		int rem = n % 10;
		if (rem == 5) {
		count++;
	}
	n = n / 10; 
System.out.println(count) ;
}
```

**Reverse a number**

```java
public class Reverse {
	public static void main(String[] args) {
		int num = 123456;
		int ans = 0;
		while (num > 0) {
		int rem = num % 10;
		num / = 10;
		ans = ans * 10 + rem;
}
```

***Calculator program***

```
public class Calculator {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        // Take input from user till user does not press X or x
        int ans = 0;
        while (true) {
            // take the operator as input
            System.out.print("Enter the operator: ");
            char op = in.next().trim().charAt(0);

            if (op == '+' || op == '-' || op == '*' || op == '/' || op == '%') {
                // input two numbers
                System.out.print("Enter two numbers: ");
                int num1 = in.nextInt();
                int num2 = in.nextInt();

                if (op == '+') {
                    ans = num1 + num2;
                }
                if (op == '-') {
                    ans = num1 - num2;
                }
                if (op == '*') {
                    ans = num1 * num2;
                }
                if (op == '/') {
                    if (num2 != 0) {
                        ans = num1 / num2;
                    }
                }
                if (op == '%') {
                    ans = num1 % num2;
                }
            } else if (op == 'x' || op == 'X') {
                break;
            } else {
                System.out.println("Invalid operation!!");
            }
            System.out.println(ans);
        }
    }
}
```

Automorphic number
```java
public class Main {  
    public static void main(String[] args) {  
        int num = 25;  
        System.out.println(automor(num));  
    }  
    static boolean automor(int num){  
        int n = num*num;  
        while(num>0){  
            int firstl = num%10;  
            int secl = n%10;  
            if(firstl!=secl)  
                return false;  
            num/=10;  
            n/=10;  
        }  
        return true;  
    }  
    }
```