# java

### 构造方法
```java
java 构造方法必须与类名一致，一个类可以有多个构造方法
```
### 源文件声明规则
```java
局部变量：在方法、构造方法或者语句块中定义的变量被称为局部变量。变量声明和初始化都是在方法中，方法结束后，变量就会自动销毁。
成员变量：成员变量定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化。成员变量可以被类中的方法、构造方法和特定类的语句块访问。
类变量：类变量也声明在类中，方法体之外，但必须声明static类型。
1.一个源文件中只能有一个public类，可以有多个非public类
2.源文件的名称应该和public类名称保持一致
3.如果一个类定义在某个包中，package语句应该放在源文件的首行
4.如果源文件包含import语句，那么应该放在package语句和类定义之间，如果没有package语句，那么import语句应该放在源文件中最前面

```
### 变量和常量、类声明规范
```java
  类成员变量：首字母小写和驼峰原则（monthSalary）
  局部变量：首字母小写和驼峰原则
  常量：大写字母和下划线原则（MAX_VALUE）
  类名：首字母大写和驼峰原则（Man，GoodMan）
  方法名：首字母小写和驼峰原则（run(),runRun()）
```

### 数据类型
```java
1.byte
2.short
3.int
4.long
5.float
6.double
7.boolean
8.char
常量 final
```

### 方法重写
```java
1、方法名、形参列表相同
2、返回值类型和声明异常类型，子类小于等于父类
3、访问权限，子类大于等于父类
```
### super父类对象引用
```java
 1、构造方法的第一句总是super()来调用父类对应的构造方法。所以流程是：先向上追溯到 object,然后在依次详细执行类的初始化块和构造方法，知道子类为止。（静态初始化块调用顺序和构造方法调用顺序一样）
public class SuperTest {
    public static void main(String[] args) {
            System.out.println("开始创建ChildClass对象");
            ChildClass f0 = new ChildClass();
  }
}
class FatherClass{
       public FatherClass(){
           super(); //系统默认会加上
            System.out.println("这是父类");
  }
}

class ChildClass extends FatherClass{
    public ChildClass(){
        super();//系统默认会加上
        System.out.println("这是子类");
  }
}
```
### 封装
```java
1、private：私有的，只能自己类访问
2、default:同一个类中和一个包中的类能访问
3、protected:同一个类中，一个包中，子类中能访问
4、public：所有类都能访问
```
### 多态
```java
多态指的是同一个方法调用，由于对象不同可能会有不同的行为。现实生活中，同一个方法，具体实现会完全不同。
多态的要点：
1、多态是方法的多态。不是属性的多态（多态与属性无关）
2、多态的存在要有三个必要条件：继承、方法重写，父类引用指向子类对象。
3、父类引用指向子类对象后，用该父类引用调用子类重写的方法，此时多态出现了
例如：
 public static void main(String[] args) {
    Cat cat = new Cat();
    animal(cat);
    Animal dog = new Dog();
    animal(dog);

  }
  static void animal(Animal a){
    a.shout();
  }
}

class Animal{
    public void shout(){
        System.out.println("叫了一声");
  }
}

class Cat extends Animal{
    public void shout(){
        System.out.println("喵喵喵");
  }
}

class Dog extends Animal{
    public void shout(){
        System.out.println("汪汪汪");
  }
}
```
### final
```java
1、修饰变量：被修饰的变量不可改变，一旦赋了值就不能被重新赋值
2、修饰方法：该方法不能被子类重写。但是可以被重载
3、修饰类：修饰的类不能被继承
```
### 数组
```java
1、长度是确定的。数组一旦被创建，它的大小就是不可改变的
2、其元素必须是相同类型，不允许穿线混合类型
3、数组类型可以是任何数据类型，包括基本类型和引用类型
声明数组:  type[] name
            或者
          type name[]
          
例如：int[] arr = new int[10]
数组的初始化方式总共三种：静态初始化、动态初始化、默认初始化
静态初始化：int[] a = {1,2,3}
            User[] b = {new User(1,"哈哈")，new User(2,"呵呵")}
默认初始化：int[] a = new int[2] //默认给数组的元素进行赋值，int默认值0，string默认值 null 

动态初始化: int[] a = new int[2]
          a[0] = 1;
          a[1] =2;
```
### foreach
```java
foreach 只能读取数组的值，不能修改数组的值
例如：

int[] a = {1,2,3}
for(int m:a){
    System.out.println(m); 
}
```
