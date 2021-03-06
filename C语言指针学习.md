# C语言的指针学习

## 基本类型指针

1. 初识指针

   - 代码以及说明：![未命名图片](D:\桌面\tutu\未命名图片.png)

   - 强调：int * 指的是定义一个指针类型的变量，并不是取值

   - 笔记：1. 指针就是地址，地址就是指针

     ​           2.地址就是内存单元的编号

     ​           3.指针变量是存放地址的变量

     ​           4.指针和指针变量是两个不同的概念

     ​			5. 但是要注意：通常我们叙述时会把指针变量简				称指针，实际它们含义不一样

     

2. 指针作用：

   表示一些复杂的数据结构

   快速的传递数据

   使函数返回一个以上的值

   能直接访问硬件

   能够方便的处理字符串

   是理解面向对象语言中引用的基础

   总结：指针是 C 语言的灵魂

   

   

3. 常见错误

   - 

     

     ```
     #include <stdio.h>
     
     int main()
     
     {
     
     int *p; 
     
     printf("%p\n",p);//p是垃圾值 
     
     printf("%d\n",*p);//*p未知，能和p扯上关系 
     
     int i=3;
     
     *p=i; //理论上不成立，devc++有点bug 
     
     printf("%d/n%p",*p,&i);/*p的空间是本程序的，所以本程序可以访问p的内容，
     
                               但是 如果p内部是垃圾值，所以不能访问*p内容 
     
                               因为*q所代表的内存单元的控制权限并没有分配给本程序*/ 
     return 0;
     }
     ```
     
- 
  
  ```
     #include <stdio.h>
     void change1(int a,int b)//不能完成互换功能 ,形式参数不会影响实际参数 
     {
     int t;
     t=a;
     a=b;
     b=t;return;
     } 
     void change2(int *p,int *q)			//p,q存放的是a,b的地址，函数里交换的是p,q存放的内容 
     {
     int *t;
     t=p;
     p=q;
     q=t;
     }
     void change3(int *p,int *q)//
     {
     int t;        //如果互换ab,就定义int t;但定义int *t也可，只是语法错误 
     t=*p;
     *p=*q;
     *q=t;
     }
     int main()
     {
     int a=3;
     int b=4;
     //change1(a,b);
     //change2(&a,&b);
     change3(&a,&b); 
     printf("a=%d,b=%d",a,b);
     return 0;
     }					//互换整型的值，他们的地址不能轻易改变 
  ```
  
     
  
4. 如何通过被调函数修改主调函数普通变量的值

   - 实参必须为该普通变量的地址
   - 形参必须为指针变量
   - 在被调函数中通过 *形参名 的方式就可以修改主调函数相关变量的值

   - 没有指针，无法很好通过函数互换主函数两个变量的值

     

## 指针和数组

### 	指针和一维数组

1. 数组名
   - 一维数组名是个指针常量，她存放的是一维数组第一个元素的地址

2. 下标和指针关系
   - 如果p是个指针变量，则p[i]=*(p+1)
   - 




