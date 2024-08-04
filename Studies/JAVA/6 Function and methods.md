
- Function return the value if mentioned in its type
- In java the values are not passed by reference they are pass by value
- Changes made in scope liking swaping will remain inside the scope only
- Arrays can be modified using reference variable **Non primitive *** (Pass by value)
- Value initialized outside the block cant be reinitialized but can be modified
- Value initialized inside the block cant be used outside
- Anything initialized inside the block can be initialized outside the block


```java
public class Sum {
public static void main (String[] args) {
int ans = sum20 ;   //return value is stored in ans
System.out - println(ans) ;
}
// return the value
static int sum2() {
Scanner in = new Scanner (System. in) ;
System.out print("Enter number 1: ");
int numi = in.nextInt;
System.out print("Enter number 2: ");
int num2 = in. nextInt() ;
int sum = numl + num2;
return sum;|
}
```

Function that prints 

```
public class Sum {
public static void main (String[] args) {
sum () ;
}
static void sum() {
Scanner in = new Scanner (System. in) ;
System.out-print("Enter number 1: ");
int numl = in. nextInt) ;
System.out-print("Enter number 2: ");
int num2 = in. nextInt) ;
int sum = numl + num2;
System.out.println("The sum = " + sum) ;
```

Passing input value from user
 
```
Scanner in = new Scanner (System.in);
System.out print("Enter your name: ");
String name = in. next;
String personalised = myGreet (name) ;
System.out. println (personalised);
}
static String myGreet(String name) {
String message = "Hello" + name;
return message;
```

###### **Shadowing**
	Higher value is over rided by low level is known as shadowing
	Shadowing doesnt work at method only in class variable

```
public class Shadowing {
	static int x = 90; // this will be shadowed at line 8
	public static void main(String[] args) {
		System.out. println(x); // 90
		int x = 40;
		System.out.println(x); // 40
		fun () ;
		}
	}
static void fun() {
	System.out.println(x);
}
```

###### ***Vairables and arguments***

Vairable number of arguments
```
public class VarArgs {
	public static void main(String[] args) {
		fun (...v: 2, 3, 4, 5, 56, 87, 23, 45, 65);
		}
static void, fun(int ...v) {
		System.out.println(Arrays.toString (v));
}
}
```

###### **Overloading**
Two or more function with same name but different argument
```
public class Overloading {
public static void main(String[] args) {
fun (a: 67);
fun (name: "Kunal Kusbwaba");
}
}
}
static void fun(int a) {
System. out. println(a) ;1
static void fun(String name) {
System.out. println(name);
}
```