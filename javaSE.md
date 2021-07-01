~~~java
1.
九九乘法表：
四个方向，八种情况，1*1和9*9只能在两锐角处：
 //		***
//		**
//		*右上角是1*1
		for(int i=1;i<10;i++) {
			for(int j=9;i<=j;j--) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		***
//		**
//		*右上角是9*9
		for (int i = 9; i >0; i--) {
			for (int j = 1; i>=j; j++) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		   *
//		  **
//		 ***又上是1*1
		for (int i = 1; i < 10 ;i++) {
			for (int j = 9; j >0; j--) {
				if(i<j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
				}
				System.out.println();
			}
//		   *
//		  **
//		 ***右上是9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 1; j < 10; j++) {
				if(i>j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		***
//		 **
//		  *左上1*1
		for (int i = 1; i < 10; i++) {
			for (int j = 1; j < 10; j++) {
				if(i>j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		***
//		 **
//		  *左上9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 9; j > 0; j--) {
				if(i<j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		*
//		**
//		***左上1*1
		for (int i = 1; i < 10; i++) {
			for (int j = 1; i>=j; j++) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		*
//		**
//		***左上9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 9; i<=j; j--) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
2.判断是否是质数
    两种方法：（1）标签法（2）break
break法:
    for(int i=1;i<=100;i++) {//对1到100的数进行遍历
			int j=2;
			for(;j<i;j++) {
				if(i%j==0) {//该数存在一个可以被整除的数
					break;//跳出
				}
			}
			if(i==j) {//如果没有存在一个可以被整除的数跳出循环的，i一定等于j
                System.out.println(i+"是质数");
            }
    }
标签法：
    //定义一个变量让其从1跑到100
    for (int n = 1; n <=100; n++) {
        //判断当前n是不是质数
        boolean b=true;//定义一个变量 作为标签
        //使用循环让一个变量m从2跑到n/2
        for (int m =2; m <=n/2; m++) {
            //循环判断m是否除尽n
            if(n%m==0) {
                b=false;//如果n被m除尽 就更改标签的值
            }
        }
        //循环完后 通过判断标签的值是否更改 来判断n是否被m除尽过  进而判断n是不是质数
        if(n!=1 && b==true) {
            System.out.println("n==="+n+",是质数！！");
        }
    }
3.获取所有的水仙花数：
// 三位数  各个位数的值的三次方之和等于此数
//使用循环 把所有的三位数跑完
int n=100;
while(n<1000) {
    //判断当前n是不是水仙花数
    //获取当前n各个位数的值
    int a=n/1%10,b=n/10%10,c=n/100%10;
    //获取更改位数值的三次方之和
    int sum=a*a*a+b*b*b+c*c*c;
    //判断sum是不是等于当前n
    if(sum==n) {
        System.out.println(n+"是水仙花数！");
    }
    n++;//迭代语句
}
4.获取1到10000内的所有完数
~~~

# Dos

cd子文件夹  ：：：change directory 进入当前目录下一个文件夹

dir                 ：：：directory显示当前文件夹下的所有子文件夹

cd/                 ：：：退到根目录下

cd..                 ：：：后退一步

盘符				：：：进入指定盘

tab键			：：：自动补齐

# Java相关软件

## jvm

java virtual machine

虚拟机：把电脑的所有组件分割一部分，组成一个整体专门用于运行java程序。

​			：java.exe

## jre

java runtime environment

java运行环境：给Java程序提供运行的平台
					   ：jre=jvm+基础类库（提高编程效率 java大师提供的一些Java小零件）

安装：客户（软件的使用者）

## jdk

java development kits

java开发工具包：Java程序的开发者安装的软件

​							：jdk=jre+开发工具（javac.exe+javadoc.exe)

安装：开发者

## 配置环境变量

配置环境变量：把jdk安装目录的bin包写入环境变量path中

为什么配置环境变量：在任意位置都能运行java.exe和javac.exe

配置环境变量的步骤：

1 复制jdk的bin 包的目录  C:\Program Files\Java\jdk1.8.0_131\bin

2 编辑环境变量path

​    我的电脑--右键属性--高级系统配置--环境变量--系统变量--path--编辑

3 验证

​          重新打开一个命令行：在任意目录输入java和javac

# 编译：根据java源文件 生成java字节码文件

编译工具：javac.exe编译器

编译准备：在命令行把目录切到源文件所在目录下

编译命令：javac源文件名.java

编译作用：对源文件进行语法检查+生成类名.class字节码文件

# 运行：运行java程序

运行工具：java.exe虚拟机

运行准备：在命令行把目录切到字节码文件所在目录下

运行命令：java 类名

运行结果：把打印输出语句的内容打印到命令行中

1.无须添加.class后缀。
 2.main函数的args直接在命令后添加即可，空格隔开。例如：java ZzTest param1 param2。
 3.若有包名，则需要有同样包路径的父文件夹，并在所有包之外的上一级执行该类。
  如ZzTest.class文件，包名路径package zz，存放在D:\下，
  则需要有D:\zz文件夹，把.class文件放在D:\zz文件夹下，
  在D:\路径下执行java zz.ZzTest。
  或者在编译时添加d参数，

``` java
javac -encoding utf-8 -d . xxx.java
```

，编译后就会自动创建包路径的文件夹，随后直接

``` Java
java package1.package2.xxx 
```

# 语法之标示符(标识符)

**标示符：名字**

**标示符作用：和同类以区分+方便调用**

**标示符命名规则：违反就是语法错误**

* 由数字 字母 下划线 美元符号 组成
* 不能以数字开头
* 不能是java关键字
* 区分大小写

**标示符命名规范：程序员写代码的习惯 违反语法不错 但代码读起来很难受**

* 尽量增加可读性
* 类名：所有单词首字母大写

​      包名：域名倒写 所有字母小写

# 语法之数据类型

数据类型：对数据进行分类

数据：所有有价值的信息

先按数据的性质分类、再按数据所占空间大小分类

## 整数类型：没有小数点的数字

### 字节型：byte

* java存储数据的基本单位（计算机存储数据的基本单位bit（字节），一个二进制）
* 1byte=8bit
* byte取值范围[-128,127]

### 短整型：short

* 1short=2byte
* short取值范围[-32768,32767]

### 整型：int

* 1int=4byte
* int取值范围[-20亿，20亿]
* 整数数据默认是int类型

### 长整型：long

* 1long=8byte

* long类型的数据后面加 l/L

  1        int

  1L      long

## 浮点类型：有小数点的数字

### 单精度：float

* 1float=4byte
* float小数点后有效位数为6~8位
* float类型的数据后面加 f/F

### 双精度：double

* 1double=8byte

* double小数点后的有效位数为12位

* 浮点数据默认是double类型

  1.1    double类型

  1.1F    float类型

## 字符类型：所有的符号/文字

### 字符型：char

* 1char=2byte

* char类型的数据必须写在单引号中，单引号中有且只有一个字符

  1        int 

  1.0	double

  1L	long

  1.0f	float

  '1'	char

  '梁''贵''莹'	三个字符

## 布尔类型：结果只有true或false

### 布尔型：boolen

* 1boolen=1byte
* boolen数据只有两个值：true、false

**笔试题：描述八种基本数据类型及其所占的字节数**

# 常量和变量

## 常量：运算中值不能改变的数据

* 整数类型：1  1L
* 字符常量：'1'   'a'   '梁'    ‘ ’
* 浮点常量：1.1  1.1f
* 布尔常量：true false

## 变量：运算过程中值可以更改的数据

变量类似于代数中的未知数

* 定义变量格式：变量类型 变量名；
* 变量赋值格式：变量名=值；

**注意事项：**

* 同名的变量只能定义一次
* 变量必须先定义 再赋值 然后使用
* 变量赋的值的类型必须和变量的类型一致
* =：把右边的值赋值给左边的变量

# 数据类型转换

不同数据类型之间相互转换

~~~java
//数据类型精度表：byte--short--int(char)--long--float--double
//1 自动类型转换情况1：高精度变量=低精度数据;
//         编译器会自动的把低精度数据 转换为和变量一致的高精度数据 然后赋值
//如：float f=1;
//2 自动类型转换情况2：byte\short\char类型的变量=int常量值;
//         编译器会自定判断变量是否能装下右边的值  装的下就转换然后赋值  装不下就报错
//如：char c=98;
//强制类型转换：低精度变量=(低精度变量的类型)高精度数据;
//         注意：强制类型转换可能会出现数据丢失
//如：float f=(float)1.1;
~~~

编码集

~~~java
//编码集：计算机只识别01---只识别数字
//       人类语言是字符
//编码集：实现整数int和字符char之间的对应关系 
//编码集：ascii    所有的编码表兼容ascii表
//支持中文：GBK(一个序列：gb2312 gb18030)  utf-8  
//不支持中文：iso-8859-1  ascii
~~~

# 运算后结果的数据类型

byte short char 不能直接参加运算 需要自动提升为int

~~~java
byte b1=1,b2=1;
		short s1=1,s2=1;
		char c1=1,c2=1;
//		b1=b1+b2;//Type mismatch: cannot convert from int to byte
//		         //byte+byte=int
//		b1=b1+s1;//byte+short=int
//		b1=s1+c1;//short+char=int
~~~

运算后结果的数据类型取决于精度最高的数据

# 运算符

## 算术运算符

~~~
已有的算数运算符：+  -  *  /
java中特有的算数运算符：
			1：+	
			2：%
			3：++ --
~~~

* +作为加法号

~~~java
System.out.println(1+1);//加法运算
~~~

* +作为正号

~~~java
System.out.println(+1-(+2)-(-1));//表示正负
~~~

* +作为字符串连接符
* %求余 取模
* ++自增
* --自减

## 赋值运算符

已有的：= 把右边的值赋值给左边的变量

java特有的：+=	-=	/=	%=	*=

~~~java
int a=1,b=2;
a+=b;//等价于a=a+b;
System.out.println("a="+a+",b="+b);
byte b1=1,b2=2;
b1+=b2;//a+=b 完全等价于：a=(a的类型)(a+b);
~~~

## 比较运算符

结果是boolean类型的值

已有的：>	>=	<	<=

特有的：==	恒等号	判断两边的值是不是相等

​				!=    不等号	判断两边的值是不是不相等

~~~java
System.out.println(1>2);
System.out.println(1==2);
System.out.println(1!=2);
~~~

## 逻辑运算符

逻辑运算符：只能操作boolean数据 结果是boolean类型的数据

&	单与

&&	双与	and	两边只要有一个false 结果就是false

|	单或

||	双或	or	两边只要有一个true	结果就是true

^	异或	两边不同则为true	两边相同则为false

!	取反	非

~~~java
System.out.println("测试&");
System.out.println("true&false="+(true&false));//false
System.out.println("false&false="+(false&false));//false
System.out.println("true&true="+(true&true));//true
System.out.println("false&true="+(false&true));//false

int a=1,b=2,c=3;
System.out.println(a>b&&a>c);//判断a是最大的
System.out.println((a-b)*(a-c)<0);//a是中间值
System.out.println((a>b&&a<c)||(a>c&&a<b));//a是中间值
~~~

## 位运算符

（了解）

|	&	>>	<<

位运算符操作的是整数的二进制

0作为false

1作为true

~~~java
System.out.println("(15|2)="+(15|2));//15
System.out.println("(15&2)="+(15&2));//2
System.out.println("(15<<2)="+(15<<2));//60
System.out.println("(15>>2)="+(15>>2));//3
~~~

## 三元运算符

boolean表达式？值1：值2

如果boolean表达式结果位true 取值值1 否则取值值2

~~~java
int a,b,c;
a=1>2?3:4;
System.out.println("a="+a);
a=1;b=2;
int max1;//定义变量记录大值
max1=a>b?a:b;//给max1赋值大值

a=1;b=2;c=3;
max1=a>b?a:b;
max1=max1>c?max1:c;//max1取值三个中的大值
max1=(a>b)&&(a>c)?a:(b>c?b:c);
max1=a>b?(a>c?a:c):(b>c?b:c);

//怎么获取abc中的大值 小值  中间值
int max=(a>b)&&(a>c)?a:(b>c?b:c);
int min=(a<b)&&(a<c)?a:(b<c?b:c);
int mid=a+b+c-min-max;
~~~

# 流程控制之 选择结构

## if-else

if-else：单分支

~~~java
if(条件表达式) {条件表达式成立时 执行的代码块}
~~~

if-else: 双分支

~~~java
if(条件表达式) {表达式成立时 执行的代码块}else {表达式不成立时 执行的代码块}
~~~

if-else:多分支

~~~java
float score=(float)81.5;
if(score<60) {
    System.out.println("score="+score+",等级是不及格！");
}else if(score<70) {//隐藏条件score>=60
    System.out.println("score="+score+",等级是及格！");
}else if(score<80) {//隐藏条件score>=70
    System.out.println("score="+score+",等级是良好！");
}else {//隐藏条件 score>=80
    System.out.println("score="+score+",等级是优秀！");
}

if(score<60) {
    System.out.println("score="+score+",等级是不及格！");
}else if(score>=60&&score<70) {
    System.out.println("score="+score+",等级是及格！");
}else if(score>=70&&score<80) {
    System.out.println("score="+score+",等级是良好！");
}else {
    System.out.println("score="+score+",等级是优秀！");
}
~~~

## if-else的练习

~~~java
//1 判断一个数是不是水仙花数
// 水仙花数 必须是三位数：并且各个位数的值的三次方之和等于此数 
//如：153==1*1*1+5*5*5+3*3*3=1+125+27=
{
    int a;//定义变量记录要判断的数据
    a=372;//为了程序正常运行  赋值
    //对a进行判断  是不是水仙花数
    //判断是不是三位数
    if(a>=100&&a<=999) {
        //获取a各个位数的值
        int a1=a/1%10;  //获取个位数
        int a2=a/10%10; //获取十位数
        int a3=a/100%10;//获取百位数
        //获取三次方之和
        int  sum=a1*a1*a1+a2*a2*a2+a3*a3*a3;
        //判断是否等于a
        if(a==sum) {
            System.out.println(a+"是三位数 并且是水仙花数！");
        }else {
            System.out.println(a+"是三位数 但不是水仙花数！");
        }
    }else {
        System.out.println(a+"不是三位数 肯定不是水仙花数！");
    }
}
//2 判断一个年 是不是闰年
//情况1：可以被4整除  单不能被100整除
//情况2：可以被400整除
{
    //定义变量记录要判断的年
    int year=1900;
    if(year%4==0&&year%100!=0) {
        System.out.println(year+"年是闰年！");
    }else if(year%400==0) {
        System.out.println(year+"年是闰年！");
    }else {
        System.out.println(year+"年不是闰年！");
    }

    if((year%4==0&&year%100!=0)||(year%400==0)) {
        System.out.println(year+"年是闰年！");
    }else {
        System.out.println(year+"年不是闰年！");
    }
}

//3 根据月份判断季节：3 4 5春季 678夏 9 10 11秋 12 1 2 冬
{
    int month=11;//定义变量记录月
    if(month==3||month==4||month==5) {
        System.out.println(month+"月是春季！");
    }else if(month==6||month==7||month==8) {
        System.out.println(month+"月是夏季！");
    }else if(month>=9&&month<=11) {
        System.out.println(month+"月是秋季！");
    }else {
        System.out.println(month+"月是冬季！");
    }
}
//4 根据年龄和性别 判断称呼：
//小男孩  18 帅哥  35 叔叔  60爷爷
//小女孩       美女        阿姨      奶奶
{
    //定义变量记录年龄和性别
    int age=19;char sex='男';
    //有八种情况  使用多分支
    if(sex=='男'&&age<18) {
        System.out.println("sex="+sex+",age="+age+",称呼是小男孩！");
    }else if(sex=='男'&&age<35) {//隐藏条件：如果是男的  age>=18
        System.out.println("sex="+sex+",age="+age+",称呼是帅哥！");
    }else if(sex=='男'&&age<60) {
        System.out.println("sex="+sex+",age="+age+",称呼是叔叔！");
    }else if(sex=='男') {
        System.out.println("sex="+sex+",age="+age+",称呼是爷爷！");
    }else if(age<18) {//隐含条件：sex=='女'
        System.out.println("sex="+sex+",age="+age+",称呼是小女孩！");
    }else if(age<35) {
        System.out.println("sex="+sex+",age="+age+",称呼是美女！");
    }else if(age<60) {
        System.out.println("sex="+sex+",age="+age+",称呼是阿姨！");
    }else{
        System.out.println("sex="+sex+",age="+age+",称呼是奶奶！");
    }


    //先判断性别  再判断年龄
    if(sex=='男') {
        //判断男生的年龄
        if(age<18) {
            System.out.println("sex="+sex+",age="+age+",称呼是小男孩！");
        }else if(age<35) {
            System.out.println("sex="+sex+",age="+age+",称呼是帅哥！");
        }else if(age<60) {
            System.out.println("sex="+sex+",age="+age+",称呼是叔叔！");
        }else {
            System.out.println("sex="+sex+",age="+age+",称呼是爷爷！");
        }
    }else {
        //判断女生的年龄
        if(age<18) {
            System.out.println("sex="+sex+",age="+age+",称呼是小女孩！");
        }else if(age<35) {
            System.out.println("sex="+sex+",age="+age+",称呼是美女！");
        }else if(age<60) {
            System.out.println("sex="+sex+",age="+age+",称呼是阿姨！");
        }else {
            System.out.println("sex="+sex+",age="+age+",称呼是奶奶！");
        }
    }
}
~~~

## switch

switch格式：

~~~java
 /*switch(表达式){
		 *        case 值1:
		 *             表达式值为值1时  要执行的代码块
		 *             break;
		 *        case 值2:
		 *             表达式值为值2时  要执行的代码块
		 *             break;
		 *        case 值3:
		 *             表达式值为值3时  要执行的代码块
		 *             break;
		 *        case 值n:
		 *             表达式值为值n时  要执行的代码块
		 *             break;
		 *        default:
		 *             表达式值不为以上所有值时  要执行的代码块
		 *             break;      
		 *    }
		 *    
		 * 注意事项：
		 *     1 switch只适用于穷举法：列举出所有的情况
		 *     2 switch表达式的值仅限于：int String Enum
		 *     3 只有当所有的case都不得于switch表达式的值是  才执行default 与其位置无关
		 *     4 break作用是结束switch结构
		 *     5 case不能重复
		 * */
//根据月份判断季节
int month=4;
//Cannot switch on a value of type double. Only convertible int values, strings or enum variables are permitted
switch(month) {
    default:
        System.out.println(month+"月是火星季！default");
        //break;
    case 12:
    case 1:
    case 2:
        System.out.println(month+"月是冬季！");
        break;
    case 3:
    case 4:
    case 5:
        System.out.println(month+"月是春季！");
        break;
    case 6:
    case 7:
    case 8:
        System.out.println(month+"月是夏季！");
        break;
    case 9:
    case 10:
    case 11:
        System.out.println(month+"月是秋季");
        break;
}
~~~

# 循环结构

## while

* while格式

~~~java
/* while格式
			 * while(添加表达式){
			 *     条件表达式成立时执行的代码块
			 * }
			 * 格式与if完全相同
			 * */
~~~

* while执行过程

~~~java
int a=1;
if(a<5) {
    System.out.println("if   a="+a);
}
//if ：条件表达式成立  执行代码块一次
a=1;
while(a<5) {
    System.out.println("while   a="+a);
    Thread.sleep(200);
    a++;//完全等价于 a=a+1;
}
//while ：1  判断条件表达式是是否成立 不成立结束while
//      : 2 条件表达式成立  执行代码块一次
//      : 3 继续 1 2  直到条件表达式不成立
~~~

* while组成

~~~java
/*while的组成：
			 *    1 a<5：条件表达式   
			 *    2 System.out.println("while   a="+a);  循环执行的代码：：循环体
			 *    3 a++;迭代语句
			 *选择执行或者不执行  用if-elase
			 *需要一个数从值1有规律的跑到值2时  用while    
			 * */
~~~

## do-while

~~~java
//for和while完全等价：格式不同
		/*for(初始化语句;条件表达式;迭代语句){
		 *     循环体(条件表达式成立时执行的代码块)
		 *}
		 *初始化语句：用于定义变量、给变量赋初始值的语句
		 *
		 *while(条件表达式){
		 *   循环体(条件表达式成立时执行的代码块)
		 *   迭代语句
		 *}
		 * */
~~~

## for

~~~java
//for和while完全等价：格式不同
		/*for(初始化语句;条件表达式;迭代语句){
		 *     循环体(条件表达式成立时执行的代码块)
		 *}
		 *初始化语句：用于定义变量、给变量赋初始值的语句
		 *
		 *while(条件表达式){
		 *   循环体(条件表达式成立时执行的代码块)
		 *   迭代语句
		 *}
		 * */
~~~

~~~java
九九乘法表：
四个方向，八种情况，1*1和9*9只能在两锐角处：
 //		***
//		**
//		*右上角是1*1
		for(int i=1;i<10;i++) {
			for(int j=9;i<=j;j--) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		***
//		**
//		*右上角是9*9
		for (int i = 9; i >0; i--) {
			for (int j = 1; i>=j; j++) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		   *
//		  **
//		 ***又上是1*1
		for (int i = 1; i < 10 ;i++) {
			for (int j = 9; j >0; j--) {
				if(i<j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
				}
				System.out.println();
			}
//		   *
//		  **
//		 ***右上是9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 1; j < 10; j++) {
				if(i>j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		***
//		 **
//		  *左上1*1
		for (int i = 1; i < 10; i++) {
			for (int j = 1; j < 10; j++) {
				if(i>j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		***
//		 **
//		  *左上9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 9; j > 0; j--) {
				if(i<j) {
					System.out.print('\t');
				}else {
					System.out.print(i+"*"+j+"="+i*j+"\t");
				}
			}
			System.out.println();
		}
//		*
//		**
//		***左上1*1
		for (int i = 1; i < 10; i++) {
			for (int j = 1; i>=j; j++) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
//		*
//		**
//		***左上9*9
		for (int i = 9; i > 0; i--) {
			for (int j = 9; i<=j; j--) {
				System.out.print(i+"*"+j+"="+i*j+"\t");
			}
			System.out.println();
		}
~~~

# break   continue

跳转：

break使用场景1：switch 结束switch结构

​			使用场景2：用在循环中 结束本次循环

continue使用场景1：用在循环中	跳过本次循环	继续进行下次循环

# 数组

> **数组：装指定个数个 相同类型数据的容器**

> 元素：数组中的每个数据---数组的元素
>
> 指定个数：数组创建之前必须指定元素个数
>
> 相同类型：数组创建之前必须指定元素类型

**数组：多个基本数据(8种基本数据类型)有机组合形成一个复杂数据**

**引用数据类型数据：复杂数据  非基本数据类型数据**

**基本数据类型数据的值：常量值  int a=10**

**引用数据类型数据的值：对象/数组对象**

**基本数据类型数据的名字：变量名**

**引用数据类型数据的名字：对象名/数组名/引用名**

> 数据少时用变量记录  同一类型数据多时用数组记录
>
> **数组关键字：[]**

# 二 数组创建

~~~java

//创建数组  存储班级学生的年龄
//创建数组前必须先明确：元素类型+元素个数
//元素个数：10
//元素类型：int
int[] arr;//定义数组名:元素类型[] 数组名;
arr=new int[10];//创建数组对象:new 元素类型[元素个数]; 并赋值给数组名arr
arr=new int[10];//数组名arr指向了一个新的数组对象
//关键字new 每被调用一次  就创建一个新的对象
arr=new int[3];
int[] array;//定义一个新的数组名
array=arr;//让数组名array指向数组名arr指向的数组对象  对象int[3]有两个引用 arr 和 array
~~~

### 三种创建方式

~~~java
//创建数组对象并起个名字  有三种格式：
//格式1： 元素类型[] 数组名=new 元素类型[元素个数];
int[] arr1=new int[10];//元素都是默认初始值
//格式2：元素类型[] 数组名=new 元素类型[]{值1,值2,值3....};
int[] arr2=new int[] {1,4,7,8,9};//元素都是指定的值
//格式3：元素类型[] 数组名={值1,值2,值3....};
int[] arr3= {1,5,7,8,9,0};//格式3是格式2的简写方式 编译器会自动补齐
~~~

### 数组的好处

~~~java
//使用数组好处：
//1 数组会给其中的元素自动分配编号：(编号、索引、下标)  编号0开始
//2 可以通过数 组名 编号 的方式设置和获取其中的元素：数组名[元素下标]
arr[0]=13;//给arr的第一个元素赋值
System.out.println(arr[0]);//打印第一个元素的值
arr[2]=11;
//arr[3]=1;//ArrayIndexOutOfBoundsException  下标越界异常
~~~

### 数组的使用

~~~java
//数组中的元素如果不赋值 有默认初始值--编译器
//默认初始值是什么 取决于元素的类型  --指定类型的0
//获取所有个数:对象名.length 
System.out.println(arr.length);//3
int[] arr0=new int[10];
//左边：int[] arr0： 定义一个要指向int数组的数组名（引用）arr0
//右边：new int[10]：创建一个装10个int元素的数组对象
//=：让左边的数组名arr0指向右边的数组对象
~~~

~~~java
//数组使用1：遍历数组
arr0=new int[] {1,4,5,8,9,0,12};
for (int i = 0; i < arr0.length; i++) {
    //System.out.print(arr0[i]+(i==arr0.length-1?"\n":","));
    if(i==arr0.lengrh-1){
        System.out.print("\n");
    }else{
        System.out.print(",");
    }
}
~~~

~~~java
//数组使用2：获取最大值
int max;//定义变量记录最大值
max=arr0[0];//赋初始值为第一个元素的值
for (int i = 1; i < arr0.length; i++) {//拿max与所有元素做比较
    max=max>arr0[i]?max:arr0[i];
}
System.out.println("元素的最大值："+max);
~~~

# 数组排序

## 顺序排序

~~~java
//排序规则：依次拿当前元素和其后面的所有元素做比较
~~~

~~~java
int[] arr= {1,5,9,0,2,3};
//打印比较的细节
for (int i = 0; i < arr.length-1; i++) {//外层for循环变量i 记录当前元素的下标
    for (int j =i+1; j < arr.length; j++) {//内层for循环变量j 记录当前元素的后面元素的下标
        System.out.print("arr["+i+"]-arr["+j+"]\t");
    }
    System.out.println();
}
//把打印更改为比较 互换
for (int i = 0; i < arr.length-1; i++) {//外层for循环变量   i 记录当前元素的下标
    for (int j =i+1; j < arr.length; j++) {//内层for循环变量 j 记录当前元素的后面元素的下标
        //拿arr[i]和arr[j]比较
        if(arr[j]<arr[i]) {
            int k=arr[i];arr[i]=arr[j];arr[j]=k;
        }
    }
}
~~~

## 冒泡排序

~~~java
//冒泡排序：依次拿相邻元素做比较
~~~

~~~java
//通过代码实现排序细节
int[] arr= {1,6,9,0,2,1};
for (int i = 0; i < arr.length-1; i++) {//外层for循环控制比较的轮数
    for (int j = 0; j < arr.length-i-1; j++) {
        System.out.print("arr["+j+"]-arr["+(j+1)+"]\t");
    }
    System.out.println();
}
//把细节更改为比较
for (int i = 0; i < arr.length-1; i++) {//外层for循环控制比较的轮数
    for (int j = 0; j < arr.length-i-1; j++) { //让j记录相邻的两个元素前面的一个元素的下标
        //拿arr[j]和arr[j+1]比较
        if(arr[j]<arr[j+1]) {
            int k=arr[j];arr[j]=arr[j+1];arr[j+1]=k;
        }
    }	
}
~~~

## 插入排序

~~~java
		for(int i=1; i<ins.length; i++){//i表示当前未排序元素的下标
			for(int j=i; j>0; j--){//让当前元素依次和前面的元素进行比较
				if(ins[j]<ins[j-1]){
					int temp = ins[j-1];
					ins[j-1] = ins[j];
					ins[j] = temp;
				}
			}
		}
~~~



# 二维数组

~~~java
* 数组：装指定个数个 相同类型 的数据的容器 n维数组：装指定个数个 相同类型的n-1维数组的容器 n维数组的元素是n-1维数组
* 默认情况下：数组指的就是一维数组
* 二维数组关键字：[][]
* 创建二维数组格式1：
      元素类型[][] 数组名=new 元素类型[一维数组的个数][一维数组中元素的个数]; 
* 创建二维数组格式2：
      元素类型[][] 数组名=new 元素类型[][]{{值1,值2..},{值1,值2..},{值1,值2..}}; 
* 创建二维数组格式3：
      元素类型[][] 数组名={{值1,值2..},{值1,值2..},{值1,值2..}};
~~~

~~~java
int[][] arr1 = new int[3][4];
// arr1---二维数组的名字
// new int[3][4]---二维数组对象
// int---二维数组中数据的类型
// 3----二维数组中有3个一维数组
// 4----每个一维数组中有4个元素
~~~

~~~java
System.out.println(arr1);// [[I@7852e922
System.out.println(arr1.length);// arr.length:二维数组中一维数组的个数
System.out.println(arr1[0]);// [I@4e25154f arr[i]：二维数组中下标为i的一维数组对象
System.out.println(arr1[0].length);// arr[i].length:二维数组中下标为i的一维数组中的元素个数
System.out.println(arr1[0][1]);// arr[i][j]:二维数组中下标为i的一维数组中下标为j的元素
~~~

~~~java
// 要求：会创建+会遍历
int[][] arr2 = { { 1, 2 }, { 11, 12, 5, 6, 1 }, { 21, 22, 4, 3 }, { 31, 32, 3 } };
// 遍历二维数组 使用两层for循环
for (int i = 0; i < arr2.length; i++) {// 外层for循环当前二维数组中所有的一维数组
    for (int j = 0; j < arr2[i].length; j++) {// 内层for循环遍历当前一维数组中元素
        System.out.print(arr2[i][j] + (j == arr2[i].length - 1 ? "\n" : ","));
    }
}
~~~

# 二维数组练习

~~~java
// 练习：获取二位数组中元素的平均值
// 定义变量记录和 定义变量记录个数
int sum = 0, count = 0;
// 遍历二维数组
for (int i = 0; i < arr2.length; i++) {
    for (int j = 0; j < arr2[i].length; j++) {
        sum += arr2[i][j];
        // count++;
    }
    count += arr2[i].length;
}
System.out.println("元素的平均值=" + sum * 1.0 / count);
~~~

~~~java
/*
		 * 1
		 * 1 1 
		 * 1 2 1 
		 * 1 3 3 1 
		 * 1 4 6 4 1 
		 * 1 5 10 10 5 1 
		 * 1 6 15 20 15 6 1
		 * 
		 * 打印前10行的数据 使用二维数组arr装所有的数据 arr中有10个1维数组对象 arr[i]中应该有i+1个元素
		 * 元素的特点：arr[i][j]------j==0||j==arr[i].length-1----arr[i][j]=1 arr[i][j]=
		 * arr[i-1][j]+arr[i-1][j-1]
		 */
//杨辉三角
int[][] a1 = new int[10][];
for (int i = 0; i < array.length; i++) {
    // 给当前一维数组a1[i]中的元素赋值
    System.out.println(a1[i]);// null 表示对象名没有指向任何对象
    a1[i] = new int[i + 1];//创建一维数组
    System.out.println(al[i]);//[I@4e25154f [I@70dea4e [I@5c647e05 ··· 十个一维数组的地址
    for (int j = 0; j < a1[i].length; j++) {
        // 首尾赋值1
        if (j == 0 || j == a1[i].length - 1) {
            a1[i][j] = 1;
        } else {
            a1[i][j] = a1[i - 1][j] + a1[i - 1][j - 1];
        }
    }

}
for (int i = 0; i < a1.length; i++) {
    for (int j = 0; j < a1[i].length; j++) {
        System.out.print(a1[i][j] + (j == a1[i].length - 1 ? "\n" : "\t"));
    }
}
~~~

# ++参加混合运算

~~~java
int a=1;
a++;//等价于a=(a的类型)(a+1);

a=5;
//++在前 先自增后运算  ++在后 先运算后自增
//a=5
int b=a+(a++)+2+(++a)/a+(--a)+(a--)*a;
//  b=5+ 5  + 2+ 7/7   + 6   +  6*5
System.out.println(b);
~~~

# && 和 & 的区别

~~~java
//阐述a和b的区别
//1 先解释a  解释b
//2 列举a和b的相同之处
//3 列举a和b的不同之处

//&& 和 & 区别
//&& 是逻辑运算符的双与
//&  是逻辑运算符的单与 和 位运算符的单与
//相同之处：作为逻辑运算符时：&&和&的结果一样：两边只要有一个false 结果就是false
//不同之处：1 &还可以作为位运算符：位运算符操作的是数字的二进制
//        2 &&存在逻辑短路的现象：A&&B 当通过A就知道结果时 B就不再执行直接给出结果
//逻辑运算时&&的效率更高
a=3;
if(false&&++a<3) {}
System.out.println("&& a="+a);//3
a=3;
if(false&++a<3) {}
System.out.println("& a="+a);//4

a=3;
if(true||++a<3) {}
System.out.println("|| a="+a);//3
a=3;
if(true|++a<3) {}
System.out.println("| a="+a);//4
~~~

# 方法/函数（method/function）

**方法：类中定义的 一段具有特定功能的代码块**

**方法意义：提高代码的复用性**

~~~java
 * 方法：在类中定义的具有特定功能的代码块
    * 方法关键字：()
    * 方法格式：
    *   修饰符  返回值类型 方法名(参数列表){
    *        实现方法具体功能的代码块(方法体)
    *        return 返回值;
    *   }
    * 方法：小程序 --计算机命令和数据的集合
    *      程序作用--处理数据  ---把原始数据 通过指定的算法处理后 得到结果数据
    * 修饰符：让被修饰者具有一些本来不具有的特征
    *      public static
    *      public :  可以让方法在整个项目中访问到
    *      static :  可以让方法在主方法(主方法是类运行的入口)中调用
    * 返回值：     方法运行完后得到的结果数据
    * 方法名：方法的标示符：：：命名规则--命名规范(和变量名完全相同：：尽量增加可读性+除了第一
                                           个单词 其他单词首字母大写)
    * 参数列表：定义的多个变量 来接受方法运行需要的原始数据
    * 
    * 
    * 通过方法来模拟洗衣机
    * public static 干净衣服类型  小天鹅(脏衣服类型 a,水类型 b,电类型 c){
    *        注水
    *        搅拌
    *        甩干
    *        return 干净衣服;
    * }
    * 
    * 
    * 方法声明部分： 修饰符  返回值类型 方法名(参数列表)
    *         ：方法的使用说明
    * 方法体部分：   {....}
    *         ：方法功能的具体实现
~~~

案例1

~~~java
//求两个int数的和
//确定方法的参数列表 ：为接受方法运行需要的原始数据定义的变量
//确定方法的返回值：方法运行完后返回给调用者的结果数据
public static int  add(int n,int m) {//定义方法
    int sum=n+m;
    System.out.println(n+"+"+m+"="+(n+m));
    return sum;
}

public static void main(String[] args) {
    //调用方法
    int s=add(1, 2);//int s:调用者用于接受方法运行后的结果数据而定义的变量
    System.out.println("s="+s);
    add(11, 22);//调用者可以不接收方法的返回值
}
~~~

案例2

~~~java
//打印一个int和一个doublde的和
//方法参数列表：int ,double
//方法返回值：无
public static void addIntDouble(int a,double b) {//如果方法没有返回值 返回值类型用void标示
    System.out.println(a+"+"+b+"="+(a+b));
    //return ; //当没有返回值时 return是可以省略
    return;
    //System.out.println(1);//Unreachable code
}
public static void main(String[] args) {
    addIntDouble(1, 1.2);//调用方法
}
~~~

方法注意事项

~~~java
    * 注意事项1：方法定义在类中  而非主方法中
    * 注意事项2：方法原始数据可以有多个  而结果数据最多只能有一个
    * 注意事项3：方法必须在主方法中调用 才能运行
    * 注意事项4：方法有返回值 调用者可以选择不接收方法的返回值
    * 注意事项5：方法如果没有返回值  返回值类型用void来标示
    * 注意事项6：方法没有返回值 return可以省略
    * 注意事项7：return两个作用：把返回值返回给调用者  + 结束方法
~~~

# 形参和实参

**形参：定义方法时  用于接受方法运行需要的原始数据而定义的参数列表
实参：调用方法时 调用者给方法传递的原始数据 **

# 基本数据类型和引用数据类型作为参数

~~~java
//方法参数是基本数据类型：实参给形参传递的是常量值
public static void testInt(int a) {
    a++;
    System.out.println("a="+a);//13
}
public static void main(String[] args) {
    int aa=12;
    testInt(aa);//等价于：int a=aa;a++;System.out.println("a="+a);
    //int a=aa;把 变量aa的值 复制一份 给 a  在方法体中对a进行修改  跟变量aa没有关系
    System.out.println("aa="+aa);//12
}
~~~

~~~java
//方法参数列表是引用数据类型 ：传递的是对象的地址
//                         两个引用指向同一个对象
public static void testArray(int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        arr[i]++;
    }
}
public static void main(String[] args) {
    int[] array= {2,4,5,6,3};
    testArray(array);//等价于：int[] arr=array;让数组名arr指向了array指向的数组对象 
    //等于说是给18行的数组对象起了两个名字:main方法中的array 和testArray方法中的arr
    System.out.println(array[0]);//3
    //System.out.println(arr);
}
~~~

# 方法递归

**递归：方法自己调用自己
方法递归 必须有一个出口**

~~~java
//求1到n的和
public static int getSum1(int n) {
    int sum=0;
    for (int i = 1; i <=n; i++) {
        sum+=i;
    }
    return sum;
}
//1+2+3+4+....+(n-1)+n;
//1到n的和 等价于n+ 1到n-1的和
//使用递归实现
public static int getSum2(int n) {
    if(n==1) {
        return 1;
    }
    return n+getSum2(n-1);
}
public static void main(String[] args) {
    System.out.println(getSum2(10));
    //如果递归没有出口  会出现栈溢出错误StackOverflowError
}
~~~
