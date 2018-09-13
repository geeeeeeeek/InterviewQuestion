
#### 关键词：对象个数，内存指向

#### 常见问题：
1. String abc = “a” + “b” + “c”; 一共创建了几个对象
2. String s = new String(“hello”); 一共创建了几个对象

#### String pool机制：
目的：JVM为了提高性能和减少内存开销，实现数据共享；

1. 为字符串开辟一个字符串常量池(存在于方法区)
2. 创建字符串常量时，首先坚持字符串常量池是否存在该字符串
3. 存在该字符串，返回引用实例，不存在，实例化该字符串并放入池中   

<br />
String pool在方法区中存在，GC不会回收。

#### 答案：
String abc = “a” + “b” + “c”;
会创建几个objects？
<br />
1个或0个，Java编译器会把”a”+”b”+”c”合并成“abc”，如果String池中包含”abc”，创建0个对象，如果不包含，则创建1个。
<br />
String s = new String(“hello”);
创建了几个”hello”？
<br />
2个或1个，JVM寻找String pool，如果String pool中存在”hello”，则创建1个，如果String池中不存在“hello”, 则创建2个。

<br />
String s = new String(“hello”).intern();
intern()会优化代码，将s直接指向String pool中的”hello”

```
String s1 = "Cat";		
String s2 = "Cat";		
String s3 = new String("Cat");		
String s4 = new String("Cat").intern();
		
System.out.println((s1 == s2));  // true
System.out.println((s1 == s3)); // false
System.out.println((s1 == s4)); // true
```

#### 参考文献
- https://segmentfault.com/a/1190000009888357
- https://www.journaldev.com/797/what-is-java-string-pool
