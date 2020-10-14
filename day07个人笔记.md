- 数组中的数据类型一致不要理解过于死板，要结合隐式转换使用

  ```
  比如int数组中可以存储int类型或者是byte类型等比int类型取值范围小的类型的数据
  但是建议存储的一组数据的数据类型一致
  ```

- 什么时候使用数组![image-20201007085226173](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20201007085226173.png)

- 数组初始化的简化格式仅仅只是简化了书写格式，编译时系统会自动帮我们加上new关键字（细节）

- 数组遍历是指将数组所有的内容取出来，是一个过程，你可以将取出来的数据进行各种操作，不只是局限为打印操作

  ```java
  //arr.fori + 回车
  //arr[i]:在循环中代表每一个元素
  //i:在循环中代表的是每一个元素的下标索引
  ```

- null只能赋值给引用数据类型，若赋值给基本数据类型则会报错！！

- 空指针异常：![image-20201007111702786](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20201007111702786.png)

- 用亦或‘^‘实现数据交换*![image-20201007145017358](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20201007145017358.png)

- 二维数组的反转逻辑代码

  ```java
  public static void main(String[] args){ 
      int[][] arr = new int[][]{
      	{11,22,33},
      	{44,55,66},
      	{77,88,99}
  	};
      //开始写反转逻辑
      for(int i = 0; i < arr.length; i++){
          int start = 0;
          int end = arr.length - 1;
          for(; start < end; start++,end--){
              int temp = arr[i][start];
              arr[i][atart] = arr[i][end];
              arr[i][end] = temp;
          }
      }//fori
  
  }
  ```