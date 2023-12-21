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
1. **Modularity(模块化)**: The source code for anobject canbewritten and maintained independentlyof thesourcecode for other objects. After it is created, anobjectcan be easily passed around insidethesystem.(对象的源代码可以独立于其他对象的源代码来编写和维护，创建后，对象可以轻易地在系统内传递)
2. **Information-hiding(信息隐藏)**: By interacting only with an object’s methods, the details of its internal implementation remain hidden from the outside world.
3. **Code re-use(代码复用)**: If an object already exists(perhapswritten by another software developer), you can use that object in your program. This allows specialists to implement, test, and debug complex, task-specific objects, which you can thentrust torun in your own code.
4. **Pluggability and debugging ease(可插拔性和调试简便性)**: If aparticularobject is found to be problematic, you can simply remove it from your application and plugin a different object as its replacement.
5. **JVM(Java Virtual Machine)**: java虚拟机
6. **JRE(Java Routine Environment)**: java类库
7. **JDK(Java Development Kit)**: java开发工具包


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

   实现Clonable接口的类标记为可克隆的，而且它的对象可以使用在Object类中定义的clone()方法克隆：
   ``` java {line.numbers}
   package java.lang;
   public interface Cloneable { 
   }
   ```
   Object类定义了一个clone方法，其方法头是：
   ``` java
   protected native Object clone() throws 
   CloneNotSupportedException;
   ```
   关键字native表示这个方法不是用Java写的，但它是在JVM中针对
   本地平台实现的。
   关键字protected限定方法只能在同一个包中或其子类中访问。通
   常其他类必须重写该方法并将它的可见性修改为public，这样重写的
   clone方法可以在任何一个包中使用
   Object类的clone方法完成了克隆对象的任务，实现浅拷贝。

   **一个对象能被克隆，通常需满足如下两个条件**
   1. 实现Cloneable接口，使拷贝合法，避免抛出CloneNotSupportedException
   2. 重写clone方法

3. 浅拷贝和深拷贝
   1. 浅拷贝(Shallow Copy):拷贝对象时仅仅拷贝对象本身，包括对象中的基本变量，而不拷贝对象包含的引用指向的对象。
   2. 深拷贝(Deep Copy):不仅拷贝对象本身，而且拷贝对象包含的引用指向的所有对象
   Exp:
   浅拷贝：
     House house1 = new House(1, 1750.50);
     House house2 = (House)house1.clone();
     Object类中的 clone 方法将原始对象的每个数据域复制给目标对象。如果一个数据域是基本类型，复制的就是它的值；
     如果一个数据域是对象，复制的就是其引用。例如，whenbuilt是DATE类，它的引用被复制给house2。
   深拷贝：
     House house1 = new House(1, 1750.50);
     House house2 = (House)house1.clone();
     house1==house2为假，house1.whenBuilt == house2. whenBuilt为假，即house1和house2包含2个不同的Date对象。

4. sort方法
   由于所有 Comparable 对象都有 compareTo 方法，如果对象是 Comparable 接口类型的实例的话，Java API 中的 
   java.util.Arrays.sort(Object [ ]) 方法就可以使用compareTo 方法来对数组中的对象进行比较和排序。
   The java.util.Arrays.sort(array) method requires that the elements in an array are instances of Comparable<E>.

5. Comparable方法
   Comparable接口定义了compareTo方法，用于比较对象
   ``` java {.line-numbers}
   // This interface is defined in 
   // java.lang package
    package java.lang;
    public interface Comparable<E> {
    public int compareTo(E o);
    }  
   ```
   Comparable接口是一个范型接口，在实现该接口时，范型类型E被替换成一种具体的类型。compareTo方法判断这个对象相对于给定对象o的
   顺序，并且当这个对象小于、等于或大于给定对象o时，分别返回负整数、0或正整数。

6. Interface v.s. Abstract class
   在接口中，数据必须是常量；在抽象类中，它可以拥有所有类型的数据；
   接口中的所有方法只有签名没有实现，而抽象类可以有方法的具体实现；
   所有类共享一个根，但接口没有单一的根，与类一样，接口也有定义类型；
   接口类型的变量可以引用实现该接口的类的所有实例。
   
## Chapter 14 JavaFX Basics

1. 在一个窗体中显示按钮
   ``` java
   import javafx.application.Application;
   ```

## 选择题库遇到的问题补充

1. final关键字
   1. 当用final修饰一个类时，表明这个类不能被继承。也就是说，如果一个类你**永远不会让他被继承**，就可以用final进行修饰。final类中的成员变量可以根据需要设为final，但是要注意final类中的所有成员方法都会被隐式地指定为final方法。
   2. 使用final方法的原因有两个。第一个原因是把方法锁定，**以防任何继承类修改它的含义**；第二个原因是效率。在早期的Java实现版本中，会将final方法转为内嵌调用。但是如果方法过于庞大，可能看不到内嵌调用带来的任何性能提升。在最近的Java版本中，不需要使用final方法进行这些优化了。
   3. 对于一个final变量，如果是基本数据类型的变量，则其**数值一旦在初始化之后便不能更改**；如果是引用类型的变量，则在对其初始化之后便不能再让其指向另一个对象。
   
2. Int超过范围不会报溢出错误
   An integer literal can be assigned to an integer variable as long as it can fit into the variable. A compilation error would occur if the literal were too large for the variable to hold. For example, the statement byte b = 1000 would cause a compilation error, because 1000 cannot be stored in a variable of the byte type.

3. true是一个Boolean Literal，不是和1相等的值
4. random(): Returns a random double value in the range [0.0, 1.0).
5. homework_1
   point and its distance to the center. Here are sample runs:  
   <output>
   The point is (-3.3878721143708708, 3.1409080280010944) and its distance to the center is 4.619846393950072
   <end output>
   <output>
   The point is (-0.14972878708817536, 4.986535034124079) and its distance to the center is 4.9887824522852995
   <end output>
   Answers:

   ``` java {.line-numbers}
   package com.itheima.demo1;

   import java.util.Random;

   public class homework01 {
       public static void main(String[] args) {
           //生成一个圆心为(0,0),半径为5的圆内的随机一点，并打印它到圆心的距离

          //生成一个random对象
          Random rd = new Random();
          //生成随机点坐标
          double x = (rd.nextDouble() * 10) - 5;
          double y = (rd.nextDouble() * 10) - 5;
          //计算到圆心距离
          double distance = Math.sqrt(x * x + y * y);
          //打印
          System.out.println("The point is (" + x + "," + y + ") and its distance to the center is " + distance);
       }
   }
   ```
6. homework_2
   Write a program that displays a menu as shown in the sample run. You can enter 1, 2, 3, or 4 for choosing an addition, subtraction, multiplication, or division test. After a test is finished, the menu is redisplayed. You may choose another test or enter 5 to exit the system. Each test generates two random single-digit numbers to form a question for addition, subtraction, multiplication, or division. For a subtraction such as number1 – number2, number1 is greater than or equal to number2.  For a division question such as number1 / number2, number2 is not zero.
   <Output>
   Main menu
   1: Addition
   2: Subtraction
   3: Multiplication
   4: Division
   5: Exit
   Enter a choice: 1<enter icon>
   What is 1 + 7? 8<enter icon>
   Correct

   Main menu
   1: Addition
   2: Subtraction
   3: Multiplication
   4: Division
   5: Exit
   Enter a choice: 1<enter icon>
   What is 4 + 0? 5<enter icon>
   Your answer is wrong. The correct answer is 4

   Main menu
   1: Addition
   2: Subtraction
   3: Multiplication
   4: Division
   5: Exit
   Enter a choice: 4<enter icon>
   What is 4 / 5? 1<enter icon>
   Your answer is wrong. The correct answer is 0

   Main menu
   1: Addition
   2: Subtraction
   3: Multiplication
   4: Division
   5: Exit
   Enter a choice:
   <End Output>
   
   Answers:
   ``` java {.line-numbers}
   package com.itheima.demo1;

   import java.util.Random;
   import java.util.Scanner;

   public class homework02 {
       public static void main(String[] args) {
           //口算题卡，自动生成两位数，给出加减乘除的运算菜单，用户输入计算结果，计算结果与正确答案比较并输出是否正确
           //循环内进行，提供循环推出的条件

           //创建输入和随机对象
           Scanner sc = new Scanner(System.in);
           Random rd = new Random();
           //创建选择菜单
           int choice;
           do {
               System.out.println("Menu:");
               System.out.println("1. Addition");
               System.out.println("2. Subtraction");
               System.out.println("3. Multiplication");
               System.out.println("4. Division");
               System.out.println("5. Exit");
               System.out.print("Enter your choice: ");
               choice = sc.nextInt();
               while (choice > 5 || choice < 1) {
                   System.out.println("输入非法数字，请再次选择:");
                   choice = sc.nextInt();
               }
               int num1 = rd.nextInt(200);
               int num2 = rd.nextInt(200);
               //switch语句进行四种情况的分别处理
               switch (choice) {
                   case 1:
                       int ans1 = num1 + num2;
                       System.out.println(num1 + "+" + num2 + "=?");
                       int userAns1 = sc.nextInt();
                       if (ans1 == userAns1) {
                           System.out.println("答案正确！");
                       } else {
                           System.out.println("输入错误！正确答案是：" + ans1);
                       }
                       break;
                   case 2:
                       int ans2 = num1 - num2;
                       System.out.println(num1 + "-" + num2 + "=?");
                       int userAns2 = sc.nextInt();
                       if (ans2 == userAns2) {
                           System.out.println("答案正确！");
                       } else {
                           System.out.println("输入错误！正确答案是：" + ans2);
                       }
                       break;
                   case 3:
                       int ans3 = num1 * num2;
                       System.out.println(num1 + "*" + num2 + "=?");
                       int userAns3 = sc.nextInt();
                       if (ans3 == userAns3) {
                           System.out.println("答案正确！");
                       } else {
                           System.out.println("输入错误！正确答案是：" + ans3);
                       }
                       break;
                   case 4:
                       System.out.println(num1 + "/" + num2 + "=?");
                       int userAns4 = sc.nextInt();
                       if (num1 / num2 == userAns4 && num2 != 0) {
                           System.out.println("答案正确！");
                       } else {
                           System.out.println("输入错误！正确答案是：" + num1/num2);
                       }
                   default:
                       break;
               }
           } while (choice != 5);

       }
   }
   ```
7. homework_3
   Write a method that parses a decimal number into a binary number as a string. The method header is:
   public static String decimalToBinary(int value)
   Write a test program that prompts the user to enter a decimal integer value and displays the corresponding binary value.
   <Output>
   Enter an integer: 1451
   The binary value is 10110101011
   <End Output>
   Answers:
   ``` java {.line-numbers}
   package com.itheima.demo1;

   import java.util.Scanner;

   public class DecimalToBinary {
       public static void main(String[] args) {
           //输入一个十进制整数，并输出它的二进制形式，以字符串的类型
           Scanner sc = new Scanner(System.in);
           System.out.println("输入一个十进制整数：");
           int decimal = sc.nextInt();
           System.out.println("它的二进制形式为："+decimalToBinary(decimal));
       }
       public static String decimalToBinary(int decimal){
           if(decimal == 0){
               return "0";
           }
           StringBuilder sb = new StringBuilder();
           while(decimal!=0){
               int temp = decimal%2;
               sb.insert(0,temp); //在字符串索引为0的位置更新字符
               decimal/=2;
           }
           return sb.toString();
       }
   }
   ```

