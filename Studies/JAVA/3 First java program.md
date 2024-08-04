- Every file end with **.java** is a class itself
- Java works on unicode value

#### Line of code
![[new 13.jpeg]]
(string[] args)-command line argument

**String is Non primitive**

```
`import java.util.Scanner;`
`public class Main{`
			`public static void main(string args[]){`
					`Scanner in = new Scanner(System.in);`
					`System.out.println(input.nextInt());`
					`}`
					`}`

```

**Primitives**
	Any data type that cannot be break even further are known as primitive 
	
```
`public class Primitives`
	`public static void main (String[] args) {`
	`int collar = 64;`
	`char letter = 'r';`
	`float marks = 98.67f;`
	`double largeDecimalNumbers = 4567654.4567;`
	`long largeInteger = 34567834567876543L;`
	`boolean check = false:
	}
	}`
```

`import java.util.Scanner;`
`publi class Main{`
		`public static void main(string args[]){`
			`Scanner in = new Scanner(System.in);`
			`Int num1 = in.nextInt();`
			`Int num 2 = in .nextInt();`
			`sum = num1+num2`
			`System.out.println(" Number"+ sum)`	
		`}`
`}`

##### Type Casting
Compressing bigger number in smaller type

*Float to int*
`int num = (int) (65.67);`    ==Output - 65==

**Automatic Type promotion in expression**

```
`int a =257;`                           
`byte b = (byte) (a)`;           ==Output - 1==
```

				~~*Maximum range of byte - 256 ---> 257>256*~~
				~~*So 256 % 257 = 1 (Reminder)*~~



```
`byte a = 40;`
`byte b = 50;`
`byte c = 100;`
`int d = (a * b) / c`         

```
==Output - 20==

`int number = 'A'`                            ==Output - 65==

```
byte b = 42;
char c = 'a';
short s = 1024;
int i = 50000;
float f = 5,67f;
double d = 0.1234;
double result = (f * b) + (1 / c) - (d - s);
System.out.println("OUTPUT 1" + (f * b) + "  " + (i / c) +"  " + (d - s));
System.out.println("OUTPUT 2" + result);
```
==OUTPUT 1-   238.14  515  -1023.8766==
==OUT PUT 2-    1777.0166146484376==

*Float + int + Double = Double (As double is bigger everything converted ton double)*
```

		public class Temperature {
			public static void main(String[] args) f
				Scanner in = new Scanner (System. in);
				System.out.print("Please enter temp in C: ");
				float tempC = in. nextFloat);
				float tempF = (tempC * 9/5) + 32;
				System.out. println (tempF);
```