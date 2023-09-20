## Lab07 Questions  
**Laboratory Exercise 7 – Introduction to JavaScript Programming **  
## Task 01- Operators  
Design a program that help to calculate Circle and Sphere related geometric equation. Let π with a variable name Pi= Math.PI. Capture one user input and create the number type variable name “radius ” to keep the user input value.  
  
>1.	Calculate the below list of equations:  
>>a.	 ![image](https://github.com/worldetude/ITP4507/assets/85270523/1897e955-8f73-4e40-91f4-d80d60bbabc2) [A=Pi\*Square(radius)]    
>>b.	 ![image](https://github.com/worldetude/ITP4507/assets/85270523/e6474501-20e9-4739-9360-e499ff6a8d28) [S=4\*Pi\*Square(radius)]   
>>c.	 ![image](https://github.com/worldetude/ITP4507/assets/85270523/41e9d26a-f6d7-41e0-b10c-8ce6d9c9a079) [V=4/3\*Pi\*Cube(radius)]   
>2.	Show the calculation result in the table.  
  
Expected Input and output  
![image](https://github.com/worldetude/ITP4507/assets/85270523/b91e9db6-2ae3-4731-9a2b-99945c5645af)  
![image](https://github.com/worldetude/ITP4507/assets/85270523/5ca291f2-ba90-40af-bd5d-dda0e519f362)  


## Task 02 - Array  
Design a program that can generate Mark Six Result. Method to get a single Mark Six number:   
>1.	Use Math.random() to get the random number from 0 to 1.  
>2.	Multiple the random number by 49 and add 1, as the greatest number for Mark 6 is 49!  
>3.	Use Math.floor(x) to get the integer closest to x, not greater than a, where x is the value generated at the step 2.  
>4.	Combine it in a single line statement.  
  
Program logic:  
>1.	Create a array of 6 slot in name mark_six.  
>2.	Modify the “for” statement.   
>3.	Modify the assign value from i to random Mark Six value.   
  
Expected Input and output  
![image](https://github.com/worldetude/ITP4507/assets/85270523/9c999633-f32a-45b3-8d73-5feb2228b9fc)  

## Task 03 - Loop  
Calculate Arithmetic Sequences and Sums  
Use the following code template to prepare the answer.  
```html
<!DOCTYPE html>
<html><head>
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
<script>
	var input,n,d,answer;
	input = window.prompt( "Enter n:", "0" ); //The last value with default 0.
	n = parseInt(input);
	input = window.prompt( "Enter d:", "0" ); //The step size with default 0.
	d = parseInt(input);

//Write your logic here!

//Alert the answer!
	alert("part (a) "+answer);	
</script>
</head><body></body></html>	
```

>a.	answer = 1 + 2 + 3 + … + n;  
>b.	answer = 1 + 4 + 9 + … + n*n;   
>c.	answer = 1 + (1+d) + (1+2d) + … + (1+n*d);  
>d.	answer = 1 * 2 * 3 * … * n (or n! This called Factorial)  
>e.	Final Challenge!  
>answer = 1! * 2! * 3! * … * n!  
>>(Hints:   
>>You need to use nested for loop, and the inner loop is answer of part (d).  
>>Rewrite the expression as following:  
>>1*  
>>1*2*  
>>1*2*3*  
>>…………..  
>>1 * 2 * 3 * … * n  
>>Do you know how to print the above triangle?)

## Task 04 - Function  
Computers are playing an increasing role in education. Write a program that will help a primary school student learn multiplication. Use the methods of Math class to produce two positive one-digit integers.   
If the answer is correct, the string “Very good!” is displayed and the student is asked to try another question.   
On the other hand, if the answer is incorrect, the string “No. Please try again.” is displayed in the browser’s status bar and the student is forced to try another answer until the answer is correct.  
  
A separate function should be used to generate each question. This function should be called once when the script begins execution and each time the user answers the question correctly.  
![image](https://github.com/worldetude/ITP4507/assets/85270523/f04003ff-b7cc-45c4-8335-3b959f8f9d1c)
![image](https://github.com/worldetude/ITP4507/assets/85270523/d5835b96-0aa1-4f59-9286-2d0cfca650e2)


