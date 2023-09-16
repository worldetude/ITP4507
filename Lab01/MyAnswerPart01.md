# Questions 01 and 02
Ip Chun Leung 200109230  
  
## Question01

**Server.java**  
``` java

package lab01q01;  

public class Server {  
	public void doService() {  
		System.out.println("Server doService");  
	}  
}  

```
  
**Server2.java**  
``` java

package lab01q01;  

public class Server2 extends Server {  
	public void doService() {
		System.out.println("Server2 doService");
	}
}

```
  
**Client.java**  
``` java

package lab01q01;

public class Client {
	public void doAction(){
		System.out.println("Client doAction");
		Server s = new Server();
		s.doService();
		Server s2 = new Server2();
		s2.doService();
	}
}


```
  
**Main.java**  
``` java

package lab01q01;

public class Main {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("Hello World");
		Client c = new Client();
		c.doAction();
	}
}

```

## Question02  

**ServerInterface.java**  
``` java

package lab01q02;

public interface ServerInterface {
	public abstract void doService();
}

```
  
**Server.java**  
``` java

package lab01q02;

public class Server implements ServerInterface {
	public void doService() {
		System.out.println("Server doService");
	}
}

```
  
**Server2.java**  
``` java

package lab01q02;

public class Server2 implements ServerInterface {
	public void doService() {
		System.out.println("Server2 doService");
	}
}

```
  
**Client.java**  
``` java

package lab01q02;

public class Client {
	public void doAction() {
		ServerInterface si = new Server();
		ServerInterface si2 = new Server2();
		System.out.println("Client doAction");
		si.doService();
		si2.doService();
	}
}

```
  
**Main.java**  
``` java

package lab01q02;

public class Main {
	public static void main(String[] args) {
		System.out.println("Hello World");
		Client c = new Client();
		c.doAction();

	}
}


```
  
  
