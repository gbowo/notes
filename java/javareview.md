# java总复习


## 复习重点

1、考试时间：12月21日
2、试卷类型：全英文试卷
3、复习范围：Chapter 1，2，3，4，5，6，7，**9，10，11，12，13**，14，15
Lab1~Lab3
4、考试题型：（1）单选题15道30分
            （2）判断题（T或F）5道5分
            （3）简答题3道15分
            （4）读程序题4道20份
            （5）编程题2道大题30分


## Chapter 1 Introduction to Computers,Programs and Java

### Terminologies:
(1)**Modularity(模块化)**: The source code for anobject canbewritten and maintained independentlyof thesourcecode for other objects. After it is created, anobjectcan be easily passed around insidethesystem.(对象的源代码可以独立于其他对象的源代码来编写和维护，创建后，对象可以轻易地在系统内传递)
(2)**Information-hiding(信息隐藏)**: By interacting only with an object’s methods, the details of its internal implementation remain hidden from the outside world.
(3)**Code re-use(代码复用)**: If an object already exists(perhapswritten by another software developer), you can use that object in your program. This allows specialists to implement, test, and debug complex, task-specific objects, which you can thentrust torun in your own code.
(4)**Pluggability and debugging ease(可插拔性和调试简便性)**: If aparticularobject is found to be problematic, you can simply remove it from your application and plugin a different object as its replacement.
(5)**JVM(Java Virtual Machine)**: java虚拟机
(6)**JRE(Java Routine Environment)**: java类库
(7)**JDK(Java Development Kit)**: java开发工具包


## Chapter 2 Elementary Programing

1. Create a Scanner Object
``` java {.line-numbers}
Scanner input = new Scanner(System.in);
System.out.print("Enter a double value:");
double radius = input.nextDouble();
```

2. ExponentOperations(指数运算)
``` java
Math.pow((2,3));//a^3
```

## Chapter 3 Selections

``` java {.line-numbers}
Double x = 1.0-0.1-0.4;
System.out.println(x == 0.5);
System.out.println(x);
```

浮点数具有有限的计算精度，涉及浮点数的计算可能引入舍入错误。因此两个浮点数值的相等测试不可靠。


## Chapter 4 Mathemetical Functions,Characters,and Strings

1. random方法
用法:a+(int)(Math.random()*b),return a random number between a and a+b-1.

2. Conversion between Strings and Numbers
``` java {.line-numbers}
//分别将字符串转换成int和double型
int intValue = Integer.parseInt("123");
double doubleValue = Double.parseDouble("45.67");
//将数值转换成字符串
String s = 23 + "";
String s1 = String.valueOf(s);
String s2 = Integer.toString(15);
```


## Chapter 5 Loops
跟C++一样


## Chapter 6 Methods

方法的定义由方法名称、参数、返回值类型、修饰符以及方法体组成
修饰符 返回值类型 方法名(参数列表)
{//方法体;}

重载方法：根据方法签名(参数列表)决定使用哪个方法


## Chapter 7 Single-Dimensional Arrays

1. Sort Method
``` java {.line-numbers}
double[] numbers = {6.0,4.4,1.9,2.9,3.4,3.5};
java.util.Arrays.sort(numbers);//默认从小到大排序
char[] chars = {'a','A','4','F','D','P'};
java.util.Arrays.sort(chars,0,3);//对从chars[0]到char[3-1]的部分排序
```

## Chapter 9 Objects and Classes

1. The Date Class
Date();
Date(elapseTime: long);
toString():String :return a string representing the date and time
getTime():long :return the numbers of mileseconds since January 1,1970,GMT
setTime(elapseTime:long):void :Set a new elapse time in the object

2. The Random Class
Random();
Random(seed:long);
nextInt():int 返回一个随机的int值
nextLong():long
nextDouble():double
nextFloat():float
nextBoolean():boolean

3. 实例方法和静态方法的区别
实例方法可以调用实例方法和静态方法，还能访问两个数据域。
静态方法只能在静态的域里。

4. Array of Objects
``` java
Circle[] circleArray = new Circle[10];
```

## Chapter 10 Thinking in Objects

1. 包装类(Wrapper Classes):使用包装类可将基本数据类型作为对象处理.
   1. Boolean
   2. Integer
   3. Character
   4. Long
   5. Short
   6. Float
   7. Byte
   8. Double
2. Mpdifying Strings in the StringBuilder
   1. example
        ``` java {.line-numbers}
        stringBuilder = new StringBuilder("Welcome to");
        stringBuilder.append("Java");
        ```


## Chapter 11 Inheritance and Polymorphism

1. super类
   不同于属性和普通方法，父类的构造方法不会被子类继承，他们只能使用关键字super从子类的构造方法中调用。

   调用父类构造方法的语法是：super或super(arguments)

   注意：该语句必须出现在子类构造方法的第一行，这是显示调用父类构造方法的唯一方式

   ``` java {.line-numbers}
   public CircleFromSimpleGeometricObject(double radius,String color,boolean filled){
    super(color,filled); //调用父类的构造方法
    this.radius = radius;
   }
   ```

2. 构造方法类：先调用父类的构造方法再调用子类的构造方法

3. Overriding(重写) Methods in the Superclass
   和C++不同，这里重写父类方法直接写在子类里重写就可以了，不需要父类有virtual关键字，子类方法会自动覆盖父类方法

4. Polymorphism(多态)
   Polymorphism means that a variable of a super type can refer to a subtype object. A class defines a type. Atype definedbyasubclass is called a subtype, and a type defined by its superclass is called a supertype. Therefore,you can say that Circle is a subtype of GeometricObject and GeometricObject is a super type for Circle.(子类型和超类型,关键词extends)

5. Method Matching vs. Binding
   Matching a method signature and binding a method implementation are two issues. The compiler finds a matching method according to parameter type, number of parameters, and order of the parameters at compilation time. A method may be implemented in several subclasses.The Java Virtual Machine dynamically binds the implementation of the method at runtime.(编译器根据参数类型，参数个数和参数顺序找到合适的方法，一个方法可以在多个子类中实现，JVM在运行时会动态绑定方法的实现)

6. Casting from Superclass to Subclass:支持父类到子类（超类到子类）的隐式转换。
   
7. The **instanceof** Operator
   测试对象是否是类的实例
   ``` java {.line-numbers}
   Object o = new Circle();
   /* Perform casting if o is an instance of Circle */
   if(o instanceof Circle){
    System.out.println("The circle diameter is " + ((Circle) o).getDiameter());
   }
   ```

8. Accessibility Summary
   | members in a class | same class | same package | subclass | different package |
   | ---- | ---- | ---- | ---- | ---- |
   | public | √ | √ | √ | √ |
   | protected | √ | √ | √ |  |
   | default | √ | √ |  |  |
   | private | √ |  |  |  |


## Chapter 12 Exception Handling and Text IO
1. checked exceptions(必检异常)
   意味着编译器会强制程序员检查并通过try-catch块处理他们，或者在方法头进行声明
   构造异常对象:
   ``` java
   throw new ArithmeticException("Divisor cannot be zero");
   ```

   try/catch块：
   ``` java {.line-numbers}
   Scanner input = new Scanner(System.in);
   System.out.println("Enter two integers:");
   int number1 = input.nextInt();
   int number2 = input.nextInt();

   try{
    int result = quotient(number1,number2);
    System.out.println(number1 + "/" + number2 + "is " + result);
   }
   catch (ArithmeticException ex){
    System.out.println("Exception an Integer " + "cannot be divided by zero.");
   }
   ```

   finally语句通常放在try/catch语句后，无论一场是否产生，finally字句总会被执行

2. Text I/O
   调用printWriter的构造方法创建一个新文件，调用该构造方法可能会抛出一个I/O异常，Java强制要求要编写代码来处理这类异常，因此，简单起见只需在方法头声明中申明throws IOException.
   ``` java {.line-numbers}
   public class WriteData{
    public static void main(String[] args) throws java.io.IOEexception{
        if(file.exists()){
            System.out.println("File already exists");
            System.exit(1);
        }

        // Create a file
        java.io.PrintWriter output = new java.io.PrintWriter(file);

        // Write formatted output to the file
        output.print("John T smith");
        output.println(90);
        output.print("Eric K Jones");
        output.println(85);

        // Close the file(必须要关闭文件，否则数据不能正确的保存在文件中)
        output.close();
    }
   }
   ```


## Chapter 13 Abstract Classes and Interfaces

1. Define an Interface(定义一个接口)
   一个接口可以继承多个接口，一个类可以实现多个接口，一个类只能继承一个类
   ``` java {.line-numbers}
   package java.lang;
   public interface Comparable<E>{
    public int compareTo(E o);
   }
   ```
   
   Comparable接口是一个范型接口，在实现这个接口时，范型类型E被替换成一个具体的类型。

2. The Cloeable Interfaces(可克隆接口)
   Cloneable接口是一个空接口，一个方法体为空的接口称为标记接口(marker interface),它用来表示一个类拥有某些希望具有的特征.

   **一个对象能被克隆，通常需满足如下两个条件**
   1. 实现Cloneable接口，使拷贝合法，避免抛出CloneNotSupportedException
   2. 重写clone方法

3. 浅拷贝和深拷贝
   1. 浅拷贝(Shallow Copy):拷贝对象时仅仅拷贝对象本身，包括对象中的基本变量，而不拷贝对象包含的引用指向的对象。
   2. 深拷贝(Deep Copy):不仅拷贝对象本身，而且拷贝对象包含的引用指向的所有对象


## Chapter 14 JavaFX Basics

1. 在一个窗体中显示按钮
   ``` java
   import javafx.application.Application;
   ```
