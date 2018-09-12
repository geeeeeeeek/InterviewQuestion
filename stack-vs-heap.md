#### java中堆与栈的区别  
#### 答题关键词：存储、速度、线程、垃圾回收
##### 存储什么
从存储角度来说，堆内存主要用于存储实例对象和JRE classes，栈内存用于存储基本变量和对象的引用。

```

public class Memory {

	public static void main(String[] args) { // Line 1
		int i=1; // Line 2
		Object obj = new Object(); // Line 3
		Memory mem = new Memory(); // Line 4
		mem.foo(obj); // Line 5
	} // Line 9

	private void foo(Object param) { // Line 6
		String str = param.toString(); //// Line 7
		System.out.println(str);
	} // Line 8

}

```

<br />
<img src='https://github.com/geeeeeeeek/InterviewQuestion/blob/master/data/Java-Heap-Stack-Memory.png' width=400 height=300/>
<br />

##### 速度与size
栈存取速度快，堆区存储比较慢。栈区很小，堆区比较大。

##### 线程访问
每个线程都有一个自己的JAVA栈， 所有线程共享一个堆。在JVM中，内存被分为线程栈区和堆区


<br />
<img src='https://github.com/geeeeeeeek/InterviewQuestion/blob/master/data/thread-stack.png' width=400 height=300/>
<br />

##### 垃圾回收
栈区 GC比较频繁，堆区GC


#### 参考文献
- https://www.journaldev.com/4098/java-heap-space-vs-stack-memory
- https://blog.csdn.net/suifeng3051/article/details/52611310


