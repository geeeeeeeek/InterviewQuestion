
#### 关键区别
- == 比较的是引用地址（或内存地址）
- equals 比较的是两个对象的值（如果这个对象已经实现了equals方法）

#### 使用==来比较
```
public class Sample {
   public static void main(String []args) {
      String a = "hello";
      String b = "hello";
      String c = new String ("hello");
      System.out.println(a == b);
      System.out.println(a == c);
   }
}
```
输出
```
true
false
```

#### 使用equals来比较
```
public class Sample {
   public static void main(String []args) {
      String a = "hello";
      String b = "hello";
      String c = new String ("hello");
      System.out.println(a.equals(b));
      System.out.println(a.equals(c));
   }
}
```
输出
```
true
true
```
- 当使用==比较的时候，因a和b指向的是同一个地址，所以a==b为true。因c是新建的一个String对象，在内存里新开辟了一个地址来存放c，所以a==c为false。
- 当使用equals比较的时候，因a和b的值是一样的，所以a.equals(b)为true，另，c的值也是和a是一样的，故：a.equals(c)为true
<br/>
#### 如下图
<img src='' width=500 height=500/>
