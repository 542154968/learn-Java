# 一个简单的Java应用程序
```java
public class FirstSample{
    public static void main( String[] args ){
        System.out.println("we will not use 'Hello,world!'");
    }
}
```
- Java对大小写敏感
- 关键字`public`被称为访问修饰符，它用于控制程序的其他部分对这段代码的访问级别。
- 关键字`class`表名Java程序中的全部内容都包含在类中
- 这里，只需要将类作为一个加载程序逻辑的容器，程序逻辑定义了应用程序的行为
- 类是构建所有Java应用程序和applet的构建块，Java应用程序中的全部内容都必须放置在类中
- 关键字`class`后面紧跟类名，名字必须以字母开头，后面可以跟字母和数字的任意组合，长度基本没有限制，单不能使用Java保留字
- 标准的命名规范为： 类名是以大写字母开头的名词，采用驼峰法（CamelCase）
- 源代码的文件名必须与共有类的名字相同，并用`.java`作为扩展名
- `.class`是自动生成的，不要自己添加
- 运行编译程序时，`Java`虚拟机将从指定类中的`main`方法开始执行（这里的方法就是Java中所说的函数），因此为了代码能够执行，在类的源文件中必须包含一个`main`方法。也可以将用户自定义的方法天基调类中，并且在`main`方法中调用他们
- main方法必须声明为`public`
- 用花括号画风程序的各个部分（通常称为块）。`Java`中任何方法的代码都用"{"开始，用"}"结束

# 注释
```java
/**
 *
 */
 
// 
```

# 数据类型
- Java是强类型语言。这就意味着必须为每一个变量声明一种类型
- 八种基本类型
- 1. 四种整型
  2. 2种浮点类型
  3. 1种用于表示`Unicode`编码的字符单元的字符类型`char`
  4. 1种用于表示真值的`boolean`类型
- Java有一个能够表示人已经读的算术包，通常称为"大数值"，并不是一种新的Java类型，而是一个Java对象

## 整型
- 整型用于表示没有小数部分的数值，它允许是负数
- int     4字节    -2 147 483 648 ~ 2 147 483 647（正好超过20E）
- short   2字节    -32768 ~ 32767
- long    8字节    -9 223 372 036 854 775 808 ~ 9 223 372 036 854 775 807
- byte    1字节    -128 ~ 127

- 整型的范围与运行Java代码的及其无关
- 长整型有一个后缀L（4000000000L）
- 十六进制有一个前缀0x
- 八进制有一个前缀0，容易混淆，少用
- int最常用

## 浮点类型
- 表示有小数部分的数值
- float    4字节 大约+-3.40282347E+38F（有效6~7位）
- double   8字节 大约+-1.797 693 134 862 315 70E + 308（有效15位）
- 大部分采用double类型
- float类型值有一个后缀F，没有后缀F的浮点数值，默认为double类型
- 也可以在浮点类数值后面添加后缀D
- 所有的浮点数值计算你都遵循IEEE 754规范，下面是表示溢出或出错情况的三个特殊的浮点数值
- 1. 正无穷大
  2. 负无穷大
  3. NaN(不是一个数字)
- 常量`Double.POSITIVE_INFINITY`、`Double.NEGATIVE_INFINITY`和`Double.NaN`(与相应的Float类型的常量一样)，分别表示这三个特殊的值，实际中很少用到。
```java
Double.isNaN( x ) 检测是否是非数值
```
- 浮点数值不适用于进驻出现误差的金融计算中，浮点数由2进制表示，2进制无法精确表示。如果需要在数值计算中不包含有任何舍入误差，就应该用到`BigDecimal`类

## char类型
- char类型用于表示单个字符。通常用来表示字符常量。
- 代码点是指与一个编码表中的某个字符对应的代码值，采用十六进制书写，并加上前缀U+，代码点分成17个代码级别。第一个代码级别称为基本的多语言级别`U+0000  U+FFFF`，其余的16个附加级别`Y+10000 U+10FFFF`，其中包含了一些辅助字符
- 每个字符用16位表示，称为代码单元
- 辅助字符采用一对连续的代码单元进行编码
- 这样构成的编码值一定落入基本的多语言级别中空闲的2048字节内，通常被称为替代区域
- JAVA中，char类型用UTF-16编码描述一个代码单元

## boolean类型
- 两个值， true  false
- 整型值与布尔值之间不能进行相互转换

# 变量
- 在java中，每一个变量属于一种类型
- 在声明变量时，变量所述的类型位于变量名之前
```java
double salary;
int vacationDays;
long earthPopulation;
boolean done;
```
- 每个声明必须以分号结束。由于声明时一条完整的语句，所以必须以分号结束
- 变量名必须是一个以字母开头的有字幕或数字构成的序列。
- 大小写敏感
- 变量名长度没有限制
- 不能声明保留字

## 变量初始化
- 声明一个变量后，必须用赋值语句对变量进行显示初始化，不要使用违背初始化的变量
- 变量的声明尽可能地靠近变量第一次使用的地方

## 常量
- `final`声明常量
- 只能被赋值一次，一但被赋值之后，就不能够再更改了
- 习惯上，常量名使用大写
- 在Java中，竟成希望某个常量可以再一个类中的多个方法中使用，通常将这些常量称为`类常量`，可以使用关键字`static final`设置一个类常量
```java
public class Constants2{
    public static void main( String[] args){
        double paperWidth = 8.5;
        double paperHeight = 11;
        System.out.println( CM_PER_INCH ）
    }
    public static final double CM_PER_INCH = 2.54;
}
```
- 类常量的定义位于main方法的外部，因此，在同一个类的其他方法中也可以使用这个常量。
- 如果一个常量被声明为public，那么其他类的方法也可以使用这个常量
- const是保留字，暂未用（书上的时间）

## 运算符
- 不多讲。。加减乘除啥的
- x += 4 等价于 x = x + 4

### 自增运算符与自减运算符
```java
int n = 12;
n++;
++n;
```
- 只能改变变量的值，不能改变数值。
- 后缀形式使用变量原来的值，前缀形式先加1运算。
```javascript
int m = 7;
int n = 7;
int a = 2 * ++m; // a 16 m 8
int b = 2 * n++; // a 14 n 8
```
- 不建议在其他表达式内容使用++

### 关系预算算符与boolean运算符
- 相等 ==
- 不等 ！=
- < > <= >=
- && || !
- && 短路计算 
```java
expression1 && expression2
- 第一个为false 第二个表达式就没有必要计算了
```
- || 短路计算
```java
expression || expression
- 第一个为true 结果自动为true 不计算后面部分
```
- ? : 三元一次

### 位运算
- 在处理整型数值时，可以直接对组成整型数值的各个位进行操作。这意味着可以使用疲敝技术获得整数中的各个位
- 位运算符包括 &('与') |(或) ^(异或) -(非)
- & 和 | 运算符应用于布尔值，得到的结果也是布尔值
- 这两个运算符与&&和||的运算非常类似，只是不按短路方式计算，即在得到计算结果之前，一定要计算两个操作数的值
- >> 和 << 运算符将二进制位进行右移或左移操作。当需要建立位模式屏蔽某些位时，使用这两个运算符十分方便
- >>> 用0填充高位， >>运算符用符号填充高位 没有<<<运算符

### 数学函数与常量
- Math.sqrt 计算一个数值的平方根
- ……

### 数值类型之间的转换
```java

              char
                ↑
byte → short → int → long
                       ↓
               float  double

```
- long 转成double、 int 转 float long转float 有精度损失
- 当使用上面两个数值进行二元操作时，先要将两个操作数转换为同一种类型，然后再进行计算
- 如果量那个操作书中有一个是double类型的，另一个操作数就会转换为double类型
- 如果其中一个操作数是float类型，另一个操作数将会转换为float类型
- 如果其中一个操作数是long类型的，另一个操作数将会转换为long类型
- 否则，两个操作数都将被转换为int类型

### 强制类型转换
- java允许数值之间的类型转换，当然有可能会丢失一些信息，在这种情况下，需要通过强制类型转换实现这个操作。
- 强制类型转换的语法格式是在圆括号中给出想要转换的目标类型，后面紧跟带转换的变量名
```java
double x = 9.997;
int nx = (int) x; // 9
```
- 变量nx的值是9 强制类型转换通过阶段小数部分将浮点值转换为整型
- 如果想对浮点数进行舍入运算，一遍得到最接近的整数，那就要用 Math.roud方法
```java
double x = 9.997;
int nx = (int) Math.round(x)
```
- 现在，变量nx的值为10.当调用round的时候，仍然需要使用强制类型转换，原因是round方法返回的结果为long类型，由于存在信息丢失的可能性，所以只有使用显示的强制类型转换才能够将long类型转换成int类型

### 括号与运算符级别
- 不使用括号，按照给出的运算符优先级次序进行计算
- 同一个级别的预案算符按照从左到右的次序计算（除了油价和元素福外）

### 枚举类型
- 枚举类型包括有限个命名的值
```java
enum Size { SMALL, MEDIUM, LARGE, EXTRA_LARGE }
// 可以声明这样一种类型的变量
Size s = Size.MEDIUM;
```
- Size类型的变量之鞥呢存储这个类型生命中给定的某个枚举值，或者null值，null表示这个变量没有设置任何值a

### 字符串
- 从概念上讲，Java字符串就是Unicode字符序列。例如"Java\u2122"由5个Unicode字符`J a v a `和`™`|
- java没有你日志的字符串类型，而是在标准java类库中提供了一个预定义类String
- 每个用双引号括起来的字符串都是String类的一个实例
```java
String e = ""
String greeting = "Hello"
```

### 子串
- String类的substring方法可以从一个比较大的字符串提取出一个子串
```java
String greeting = "Hello";
String s = greeting.substring(0, 3)
```
- substring方法的第二个参数是不想复制的第一个位置。这里要复制位置0， 1， 2的字符。substring中从0开始计数，知道3为止，但不包含3
- 容易计算子串的长度。字符串s.substring(a, b)的长度为b-a

### 拼接
- Java语言允许使用`+`号拼接两个字符串
- 当讲一个字符串与一个费字符串的值拼接时，后者被转换成字符串

### 不可变字符串
- 由于不能修改Java字符串中的字符，所以在Java文档中将String类独享称为不可变字符串，但是可以修改它的变量，让它引用另外一个字符串。
- 创建一个新的字符串效率确实不高，但是，不可变字符串却有一个优点：编译器可以让字符串`共享`

### 检测字符串是否相等
- `equals`方法检测两个字符串是否相等，可以是变量，也可以是常量
- `equalsIgnoreCase` 检测两个字符串相等，不区分大小写。
- 不能使用`==`运算符检测两个字符串是否相等！ 这个元素福只鞥确定两个字符串是否放置在同一个位置上，如果两个字符串放在同一个位置上，他们必然相等，但是完全有坑将内容相同的多个字符串的拷贝放置在不同的位置上
- 如果虚拟机始终将相同的字符串共享，就可以使用==运算符检测是否相等。当时机上只有字符串常量是共享的，而+或substring等操作产生的结果并不是共享的

### 代码点，代码单元
- java字符串由char序列组成。
- 字符数据类型是一个采用`UTF-16`编码表示`Unicode`代码点的代码单元
- 大多数的常用`Unicode`字符使用一个代码单元就可以表示，而辅助字符需要一堆代码单元表示
- length方法返回采用`UTF-16`编码表示的给定字符串所需要的代码单元数量。
```java
String greeting = "Hello";
int n = greeting.length(); // 5

// 想要得到实际的长度
int cpCount = greeting.codePointCount( 0, greeting.length() );
```
- 调用s.charAt(n)将返回位置n的代码单元， n介于 0~s.length() - 1之间
- 如果想要遍历一个字符串，并且依次查看每一个代码点
```java
int cp = sentence.codePointAt(i);
if( Character.isSupplementaryCodePoint(cp) ){
    i += 2
} else{
    i++
};
```
- `codePointAt`方法能够辨别一个代码但愿是辅助字符的第一部分还是第二部分，并能够正确返回结果
- 可以使用下列语句实现回退操作
```java
i--;
int cp = sentence.codePointAt(i);
if( Character.isSupplementaryCodePoint(cp) ) i--;
```

### 字符串API
- char charAt( int index )： 返回给定位置的代码单元。除非对底层的代码单元感兴趣，否则不需要调用这个方法
- int codePointAt( int index ) 5.0： 返回从个定位置开始或结束的代码点
- int offsetByCodePoints( int startIndex, int cpCount ) 5.0 ： 返回从startIndex代码点开始，唯一cpCount后的代码点索引
- int compareTo( String other )： 按照字典顺序，如果字符串位于other之前，返回一个负数；如果字符串位于other之后，返回一个正数，如果两个字符串相等，返回0
- boolean endsWith(String suffix)： 按照字典顺序，如果字符串位于other之前，返回一个负数。如果字符串位于other之后，返回一个正数。如果两个字符串相等，返回0
- boolean equals(Object other)： 如果字符串与ohter相等，返回true
- boolean equalsIgnoreCase(String other)： 如果字符串与other相等，忽略大小写，返回true
- int indexOf(String str)、 int indexOf(String str, int fromIndex) int indexOf(int cp) int indexOf(int cp, int fromIndex)： 返回与字符串str或代码点cp匹配的第一个子串的开始位置。这个位置从索引0或fromIndex开始计算，如果在原始串中不存在str 返回-1
- int lastIndexOf( String str ) int lastIndexOf(String str, int fromIndex) int lastindexOf(int cp) int astindexOf(int cp, int fromIndex)： 返回与字符串str或代码点cp陪陪的最后一个子串的开始位置，这个位置从原始串尾端或fromIndex开始计算
- int length() 返回字符串的长度
- int codePointCount(int startIndex, int endIndex) 5.0： 返回startIndex和endIndex-1之间的代码点数量，没有配成对的带动字符将计入代码点
- String replace(CharSequence oldString, CharSequence newString)： 返回一个新字符串。这个字符串用newString代替原始字符串中所有的oldString，可以用String或StringBuilder对象作为CharSequence参数
- boolean startsWidth(String prefix): 如果字符串以preffix字符串开始返回true
- String substring(int beginIndex) String substring(int beginIndex, int endIndex)；返回一个新字符串，这个字符串包含原始字符串中从beginIndex到串尾或endIndex-1所有代码单元
- String toLowerCase() 返回一个新字符串，这个字符串将原始字符串中的大写字母改为小写字母
- String toUpperCase() 返回一个新字符串，这个字符串能将原始字符串中的所有小写字母改为大写字母
- String trim() 返回一个新字符串，去除首位空格

### 构建字符串
- 使用StringBuilder类可以避免例如按键或来自文件中的单次，采用字符串连接的方式达到此目的的效率比较低，每次链接字符串都会构建一个新的String对象，耗时耗空间
- 如果需要用许多小段的字符串构建一个字符串
```java
// 构建一个空的字符串构建器
StringBuilder builder = new StringBuilder();
// 每次需要添加一部分内容时，就调用append方法
builder.append(ch); // appends a single character
builder.append(str); // appends a string
// 在需要构建字符串时，就调用toString方法，将可以得到一个String对象，其中包含了构建起种的字符序列
String completedString = builder.toString();
```
- 在JDK5.0中引入StringBuilder类。这个累的前身是StringBuffer，其效率略微有些低，但允许采用多线程的方式进行添加或删除字符的操作。
- 如果所有字符串在一个单线程（通畅都是这样）中编辑，则应该使用StringBuilder代替它
- StringBuilder() 构造一个空的字符串构建器
- int length() 返回构建起或缓冲器种的代码单元数量
- StringBuilder append(String str) 追加一个字符串并返回this
- StringBuilder appendCodePoint(int cp) 追加一个代码点，并将其转换为一个或两个代码单元并返回this
- void setCharAt(int i, char c) 将低i个代码单元设置为c
- StringBuilder insert(int offset, String str) 在offset位置插入一个字符串并返回this
- StringBuilder insert( int offset, Char c ) 在offset位置插入一个代码单元并返回this
- StringBuilder delete(int startIndex, int endIndex) 删除偏移量从startIndex到 - endIndex-1的代码单元并返回this
- String toString() 返回一个与构建器或缓冲器内容相同的字符串

## 输入输出
- GUI

### 读取输入
- 打印输出到"标准输出流"（即控制台窗口）是一件非常容易得事情，只要调用`System.out.println`。
- 然而，读取"标准输入流"`System.in`就没有这么简单了。
- 要想通过控制台进行输入，首先要构造一个`Scanner`对象，并与“标准输入流”`System.in`关联
```java
Scanner in = new Scanner(System.in)
```
- 现在就可以使用`Scanner`类的各种方法实现输入操作了
```java
System.out.print("what is your name?");
String name = in.nextLine(); 
// 因为再输入行中有坑包含空格，要想读取一个单词，以空白符' '作为分隔符，就调用
String firstName = in.next();
// 要想读取一个整数，就调用nextInt方法
System.out.print("How old are you?")
int age = in.nextInt();
// 要想读取下一个浮点数， 就调用nextDouble方法
// 最后，在程序的最开始添加上一行
import java.util.*
// 
```
- Scanner类定义在java.util包中。
- 当使用的类不是定义在基本java.lang包中时，一定要使用import指示字符将相应的包加载进来
```java
import java.util.*;
public class InputText{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.print("what is your name?");
        String name = in.nextLine();
        System.out.print("How old are you?");
        int age = in.nextInt();
        System.out.println("Hello, " + name + ". Next year, you'll be " + (age + 1) );
    }
```
- 因为输入是可见的，所以Scanner类不适用于从控制台读取密码。Java SE6特别引入了Console类实现这个目的。
```java
Console cons = System.console();
String username = cons.readLine("User name: ");
char[] passwd = cons.readPassword("Password: ");
```
- 为了安全起见，返回的密码存放在一堆字符串数组中，而不是字符串中，在对密码进行处理之后，应该马上用一个天重置覆盖数组元素。
- 采用Console对象处理输入不如采用Scanner方便。每次之鞥呢读取一行输入，而没有能够读取一个单词或一个数值的方法。
- **java.util.Scanner 5.0**
- Scanner( InputStream in ) 用诶定的输入流创建一个Scanner对象
- String nextLine() 读取出入的下一行内容
- String next() 读取输入的下一个单词
- int nextInt()、double nextDouble() 读取并转换下一个表示整数或浮点数的字符序列
- boolean hasNext() 检测输入中是否还有其他单词
- boolean hasNextInt()、 boolean hasNextDouble() 检测时候还有表示整数或浮点数的下一个字符序列
- **java.lang.System 1.0**
- static Console console() 6  若果有可能进行交互操作，就谈过控制台窗口为交互的用户返回一个Console对象。否则返回null。对于热呢一个通过控制台窗口启动的程序，都可使用Console对象。否则，其可用性将于所使用的系统有关
- **java.io.Console 6**
- static char[] readPassword(String prompt, Object...args)
- static Strin readLine(String prompt, Object...args)
- 显示字符串prompt并且读取用户输入，知道输入行结束。args参数可以用来提供输入格式

### 格式化输出
- 可以使用`System.out.print(x)`将数值x输出到控制台上。这条命令将以x对应的数据类型所允许的最大非0数字位数打印输出x
```java
double x = 10000.0 / 3.0;
System.out.print(x); // 3333.33333333335
```
- Java SE5.0沿用了C语言库函数中的printf方法
```java
System.out.printf("%8.2f", x)
// 可以用8个字符宽度和小数点后两个字符的精度打印x 也就是说，打印输出一个空格和7个字符
// 3333.33
```
- 每一个以%字符开始的格式说明符都用相应的参数替换。格式说明符尾部的转换符将知识被格式化的数值类型：f表示浮点数，s表示字符串，d表示十进制整数
- d 十进制整数  x 十六进制整数  o 八进制整数  r 定点浮点数  e 指数浮点数  g 通用浮点数  a 十六进制浮点数 
- s 字符串  c 字符  b 布尔  h 散列码  tx 日期时间  % 百分号  n 与平台有关的行分隔符
- 还可以给出控制格式化输出的各种标志
- ……

### 文件输入与输出
- 要想对文件进行读取，就需要衣蛾用File对象构造一个Scanner对象
```java
Scanner in = new SXcanner( new File("myfile.txt") );
```
- 如果文件名中包含反斜杠，要加个`/`转义
- 现在，就可以利用前面介绍的任何一个`Scanner`方法对文件进行读取
- 要想写入文件，需要构造一个`PrintWriter`对象，在构造器中只需提供文件名
```java
PrintWriter out = new PrintWriter("mufile.txt")
```
- 如果文件不存在，则可以像输出到System.out一样使用print println 以及printf命令
```java
String dir = System.getProperty("user.dir") // 获取路径的位置
```
- 异常处理，在main方法中用throws子句标记
```java
public static void main( String[] args ) throws FileNotFoundException{
    Scanner in = new Scanner(new File("myfile.txt"))
}
```
- 当使用命令行启动一个程序时，可以利用重定向将任意文件捆绑到System.in和System.out
```java
java MyProg <myfile.txt> output.txt
```
- **java.util.Scanner 5.0**
- Scanner(File f) 构造一个从给定文件读取数据的Scanner
- Scanner(String data) 构造一个从给定字符串读取数据的Scanner
- **java.io.PrintWriter 1.1**
- PrintWriter(File f) 构造一个将数据写入给定文件的PrintWriter
- PrintWriter(String fileName) 构造一个将数据写入文件的PrintWriter 文件名由参数决定
- **java.io.File 1.0**
- File(String fileName) 用给定文件名，构造一个描述文件的File对象 注意这个文件当前不必存在

## 控制流程
- java使用条件语句和循环结构确定控制流程

### 块作用域
- 块，即复合语句。时只有一对花括号括起来的若干条简单的Java语句。块确定了变量的作用域。一个快可以嵌套在另一个块中
```java
public static void main(String[] args){
    int n;
    {
        int k;
    } // 只有在此块中能找到k
}
```
- 但是，不能在嵌套的两个块中声明同名的变量
```java
pualic static void main(String[] args){
    int n;
    {
        int n; // 报错
    }
}
```

### 条件语句
- 在java中，条件语句格式为  if(condition) statement
- while(condition) statement
- do statement while (condition)

### 确定循环
- for循环
- for语句的3个部门应该对同一个计数器变量进行初始化、检测和更新。
