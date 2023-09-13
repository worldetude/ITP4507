# Lab02 Questions  
**Problems**  

Eric is a young programmer.  Eric has written a simple clock application (Clock.java) which displays the time every second. He submits the program to his supervisor John.  John wants Eric to revise the program so that it can be easily extended to use either the Java AWT package or Java Swing package for the GUI.  John has shown Eric an example program for using Java Swing (SwingExample.java).  The java programs can be found in the web site of the module.  
**Perform the following tasks based on the given Problem Statement.**  
i)	Identify the Java codes that needed to change when the GUI package changes.  

ii)	Separate the Java codes which is independent of the GUI package and put into a public class called Clock and save the codes in Clock.java.  

iii)	Define a public interface called DisplayUI which the Clock class needs to call to display the time.  

iv)	Implement a public class called DisplayGUIAwtImp which implements DisplayUI interface and uses the AWT package to display the time.  Implement a default constructor for the class.  

v)	Implement a public class called DisplayGUISwingImp which implements DisplayUI interface and uses the Swing package to display the time. Implement a default constructor for the class.  
 
vi)	An object can be constructed by using Class.forName(className).newInstance(). For example, an object of DisplayGUIAwtImp can be constructed by the following codes:  
``` java
try {
  DisplayUI gui =   
  (DisplayUI)Class.forName(“DisplayGUIAwtImp”).newInstance();
} catch (Exception e) {
  e.printStackTrace();
}
``` 

Revise the public static void main(String args[]) method in the Clock class so that the class name of the implementation for the GUI can be passed as an argument in the command line, e.g. the following command line will run the program with the AWT GUI:  
```
java Clock DisplayGUIAwtImp
```  
  
vii)	Draw a class diagram to show the structure of the whole program.  Your diagram needs to show the Clock, DisplayUI, DisplayGUIAwtImp and DisplayGUISwingImp and the associations between them.    
    
**Clock.java**  
``` java
import java.awt.Frame;
import java.awt.Label;
import java.awt.BorderLayout;
import java.util.Calendar;
import java.text.DecimalFormat;

public class Clock extends Thread {
	private DecimalFormat tflz, tf;
	private Frame frame;
	private Label label;

	public Clock() {
		frame = new Frame();
		label = new Label();
		frame.add(label,BorderLayout.CENTER);
		frame.setSize(50,50);
		frame.setVisible(true);

		tf = new DecimalFormat("#0");
		tflz = new DecimalFormat("00");
	}

	public void run() {
		try {
			while (true) {
				Calendar calendar = Calendar.getInstance();
				StringBuffer buf = new StringBuffer();
				buf.append(tf.format(calendar.get(Calendar.HOUR)));
				buf.append(':');
				buf.append(tflz.format(calendar.get(Calendar.MINUTE)));
				buf.append(':');
				buf.append(tflz.format(calendar.get(Calendar.SECOND)));
				label.setText(buf.toString());
				label.repaint();
				Thread.sleep(1000);
			}
		} catch (Exception e) {
			e.printStackTrace();
		}
	}

	static public void main(String[] arg) {
		Clock clock = new Clock();
		clock.run();
	}
}
```
