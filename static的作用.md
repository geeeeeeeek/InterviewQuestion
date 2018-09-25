用static修饰的代码块表示静态代码块，当Java虚拟机（JVM）加载类时，就会执行该代码块。（优先加载，相当于vip服务，优先加载static）。static变量是全局共享的。

#### static变量
对于静态变量在内存中只有一个拷贝（节省内存），JVM只为静态分配一次内存，在加载类的过程中完成静态变量的内存分配，可用类名直接访问（方便） 
<br />
对于实例变量，每创建一个实例，就会为实例变量分配一次内存，实例变量可以在内存中有多个拷贝，互不影响
<br />
static变量的作用：
1. 对象之间共享值
2. 方便访问变量
<br />
#### 静态方法
静态方法可以直接通过类名调用，
<br />
静态方法中不能用this和super关键字，不能直接访问实例变量和方法（还没创建实例），只能访问静态方法和变量


#### 静态代码块
static代码块也叫静态代码块，是在类中独立于类成员的static语句块，可以有多个，位置可以随便放，它不在任何的方法体内，JVM加载类时会执行这些静态的代码块，如果static代码块有多个，JVM将按照它们在类中出现的先后顺序依次执行它们，每个代码块只会被执行一次。

<br />
需要注意的是：
1. Static变量仅能在class类层次创建，不能在方法里面创建
2. Static代码块和static变量是由代码执行顺序的(先申明先执行)

```
static { name="zhangsan"; } 
private static String name=null; 
// 上面这段代码，把name打印出来是null

```

```
private static String name=null; 
static { name="zhangsan"; } 
// 上面这段代码，把name打印出来是zhangsan

```

<br /><br />
Static场景：适合于公用资源的申明(学生共用学校名称)


- https://www.geeksforgeeks.org/static-keyword-java/
- https://www.jianshu.com/p/2ee995a3a348
