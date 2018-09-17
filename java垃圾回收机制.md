Java垃圾回收机制

讲到GC，面试时常见的问题有：请讲一下垃圾回收算法？讲一下minor gc和major gc的区别？讲一下内存分代？
<br />
上面的问题，你是否能够对答如流呢，如果能完美回答出来，恭喜~面试通过。哈哈

1. 讲常见题目
2. 讲今天的主题
3. 讲细节

#### 提到垃圾回收，我们一般是通过下面3个问题来学习它
1. 为什么垃圾回收
2. 回收哪些内存
3. 如何回收

1. 为什么？
Java语言中一个显著的特点就是引入了垃圾回收机制，使c++程序员最头疼的内存管理的问题迎刃而解，它使得Java程序员在编写程序的时候不再需要考虑内存管理。垃圾回收可以有效的防止内存泄露，有效的使用空闲的内存。

2. 回收哪些内存
可达性分析

3. 如何回收
标记-清除法，标记-整理法。


常见GC
- Serial Garbage Collector: 单线程GC
- Parallel Garbage Collector: 多线程GC
- CMS Garbage Collector: 多线程GC
- G1 Garbage Collector: jdk7引进GC，多线程，高并发，低暂停。逐步取代CMS GC。


#### 分代
- 为什么分代？对象的生命周期有长有短。进行分代垃圾回收，能针对这个特点做很好的优化；不同区域的回收时机不同，方便内存管理。
- 分为年轻代和老年代。

#### 年轻代分区：
- 1个eden区
- 2个Survivor区

#### Minor GC和Major GC有什么区别？
- Minor GC清理新生代，发生频率较高；Major GC清理老年代，频率较低。
- Full GC清理新生代和老年代。

 

#### 参考文献
https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/
https://www.geeksforgeeks.org/garbage-collection-java/
https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html
https://www.cubrid.org/blog/understanding-java-garbage-collection
http://www.tothenew.com/blog/java-garbage-collection-an-overview/
