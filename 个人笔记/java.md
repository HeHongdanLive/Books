# 一些奇奇怪怪的java笔记
1. java基本数据类型有哪些，int， long占几个字节      
   |C类型	   |    32	    |              64      |
    |char	          |             1	            |          1
    short int	      |            2	       |               2
    int	   |                4	          |            4
    long int	           |        4	   |                   8
    long long int	      |             8	      |                8
    char*	    |               4	         |             8
    float	          |         4	         |             4
    double	        |           8	          |            8
2. == 和 equals有什么区别
	1. ==是判断两个变量或实例是不是指向同一个内存空间 
equals是判断两个变量或实例所指向的内存空间的值是不是相同 
	2. ==是指对内存地址进行比较 
equals()是对字符串的内容进行比较
	3. ==指引用是否相同 
equals()指的是值是否相同
![Alt text](https://pic3.zhimg.com/80/v2-d9dc4362f0334802413e3a3ff2f53c2e_hd.png "Optional title")
3. hashcode 和 equals作用
	hashcode()方法返回一个int数，在Object类中的默认实现是“将该对象的内部地址转换成一个整数返回”，“如果两个对象不相同，他们的hashcode可能相同”
- 如果两个对象equals，Java运行时环境会认为他们的hashcode一定相等。 
-  如果两个对象不equals，他们的hashcode有可能相等。 
- 如果两个对象hashcode相等，他们不一定equals。 
- 如果两个对象hashcode不相等，他们一定不equals。
4. new String创建了几个对象
- String s = new String("xyz");
首先在string池内找，找到？不创建string对象，否则创建， 这样就一个string对象
遇到new运算符号了，在内存上创建string对象，并将其返回给s，又一个对象
所以总共是2个对象
5. 位运算符的一些计算
- 前缀自增自减法(++a,- -a): 先进行自增或者自减运算，再进行表达式运算。
- 后缀自增自减法(a++,a- -): 先进行表达式运算，再进行自增或者自减运算
6. java的拆装箱
- https://www.cnblogs.com/dolphin0520/p/3780005.html
> int -128~128
>Integer i = 10;  //装箱
int n = i;   //拆箱
7. compareable 和 compartor的区别
- compartor 外部实现,compareable 类内部实现
- 如果实现类没有实现Comparable接口，又想对两个类进行比较（或者实现类实现了Comparable接口，但是对compareTo方法内的比较算法不满意），那么可以实现Comparator接口，自定义一个比较器，写比较算法。
- 实现Comparable接口的方式比实现Comparator接口的耦合性 要强一些，如果要修改比较算法，要修改Comparable接口的实现类，而实现Comparator的类是在外部进行比较的，不需要对实现类有任何修 改。从这个角度说，其实有些不太好，尤其在我们将实现类的.class文件打成一个.jar文件提供给开发者使用的时候。实际上实现Comparator 接口的方式后面会写到就是一种典型的策略模式。


8. java引用和传递
- https://www.jianshu.com/p/bb68f74c3471
