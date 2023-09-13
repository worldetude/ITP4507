# Lab01 Questions  
**Laboratory Exercise 1 – Basic Techniques for Embracing Changes in Object Oriented Software Design**  
## Q01
![image](https://github.com/worldetude/ITP4507/assets/85270523/b73f1f13-dd59-486c-87a7-0b926c3b9e5f)  
- [ ] i)	Write Java programs to implement the classes shown in Figure 1.  Each class should be declared as public class and put in a separate Java source file.   
- [ ] ii)	Write a driver class (Main.java) to create a Client object and call the doAction() method of the Client class.  Run the Main class to test the implementation of the classes shown in Figure 1.  
- [ ] iii)	Modify a statement in Client.java so as to call the doService() method of the Server2 class.  Test your program after the change.  
## Q02  
![image](https://github.com/worldetude/ITP4507/assets/85270523/cdf65806-a3f9-411d-9ee4-81b64f317674)  
- [ ] i)	Write Java programs to implement the classes/interface shown in Figure 2.  Each class/interface should be declared as public and put in a separate Java source file.  
- [ ] ii)	Write a driver class (Main.java) to create a Client object and call the doAction() method of the Client class.  Run the Main class to test the implementation of the classes shown in Figure 2.  
- [ ] iii)	Modify a statement in Client.java so as to call the doService() method of the Server2 class.  Test your program after the change.  

## Q03  
A junior programmer developed the following Java program.  

``` java
public class Main {

	public static void main(String[] args) {
		Cal cal = new Cal();
		cal.compute();
	}
}

public class Cal {

	public void compute() {
	    int x = 2, y = 3;
		String s = "hello";
	
		System.out.println("Cal: compute()");
		int n = method1(x, y);
		int m = method2(s);
		System.out.println("method1(" + x + "," + y + ")" + "=" + n);
		System.out.println("method2(" + s + ")" + "=" + m);
	}

	int method1(int x, int y) {
		System.out.println("Cal: method1(" + x + "," + y + ")");
		return x + method3(y);
	}

	int method3(int y) {
		System.out.println("Cal: method3(" + y + ")");
		return 2*y;
	}
	
	int method2(String s) {
		System.out.println("Cal: method2(" + s + ")");
		return s.length()-2;
	}
}

```
He inserted many System.out.println statements display messages for helping him to debug his program.   His supervisor reviewed the program and told him that the program should be easily changed to display the debugging messages on the screen, store the messages in a text file, or send the messages to a remote socket connection.  With his current program, he finds it is difficult to change the handling of the debugging messages in the program.    

You are asked to re-design the program so that the program can handle the debugging messages in different ways by minimal changes in the program.    


**Part A - re-designing the program using a method in the same class which uses the method**  
- [ ] i)	Identify program codes which may change and separate them from the remaining program.  
- [ ] ii)	Declare a method called log(String message) for handling the debugging messages in the Cal class and revise the codes in the program to use the method to display debugging messages.  Test the revised program.  
- [ ] iii)	Now, you are going to change the implementation of the method log for handling the debugging message by over-riding the method in a subclass of Cal.  Perform the following steps:  
  > - [ ] •	Declare a class called Cal2 which is a subclass of the Cal and declare the log(String message) method which writes the debugging message in a text file called log.txt  
  > - [ ] •	You also need to declare the variables in Cal2 and create the necessary object(s) for text file handling in the constructor of Cal2.  
  > - [ ] •	Test Cal2 by creating an object of Cal2 in the Main class.
  >> *Hint: the following is a sample program to write a text file.*  
  >> ``` java  
  >> import java.io.*;
  >> 
  >> public class TestWriteText {
  >> 	public static void main(String[] args){
  >> 		try {
  >> 			FileWriter outputFile = new FileWriter(args[0]);
  >> 			PrintWriter out = new PrintWriter(outputFile);
  >> 			
  >> 			// Write text to file
  >> 			out.println("line 1");
  >> 			out.println("line 2");
  >> 			// write the text from buffer to the file
  >> 			out.flush();
  >> 			// close the file after use
  >> 			out.close();
  >> 		} catch (IOException e){
  >> 			e.printStackTrace();
  >> 		}
  >> 	}
  >> }
  >>  
  >> ```

- [ ] iv)	Draw a class diagram to show the relationships between the Main, Cal, and Cal2 classes.  Show all methods in the class diagram.  

**Part B – re-designing the program using method in a separate class**  
- [ ] i)	Declare a public interface called Debug with an abstract public method called log(String message)   
- [ ] ii)	Declare a public class called DebugToScreen which implements the Debug interface.  Declare a method call log(String message) for displaying the debugging messages.  
- [ ] iii)	Revised the codes in the Cal class for using the DebugToScreen class to handle the debugging messages.  Test the revised program.  
- [ ] iv)	Now, you are going to provide another implementation of the method log for handling the debugging message.  Perform the following steps:  
  > - [ ] •	Declare a class called DebugToTextFile which implements the Debug interface and declare the log(String message) method which writes the debugging message in a text file called log.txt     
  > - [ ] •	Test DebugToTextFile by creating an object of DebugToTextFile in the Cal class.

- [ ] v)	Draw a class diagram to show the relationships between the Main, Cal, and Debug. DebugToScreen, and DebugToTextFile.  Show all methods in the class diagram.   

**Part C – Comparison of the Design of Part A and Part B**   
- [ ] i)	Compare the design in Part A and Part B.  Explain which design is better in terms of expendability and ease of maintenance of the program.
