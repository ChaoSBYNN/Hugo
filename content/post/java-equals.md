+++
Categories = ["JAVA"]
date = "2016-07-16T10:04:36+08:00"
title = "关于Java中的 == 和 equals"

+++

<!--more-->

Updated on 2016-07-16

> `==` 对于基本数据类型比较的就是数据本身，对于引用数据类型比较的就是内存地址。
>
> `equals` 对于引用数据类型比较的也是内存地址；但其中的 `String` 类比较特殊，重写了继承自 `Object` 类的 `equals` 方法，使其比较数据本身。
>
> 打发时间的同时加深理解：)

![](/uploads/java-equals.svg "== and equals")

![](/uploads/java-equals-object.png "Object 类")

![](/uploads/java-equals-string.png "String 类")

```java
class Demo {
    public static void main(String[] args) {
        String a = "123";
        String b = "123";
        String c = new String("123");

        System.out.println(a == b);
        System.out.println(a.equals(b));
        System.out.println("--------------");
        System.out.println(a == c);
        System.out.println(a.equals(c));

        A a1 = new A();
        A a2 = new A();
        System.out.println("--------------");
        System.out.println((a1 == a2));
        System.out.println(a1.equals(a2));
    }
}
class A {
}
----
输出：
true
true
--------------
false
true
--------------
false
false
```