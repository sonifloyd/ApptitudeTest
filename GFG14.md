#
class Helper 
{ 
    private int data; 
    private Helper() 
    { 
        data = 5; 
    } 
} 
public class Test 
{ 
    public static void main(String[] args) 
    { 
        Helper help = new Helper(); 
        System.out.println(help.data); 
    } 
} 
a) Compilation error
b) 5
c) Runtime error
d) None of these

Ans. (a)
Explanation: A private constructor cannot be used to initialize an object outside the class
that it is defined within because it is no longer visible to the external class.
# 2
public class Test implements Runnable 
{ 
    public void run() 
    { 
        System.out.printf(" Thread's running "); 
    } 
  
    try
    { 
        public Test() 
        { 
            Thread.sleep(5000); 
        }    
    }  
    catch (InterruptedException e)  
    { 
        e.printStackTrace(); 
    } 
      
    public static void main(String[] args) 
    { 
        Test obj = new Test(); 
        Thread thread = new Thread(obj); 
        thread.start(); 
        System.out.printf(" GFG "); 
    } 
} 
a) GFG Thread’s running
b) Thread’s running GFG
c) Compilation error
d) Runtimer error

Ans. (c)
Explanation: A constructor cannot be enclosed inside a try/catch block.

#3) What is the output of the following program?
class Temp 
{ 
    private Temp(int data) 
    { 
        System.out.printf(" Constructor called "); 
    } 
    protected static Temp create(int data) 
    { 
        Temp obj = new Temp(data); 
        return obj; 
    } 
    public void myMethod() 
    { 
        System.out.printf(" Method called "); 
    } 
} 
  
public class Test 
{ 
    public static void main(String[] args) 
    { 
        Temp obj = Temp.create(20); 
        obj.myMethod(); 
    } 
} 
a) Constructor called Method called
b) Compilation error
c) Runtime error
d) None of the above

Ans. (a)
Explanation: When a constructor is marked as private, the only way to create a new object of that class from some external class is using a method that creates a new object, as defined above in the program. The method create() is responsible for creation of Temp object from some other external class. Once the object is created, its method can be invoked from the class in which the object is created.

# 4) Whats is the output of the following program?
public class Test 
{ 
    public Test() 
    { 
        System.out.printf("1"); 
        new Test(10); 
        System.out.printf("5"); 
    } 
    public Test(int temp) 
    { 
        System.out.printf("2"); 
        new Test(10, 20); 
        System.out.printf("4"); 
    } 
    public Test(int data, int temp) 
    { 
        System.out.printf("3"); 
          
    } 
      
    public static void main(String[] args) 
    { 
        Test obj = new Test(); 
          
    } 
      
} 
a) 12345
b) Compilation error
c) 15
d) Runtime error

Ans. (a)
Explanation: Constructors can be chained and overloaded. When Test() is called, it creates another Test object calling the constructor Test(int temp).

# 5) What is the output of the following program?
class Base 
{ 
    public static String s = " Super Class "; 
    public Base() 
    { 
        System.out.printf("1"); 
    } 
} 
public class Derived extends Base 
{ 
    public Derived() 
    { 
        System.out.printf("2"); 
        super(); 
    } 
      
    public static void main(String[] args) 
    { 
        Derived obj = new Derived(); 
        System.out.printf(s); 
    } 
} 
a) 21 Super Class
b) Super Class 21
c) Compilation error
d) 12 Super Class
Ans. (c)
Explanation: Constructor call to super class must be the first statement in the constructor of the Derived class.





