- **this**:代表当前类的对象的引用(引用也就是创建对象时所接受的变量，哪一个对象调用的方法，方法中的this就代表的是哪一个对象；**this本质就是当前类的对象的地址值**)

- **栈内存溢出**：当前情况(方法1中调用方法2(方法2中调用方法1)，没有出口导致栈内存溢出)

- 权限修饰符：修饰**成员方法**和**成员变量**

  ```java
  // private：范围是所在*本类*可以访问
  // default：范围是*所在包*可以访问
  // protected：范围是*所在包*外加一个*不同包的子类*可以进行访问
  // public：
  ```

- 对成员方法加入修饰符的作用及**思想**(一个类的方法不能被其他类访问但是还要被调用(不被直接访问)，就可以将这个方法私有化并让这个类的另一个方法调用这个方法(可以被间接访问，这样可以保护私密数据))![image-20200929100143655](https://github.com/MAYI-XINGKONG/JavaNotes/blob/master/images/day05-01.png?raw=true)

- 方法重载的好处：不需要记忆过多繁琐的方法名字(例子：Println)

- 构造方法的作用：

  ![image-20200929111733992](https://github.com/MAYI-XINGKONG/JavaNotes/blob/master/images/day05-02.png?raw=true)

  ```java
  /*
  	1、本质作用是用于创建对象（【例子：new Student();】new：开辟空间，生成地址值；Student()：调用系统默认的无参或自己定义的(Student(Strung name,int age))有参构造方法）
  	2、还可以在程序执行过程中对成员变量进行初始化
  */
  ```

- 封装：（是一种思想）隐藏实现细节，仅对外暴露公共的访问方式

  ```
  在代码中的体现：
  		1、将代码抽取到方法中，这是对功能的一种封装
  		2、将属性抽取到类中，是对数据的一种封装
  ```

- JavaBean类：(通常一个项目会将这种类放在同一个包(domain)下)![image-20200929115011502](https://github.com/MAYI-XINGKONG/JavaNotes/blob/master/images/day05-03.png?raw=true)

- 对象在方法中作为参数传递，传递的实际上是对象多记录的地址值

- 链式编程：如果一个方法的返回是一个对象的话，对象就可以继续向下.方法

  ```java
  jframe.getcomentpane().add();
  jframe.getcomentpane()//返回值是一个对象，所以可以继续往后调用方法
  ```

- 