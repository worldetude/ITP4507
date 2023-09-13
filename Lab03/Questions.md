# Lab03 Questions
Laboratory Exercise 03 – Adapter Pattern
## Question 01
The OldCircle interface defines a circle by 3 numbers a, b, c where a, b, c are the coefficients of the equation (x – a)2 + (y – b)2 = c.   
Note : The center of the circle is at point (a,b) and radius of the circle is equal to the square root of c.  
  
The code for OldCircle interface is as follow:-  
```
public interface OldCircle {
	public double [] getCoeff( );
}
```  
The NewCircle interface defines a circle by its radius and center, which is represented by a java.awt.Point object.  
  
The code for NewCircle interface is as follow:-  
```
public interface NewCircle {
	public double getRadius( );
	public Point getCenter( );
}
```  
We have some legacy code which implements OldCircle.  
``` 
public class OldCircleImpl implements OldCircle {
	private double [] coeff = new double[3];
	public OldCircleImpl(double a, double b, double c) {
		coeff[0] = a; coeff[1] = b; coeff[2] = c;
	}
	public double [ ] getCoeff( ) {
		return coeff;
	}
}
```  
However, the class PrintCircle below only uses the NewCircle interface.  
``` 
public class PrintCircle {
	public static void printCircle(NewCircle newCircle) {
		System.out.println(" r = " + newCircle.getRadius( ));
		System.out.println("center = [" + newCircle.getCenter( ).getX() 
+ " , "  + newCircle.getCenter( ).getY() + "]");
	}
} 
```  
**Part A**  
Implement an object adapter CircleObjectAdapter class that allows the PrintCircle class to print the details of a OldCircleImpl object. Write a simple test program that creates an OldCircleImpl object with a = 10.0, b = 15.0, c = 25.5 and prints the details of the circle using the PrintCircle class.  Draw a class diagram to show your solution.  
  
**Part B**  
Implement a class adapter CircleClassAdapter class that allows the PrintCircle class to print the details of an OldCircleImpl object. Write a simple test program that creates a CircleClassAdapter object with a = 10.0, b = 15.0, c = 25.5 and prints the details of the circle using the PrintCircle class. Draw a class diagram to show your solution.  
  
## Quesiton 02  
Margret is a junior programmer. She has written a program Main.java which performs calculation using Fraction objects (Fraction.java).  She has also written a simple implementation of Fraction (SimpleFraction.java) for testing Main.java.  Later, she has found a better implementation of Fraction (LongFraction.java).  She wants to use the LongFraction class to handle fractions in her program.  In order to avoid changing the old codes (Main.java, Fraction.java, and LongFraction.java), she wants to apply the Adapter Design Pattern to handle the difference between the interface expected by the Main class and the interface provided by the LongFraction class.  

**Part A**  
Implement an object adapter ObjectFractionAdapter class so that the Main class can use the LongFraction class to handle fractions.  Test your program.  Draw a class diagram to show your solution.  
  
**Part B**  
Implement a class adapter ClassFractionAdapter class so that the Main class can use the LongFraction class to handle fractions.  Test your program.  Draw a class diagram to show your solution.  
  
***Main.java:***  
```java 
public class Main {
	public static void main(String[] args) {
		Fraction a, b;

		a = new SimpleFraction(1,2); // 1/2
		b = new SimpleFraction(1,4); // 2/3

		System.out.println(a + "+" + b + "=" + a.add(b));
		System.out.println(a + "-" + b + "=" + a.subtract(b));
		System.out.println(a + "-" + 1 + "=" + a.subtract(1));
		System.out.println(a + "+" + 1 + "=" + a.add(1));
	}
}

Fraction.java
public interface Fraction {
	public int getNumerator();
	public int getDenominator();
	public Fraction add(Fraction b);
	public Fraction add(int b);
	public Fraction subtract(Fraction b);
	public Fraction subtract(int b);
	public String toString();
}
```

***SimpleFraction.java:***  
[To be inserted]  

***LongFraction.java:***  
[To be inserted]  
  
## Question 03  
**Scenario 1: BankOne Corporation**  
![image](https://github.com/worldetude/ITP4507/assets/85270523/76022f60-67bc-433e-98bf-a9b80cccdddf)  

**Scenario 2: KWBank Corporation**  
![image](https://github.com/worldetude/ITP4507/assets/85270523/e16cf916-0409-42da-af6c-46e14e976529)  
  
Figure 1 shows the analysis class diagram of a bank application of BankOne Corporation. A lot of applications were written using the methods in the Account class.   
  
Figure 2 shows the analysis class diagram of a bank application of KWBank Corporation. A lot of applications were written using the methods in the InternationalAccount class.  

**Scenario 3: BankOne + KWBank = SuperBank**  

Because of the business merge of the two organizations, BankOne Corporation is merged with a larger bank group KWBank, to form a new bank group called SuperBank. Suppose you are a system analyst in bank group KWBank, and you want to allow your current applications to access the accounts of BankOne, and you just want your programmers to use the current functions in your company.   
  
Adapter pattern converts the programming interface of one class into that of another. You use adapters whenever you want unrelated classes to work together in a single program.   
  
You need to merge the classes in Figure 1 into Figure 2 to produce the design class diagram of SuperBank. It is required that your existing applications will only use the methods existed in KWBank Corporation, but they can also access the data in BankOne Corporation. You are asked to apply the adapter pattern to handle this requirement in the new SuperBank corporation.     
  
***Part I***  
Implement the design class diagram of BankOne Corporation in figure 1. Write your test driver program to test the implementation of the design class diagram.  
  
***Part II***  
Implement the design class diagram of KWBank Corporation in figure 2. Write your test driver program to test the implementation of the design class diagram.  
  
***Part III***  
1.	Develop the design class diagram of SuperBank Corporation. You may need to add new classes, attributes, methods, parameters, etc.   
  
2.	Implement the design class diagram that you have developed. Write your test driver program to test the implementation of the design class diagram. You want to allow your current applications to access the information in BankOne corporation.

**Please do the following :**  
> 1.	Part I - Implementation  
>> a.	Class diagram implementation (source code)  
>> b.	Test driver program (source code)  
>> c.	Test runs (screen dump)  
> 2.	Part II – Implementation  
>> a.	Class diagram implementation (source code)  
>> b.	Test driver program (source code)  
>> c.	Test runs (screen dump)  
> 3.	Part III – Design class diagram  
> 4.	Part III – Implementation  
>> a.	Class diagram implementation (source code)  
>> b.	Test driver program (source code)  
>> c.	Test runs (screen dump)  







