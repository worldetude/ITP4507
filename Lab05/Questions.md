## Lab05 Questions
**Laboratory Exercise 5 – Command Pattern**  
## Part01  
![image](https://github.com/worldetude/ITP4507/assets/85270523/20800300-8fcd-4c6e-aa97-8625bb3d0518)  
**a)**	Implement the above class diagram for the Command interface and Command1 and Command2 implementation classes  
**b)**	Implement the Main class to test implementation of Command1 and Command2  
**c)**	With a Stack, write program codes to create various Command objects of Command1 and Command2, execute the Command objects in sequence, and perform undo operations of the Command objects in reverse sequence.  

## Part02  
**a)** You are asked to download the source code of a sample program GenerateNumbers.java from web site of the module. Compile and test run the program.    
**The following is a sample run of the program:-** 
![image](https://github.com/worldetude/ITP4507/assets/85270523/7021f909-4691-47f3-8290-7ca2084c191c)  
**b)**	You may find that the program will be very messy if more different types of number are to be generated periodically by the program. In fact the application can be re-designed based on the command pattern as shown in the following class diagram.   
![image](https://github.com/worldetude/ITP4507/assets/85270523/733b4586-15e6-443a-987a-abadcab00a40)  
Given the following additional information:  

|**Class Name** | **Description** |
|---|---|
|Task|An interface that has only one method `performTask()`.|
|NextNumberTask|A class that implements the interface `Task`, it shows the next positive integer when the method `performTask(`) is called (starting from 1).|
|NextPrimeNumberTask|A class that implements the interface Task, it shows the next prime number when the method `performTask()` is called (starting from 2).|
|TaskEntrt|A class that is used to hold a command object (`Task` object). It also keeps 2 data members of type `long : repeatInterval` (how often the task should be executed) and `timeLastDone`(time which the task was last done).|
|TaskMinder|TaskMinder	A thread that holds a list of `TaskEntry` objects and can periodically execute the method `performTask()` of  `Task` objects. It also keep 1 data member of type `long : sleepInterval` (how often the `TaskMinder` should check for tasks to be run).|  
You are asked to implement the class diagram based on the given information. You may need to add more methods to classes if necessary.   
  
The following is a test program for your implementation.  
```java
public class TestCommandPattern {
	public static void main(String [] args) {
		TaskMinder tm = new TaskMinder(100);

		NextNumberTask next = new NextNumberTask();
		TaskEntry numberTaskEntry = new TaskEntry(next, 3000);
		tm.addTaskEntry(numberTaskEntry);

		NextPrimeNumberTask nextPrime = new NextPrimeNumberTask();
		TaskEntry primeTaskEntry = new TaskEntry(nextPrime, 7000);
		tm.addTaskEntry(primeTaskEntry);

		tm.start();
	}
}
```

## Part03  
You are asked to apply the command pattern to provide the undo function for a simple drawing program.  Follow the steps below to complete this exercise:   
  
>1.	Download the simple drawing program from the web site of the module.   
>2.	Identify the code fragments which implement commands.  
>3.	Apply the command pattern to revise the design of the program.  Draw a class diagram to show the new design.  You may apply the Factory pattern for creating the required commands.  
>4.	Implement the new design and test the program.
