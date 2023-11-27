# Array
## 快速入门
### 定义
``` java {.line-numbers}
double[] hens = {3,5,1,3.4,2,50};
```
遍历数组
``` java {.line-numbers}
double totalWeight = 0;
for(int i = 0;i <6;++i){
    totalWeight += hens[i];
}
System.out.println("总体重= "+ totalWeight);
```
## 使用事项
### 数组赋值
数组在默认情况下是引用传递，赋的是地址，赋值方式为引用赋值
``` java {.line-numbers}
int[] arr1 = {1,2,3};
int[] arr2 = arr1; //把arr1的值赋给arr2
arr2[0] = 10;
//查看arr1的值
System.out.println("======arr1的元素======")；
for(int i = 0;i < arr1.length;i++){
    System.out.println(arr1[i]);
}
```
## 数组应用
### 数组反转
``` java {.line-numbers}
public class ArrayReverse{
    //编写一个main方法
    public static void main(String[] args){
        //定义数组
        int[] arr = {11,22,33,44,55,66};
        //反转三次
        for(int i = 0; i < arr.length/2;++i){
            int temp  = arr[i];
            arr[i] = arr[arr.length - i - 1];
            arr[arr.length - i - 1] = temp;
        }
    }
}
```
另法：创建一个新数组存储反转后的数组
### 数组扩容
方法：
``` java {.line-numbers}
public class ArrayAdd{
    //编写一个main方法
    public static void main(Strong[] args){
        //定义一个初始数组，定义一个新的数组容量为原来的容量+1，依次将原数组的元素拷贝新数组
        //新的元素放到最后一个元素位置
        int[] arr = {1,2,3};
        int[] arrNew = new int[arr.length+1];
        for(int i = 0;i<arr.length;i++){
            arrNew[i] = arr[i];
        }
        arrNew[arrNew.length - 1] = 4;
        //让arr指向arrNew
        arr = arrNew;
        System.out.println("=====扩容后元素情况=====");
        for(int i = 0;i< arr.length;i++){
            System.out.print(arr[i] + "\t");
        }
    }
}
```
实例展示：
``` java {.line-numbers}
import java.util.Scanner;
public class ArrayAdd{
    //编写一个main方法
    public static void main(Strong[] args){
        //定义一个初始数组，定义一个新的数组容量为原来的容量+1，依次将原数组的元素拷贝新数组
        //新的元素放到最后一个元素位置
        Scanner myScanner = new Scanner(System.in);
        int[] arr = {1,2,3};
        do{
            int[] arrNew = new int[arr.length+1];
            for(int i = 0;i<arr.length;i++){
                arrNew[i] = arr[i];
            }
            System.out.println("请输入你要添加的元素");
            int addNum = myScanner.nextInt();
            arrNew[arrNew.length - 1] = addNum;
            //让arr指向arrNew
            arr = arrNew;
            System.out.println("=====扩容后元素情况=====");
            for(int i = 0;i< arr.length;i++){
                System.out.print(arr[i] + "\t");
            }
            //问用户是否继续
            System.out.println("是否继续添加 y/n");
            char key = myScanner.next().charAt(0);
            if(key == 'n'){
                break;
            }
        }while(true)

    }
}
```
### 数组缩减
有一个数组{1，2，3，4，5}，可以将该数组进行缩减，提示用户是否继续缩减，每次缩减最后那个元素，当只剩下最后一个元素，提示不能再缩减


## 二维数组