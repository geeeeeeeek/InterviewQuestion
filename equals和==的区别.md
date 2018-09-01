
#### 关键区别
- == 比较的是引用地址（或内存地址）
- equals 比较的是两个对象的值（如果这个对象已经实现了equals方法）

#### 使用==来比较
```
public class Sample {
   public static void main(String []args) {
      String s1 = "hello";
      String s2 = "hello";
      String s3 = new String ("hello");
      System.out.println(s1 == s2);
      System.out.println(s2 == s3);
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
      String s1 = "hello";
      String s2 = "hello";
      String s3 = new String ("hello");
      System.out.println(s1.equals(s2));
      System.out.println(s2.equals(s3));
   }
}
```
输出
```
true

```
