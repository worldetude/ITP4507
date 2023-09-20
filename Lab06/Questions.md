## Lab06 Questions  
**Laboratory Exercise 6 – Memento Pattern**  
## Part I  
You are asked to implement the following class diagram which is based on the Memento Design Pattern.  
![image](https://github.com/worldetude/ITP4507/assets/85270523/c7ccda2a-72f3-4739-b517-430adc12c9ad)  
You may use the following Test Program to test the classes that you have implemented.
```java 
import MyPackage.*;

public class TestMemento {
	public static void main(String args[]) {
		Caretaker ct = new Caretaker();
		MyClass mc = new MyClass();
		System.out.println("Create a my class object with state 1");
		System.out.println("Current state : " + mc.getState());
		ct.saveMyClass(mc);
		mc.doAction();
		System.out.println("Change my class object to state 2");
		System.out.println("Current state : " + mc.getState());
		ct.saveMyClass(mc);
		mc.doAction();
		System.out.println("Change my class object to state 3");
		System.out.println("Current state : " + mc.getState());
		ct.saveMyClass(mc);
		mc.doAction();
		System.out.println("Change my class object to state 4");
		System.out.println("Current state : " + mc.getState());
		ct.undo();
		System.out.println("Perform undo");
		System.out.println("Current state : " + mc.getState());
		ct.undo();
		System.out.println("Perform undo");
		System.out.println("Current state : " + mc.getState());
	}
}
```

Sample output of the test program :  
![image](https://github.com/worldetude/ITP4507/assets/85270523/f8e95924-7475-4649-a570-a3e7c8b9fd01)  

## Part II  
**Scenario : SuperBank Corporation**  
![image](https://github.com/worldetude/ITP4507/assets/85270523/5d84cfe5-6d0a-4ba0-805f-36a68b8ad422)  
*Figure 1: Class Diagram for a bank application of Superbank Corporation.*  
  
Because of the merger of the two organizations (BankOne and KWBank), the new corporation Superbank is now formed. For a particular application, if the transaction fails to save because of a dropped network connection or other reason, the system may reach an inconsistent state. You are asked to apply Memento pattern in order to restore the state of the system.  
  
The Memento pattern provides a way to preserve the state of an object, while preserving encapsulation.  
  
The requirement is to apply the Memento pattern to provide undo operations. The Memento object should be able to:  
>1)	save the state (e.g. balance) of an account object, or   
>2)	restore the state of an account object, or   
>3)	save the state of a Customer object, or  
>4)	restore the state of a Customer object.

The Caretaker contains an undo list, which consists of Memento objects. The Caretaker has the method undo(), which performs undo of the last operation, such as:  
>1)	increase the balance of an account, or
>2)	decrease the balance of one account, or 
>3)	add an account to a customer, or 
>4)	remove an account from a customer.
  
Draw a design class diagram for the system. Implement the design class diagram of the system using Java.  
Write test driver program to test your implementation.   


