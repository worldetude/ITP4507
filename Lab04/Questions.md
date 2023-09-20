# Lab04 Questions  
**Laboratory Exercise 4 – Factory Pattern**  
## Part I  
![image](https://github.com/worldetude/ITP4507/assets/85270523/2e00d266-25e8-482b-aa84-1b947c96d998)    

**a)** You may use the following Test Program to test the classes that you have implemented.  
``` java 
	public class TestFactoryMethod {
		public static void main(String [] args) {
			String [] creators = {"ConcreteCreatorA", "ConcreteCreatorB"};
			try {
				int choice = Integer.parseInt(args[0]);
				Creator c = 
					(Creator)Class.forName(creators[choice]).newInstance();
				c.anOperation();
			}
			catch (Exception e) {
				System.out.println("Problem Encoutered");
			}
		}
	}
```
**Sample output of the test program :**  
![image](https://github.com/worldetude/ITP4507/assets/85270523/ffa29ffd-358c-4acf-8554-3a301dd0f0ed)  

**b)**	You are asked to implement the following class diagram which is based on the Abstract Factory Design Pattern.  
![image](https://github.com/worldetude/ITP4507/assets/85270523/9c2adc1c-726f-407a-b665-0f27b51b3831)
You may use the following Test Program to test the classes that you have implemented.
```java 
	public class TestAbstractFactory {
		public static void main(String[] args) {
			String [] factories = {"ConcreteFactory1", "ConcreteFactory2"};
			try {
				Client c = new Client();
				int choice = Integer.parseInt(args[0]);

				AbstractFactory af = 
						(AbstractFactory)Class.forName(factories[choice]).newInstance();

				System.out.println("Product A Created : " 
								+ c.createA(af).getName());
				System.out.println("Product B Created : " 
								+ c.createB(af).getName());
			}
			catch (Exception e) {
				System.out.println("Problem encountered");
			}
		}
}
```
**Sample output of the test program :**  
![image](https://github.com/worldetude/ITP4507/assets/85270523/8d7a166f-a52d-4f0a-9014-1a173d4f67c3)  
**c)**	By comparing part (a) and part (b), can you identify the main difference between Factory Method and Abstract Factory?  Give one situation (other than the examples given in the lecture notes) in which Abstract Factory pattern is more suitable than Factory Method pattern.
## Part II  
Download the simple drawing program from Moodle.   Draw a class diagram to show the classes and their associations of the program.   
Describe the problem of the program if more shapes have to be supported by the program.  
  
## Part III  
Apply the Factory Method design pattern to solve the problem which you have described in Part II.  Draw a suitable class diagram to show the design of your solution.  Indicate the roles (i.e. Creator, Concrete Creator, Product, and Concrete Product) of the classes in your diagram.  
Implement the design of your solution.  
  
## Part IV  
The java.lang.Class provides methods to load a class (String) and creates an object of the class dynamically. Study the following methods of java.lang.Class:  
forName(String className).newInstance()  
Use the methods of java.lang.Class to implement your design of solution for Part III.  
