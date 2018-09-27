#### volatile

Java内存模型，多线程对变量的访问，需从主内存copy到工作内存中操作。为了线程间变量可见，使用了volatile关键字。


```
public class SharedObject {

    public int counter = 0;

}

```


#### volatile的作用

- volatile保证 可见性. 即线程得到的 值是 最新的. Thread1 改变了 var的值, 那么Thread2再去读, 就是改变了的值, 而不是以前的。
- 如果一个字段被声明成volatile，java线程内存模型确保所有线程看到这个变量的值是一致的。
- Volatile变量修饰符如果使用恰当的话，它比synchronized的使用和执行成本会更低，因为它不会引起线程上下文的切换和调度。

- https://www.geeksforgeeks.org/volatile-keyword-in-java/
- http://www.infoq.com/cn/articles/ftf-java-volatile
- http://tutorials.jenkov.com/java-concurrency/volatile.html
