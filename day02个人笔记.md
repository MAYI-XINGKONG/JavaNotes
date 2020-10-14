## **个人云笔记——Day02**

- 关键字的识别：字母都是小写、颜色可与class作比较。[一般高级编辑器对代码颜色都有区分（高亮显示），找到与class等关键字颜色相同的英文单词]

- 常量：在代码执行过程中，不会发生改变的值叫做常量

- 布尔常量单独使用是没有意义的，可在运算符等方面进行应用

  ```java
  System.out.println(10 > 20);//显示false
  ```

  

- 二进制...

- 代码中所编写的数据，默认都是十进制（如果想要输入其他进制，要加入相应的书写格式 [二进制：0b开头，后加0或1；八进制：0开头，后加0-7；十六进制：0x开头，后加0-f]）“注意：以上规则符合jdk7后续版本”

- 编写数值时，不建议以0开头，因为jdk会默认是八进制。

- 变量就是内存中的存储空间  [空间中存储的是经常发生改变的数据]

- 变量前面有数据类型，这才是定义变量

- 断点操作：<img src="C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200924105204142.png" alt="image-20200924105204142" style="zoom: 150%;" />

- 变量在使用之前必须赋值

- 标识符：自己给变量，类等起的名字，都是标识符；标识符有着自己的命名规则（小驼峰[对应变量和方法的命名]、大驼峰[对应类的命名]）

- byte：取值范围（-128~127）

- 数据类型使用思路：如果今后定义整数类型，首选int[ Java所有整数默认类型 ]，如果发现int类型装不下则换成long[ 记得加L ]；如果定义的是小数类型变量，首选double[ Java所有小数默认类型 ]

- 有的时候定义long类型的变量，没有加L也可以编译通过，为什么呢

  ```
  long num = 12;
  先看等号右边，12是一个整数，所有正是默认都是int类型.
  代码是int类型给long类型赋值，属于隐式转换
  ```

  

- 键盘录入：

  ```java
  Scanner sc = new Scanner(System.in);
  int num = sc.nextInt();//定义一个整型变量-num来接收一个整数
  String str = sc.next();//定义一个字符串变量-str来接收一个字符串
  ......
  System.out.println(num);
  System.out.println(str);
  ```

- 运算符

  ```
  /:取整(5/2=3；5.0/2=2.0)
  %:取余(5%2=1；5.0%2=1.0)
  ```

- 数字拆分规律![image-20200924162146387](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200924162146387.png)

- Ctrl+alt +L：格式化代码

- 字符串拼接![image-20200924170259675](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20200924170259675.png)