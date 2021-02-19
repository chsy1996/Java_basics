# Java_basics
- [基础语法](#jump_basics)
- 面向对象
- 接口
- 集合
- 异常
- 范型
- 反射
- 注解
- I/O
- 图形化（Swing)



# <span id="jump_basics">基础语法</span>

# 面向对象

# 接口

# Java集合

## 概念

集合是Java中的一种容器，可以用来存储多个数据。数组和集合都是容器。

## 分类

集合按照存储结构可以分为两大类：

- 单列集合`java.util.Collection`
- 双列集合`java.util.Map`

具体分类如下(蓝色表示接口，红色表示常用类)：

![img](https://img2018.cnblogs.com/blog/1480948/201904/1480948-20190418134150126-789384923.png)

## Collection集合

**单列集合**类的根**接口**，用于存储一系列符合某种规则的元素。两个重要的子接口：

- `java.util.List`：元素**有序(存入和取出顺序一致)**、**带索引**、**可重复(通过equals方法比较是否为重复元素)**。

  ```java
  //特有方法
  public void add (int index, E element) //将指定元素添加到给集合中的指定位置上
  public E get(int index)	//返回集合中指定位置的元素。
  public E remove(int index)	//移除列表中指定位置的元素, 返回的是被移除的元素。
  public E set(int index, E element)	//用指定元素替换集合中指定位置的元素,返回值的更新前的元素。  
  ```

  - `java.util.ArrayList`：**数组结构**、元素增删慢、查找快。
  - `java.util.LinkedList`：**链表结构**、提供大量**首尾操作**、开发时也可以作为**堆栈**、**队列**使用。

- `java.util.Set`：元素**无序**，且**不可重复**。

  - `java.util.HashSet`：数组+链表/红黑树结构、依赖`hashCode`和`equals`方法保证元素唯一性。
    - `java.util.LinkedHashSet`：元素有序的HashSet、链表+哈希表。
  - `java.util.TreeSet`



**可变参数：**

```java
修饰符 返回值类型 方法名(参数类型... 形参名){  }
```

等价于

```java
修饰符 返回值类型 方法名(参数类型[] 形参名){  }
```



Collection接口**通用方法**：

* `public boolean add(E e)`：  把给定的对象添加到当前集合中 。
* `public void clear()` :清空集合中所有的元素。
* `public boolean remove(E e)`: 把给定的对象在当前集合中删除。
* `public boolean contains(E e)`: 判断当前集合中是否包含给定的对象。
* `public boolean isEmpty()`: 判断当前集合是否为空。
* `public int size()`: 返回集合中元素的个数。
* `public Object[] toArray()`: 把集合中的元素，存储到数组中。



**Iterator接口(迭代器)：**专门用来遍历集合中的所有元素。

- `public Iterator iterator()`: 获取集合对应的迭代器，用来遍历集合中的元素的。

- `public E next()`:返回迭代的下一个元素。
- `public boolean hasNext()`:如果仍有元素可以迭代，则返回 true。



## 集合工具类

* `java.utils.Collections`是集合工具类，用来对集合进行操作。部分方法如下：

- `public static <T> boolean addAll(Collection<T> c, T... elements)  `:往集合中添加一些元素。
- `public static void shuffle(List<?> list) 打乱顺序`:打乱集合顺序。
- `public static <T> void sort(List<T> list)`:将集合中元素按照默认规则排序。
- `public static <T> void sort(List<T> list，Comparator<? super T> )`:将集合中元素按照指定规则排序。



- **Comparator比较器**

`public static <T> void sort(List<T> list)`实际上实现了`Comparable接口`，该接口完成了比较规则的定义。

Comparator接口使我们可以自定义排序规则，比较方法：

` public int compare(String o1, String o2)`：比较其两个参数的顺序。

> 两个对象比较的结果有三种：大于，等于，小于。
>
> 如果要按照升序排序，
> 则o1 小于o2，返回（负数），相等返回0，01大于02返回（正数）：o1值 - o2值
> 如果要按照降序排序
> 则o1 小于o2，返回（正数），相等返回0，01大于02返回（负数）：o2值 - o1值

# 异常

# 范型

# 反射

# 注解

# I/O

# 图形化(如Swing)
