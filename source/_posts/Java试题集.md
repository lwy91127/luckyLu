title: Java试题集
date: 2015-10-22 14:28:54
tags: java
---


### 1. 说出几个与spring同类型的开源框架；说出几个与hibernate同类型的开源框架；说出几个与struts同类型的开源框架

> 解答：1)与spring同类型的：JUIDE，EJB3.0，picoContainer
> &emsp;&emsp;&emsp;2)与hibernate同类型的：ibatis，jdo，JPA
> &emsp;&emsp;&emsp;3)与struts同类型的： webwork，tapestry，JSF


#G## 2. Struts2中，OGNL访问值栈的时候查找的顺序是什么？请排序：模型对象，临时对象，固定名称的对象，Action对象

> 解答：Struts2的值栈排列顺序为：1）临时对象 2）模型对象 3）Action对象 4）固定名称的对象（如#application，#session，#request等）


### 3. Struts2中，Action通过什么方式获得用户从页面输入的数据，又是通过什么方式把自身的数据传给视图？

> 解答：1）可以直接通过与表单元素相同名称的数据成员（需要存在符合命名规范set和get方法）获取页面表单的数据
> &emsp;&emsp;&emsp;2）会把处理好的数据成员放入值栈中，页面可以使用Struts2标签取值


<!-- more -->

### 4. 说明工厂模式

> 解答：工厂模式:
> &emsp;&emsp;&emsp;工厂模式是一种经常被用到的模式，根据工厂模式实现的类可以根据提供的数据生成一组类中某一个类的实例，通常这一组
> &emsp;&emsp;&emsp;类又一个公共的抽象父类并且实现了相同的方法，但是这些方法针对不同的数据进行了不同的操作。首先需要定义一个基类
> &emsp;&emsp;&emsp;该类的子类通过不同的方法实现了基类中的方法。然后需要定义一个工厂类，工厂类可以根据条件生产不同的子类实例。当
> &emsp;&emsp;&emsp;得到子类的实例后，开发人员可以调用基类中的方法而**不必考虑到底返回的是哪一个子类的实例**。

### 5. JS中三种弹出式消息提醒（警告，确认，信息输入）的命令是什么？

> 解答：alert confirm prompt

### 6. 描述JSP和Servlet的区别、共同点、各自应用的范围

> JSP在本质上就是Servlet，但是两者的创建方式不一样。Servlet完全是Java程序代码构成，擅长于流程控制和事务处理，通过Servlet来
> 生成动态网页很不直观。JSP由HTML代码和JSP标签构成，可以方便的编写动态网页。因此在实际应用中采用Servlet来控制业务流程，而J
> SP来生成动态网页。

### 7. 简述synchronized和java.util.concurrent.locks.Lock的异同

> 解答：相同点：Lock能完成synchronized所实现的所有功能
> &emsp;&emsp;&emsp;不同点：Lock有比synchronized更精确的线程语义和更好的性能。synchronized会自动个释放锁，而Lock一定要求程序员手动释放，并且必须在finally从句中释放。

### 8. 如何格式化日期

```java
Date now = new Date();
SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd hh:mm:ss");
String formatNow = sdf.format(now);
```

### 9. Struts中如何实现国际化，涉及哪些文件？

> Struts框架通过使用<bean:message>标记，以及使用java.util数据包中定义的Locale和ResourceBundle类来支持国际化。另外，java.text.MessageFormat
> 类定义的技术可以支持消息的格式，利用此功能，开发人员不需要了解这些类的细节就可以进行国际化和设置消息的格式。
> 涉及的文件是：struts-config.xml 和 web.xml

### 10. 简述Java基本数据类型以及所占位数

> 逻辑型：boolean (1byte)
> 文本型：char (2byte)
> 整数型：byte (1byte),short (2byte),int (4byte),long (8byte)
> 浮点整型：float (4byte),double (8byte)

### 11. HashMap和HashTable的区别

> 1)HashMap允许空键值对，HashTable不允许
> 2)HashMap不是线程安全的，HashTable是
> 3)HashMap直接实现Map接口，HashTable继承Dictionary类

### 12. ArrayList，Vector，LinkedList存储性能和特性

> **都实现List接口**
> ArrayList和Vector都是基于**数组**实现的
> LinkedList基于**双向循环链表**实现(查找效率低，添加删除容易)
> ArrayList不是线程安全的，而Vector是线程安全的，所以速度上ArrayList高于Vector

### 13. Collection和Collections的区别

> Collection是集合类的上级接口，继承与他的接口主要有Set和List。
> Collections是针对集合类的一个帮助类，提供一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作。

### 14. Overload和Override的区别

> Override重写是父类与子类之间多态性的一种表现，方法名、参数列表、返回值类型都要与父类一致。
> Overload是一个类中多态性的一种表现，可以改变返回值的类型。

### 15. sleep()和wait()有什么区别

> sleep是线程类的方法，导致此线程暂停执行时间，将执行机会给其他线程，但是依然保持监控状态，到时后会自动恢复，调用sleep不会释放对象锁。
> wait是Object类的方法，对此对象调用wait方法将导致本线程放弃对象锁，进入等待此对象的等待锁定池，只有针对此对象调用notify方法后本线程才
> 进入对象锁定池准备获得对象锁定池准备获得对象锁进入运行状态。

### 16. 请说出你所知道的线程同步方法

> wait：使一个线程处于等待状态，并且释放锁持有的对象的lock；
> sleep：使一个正在运行的线程处于睡眠状态，是一个静态方法，调用时需要捕捉InterruptException；
> notify：唤醒一个处于等待状态的线程，注意的是在调用此方法的时候，不能确切的唤醒其一个等待状态的线程，而是由JVM确定，并且不按优先级；
> notifyAll：唤醒所有处于等待状态的线程，注意并不是给所有唤醒的线程一个对象的锁，而是让所有线程竞争。

### 17. 网络编程中设计并发服务器，使用多进程和多线程，请问有睡眠区别？

> 进程：子进程是父进程的复制品，子进程获得父进程数据空间堆和栈的复制品。
> 线程：相对于进程而言，线程是一个更加接近与执行体的概念，它可以与同进程的其他线程共享数据，但也拥有自己的栈空间，拥有独立的执行序列
> 两者都可以提高程序的并发度，提高程序运行效率和响应时间。
> 线程的执行开销小，但不利于资源管理和保护；而进程正相反。线程适合于在SMP机器上运行，而进程则可以跨机器迁移。

### 18. 线程的基本概念、线程的基本状态和状态间关系

> 新建(Born)：新建的线程处于新建状态
> 就绪(Ready)：创建后的线程就处于就绪状态，等待start方法被调用
> 运行(Ruuning)：线程在开始执行时进入运行状态
> 睡眠(Sleeping)：线程的执行可通过使用sleep方法来暂时终止，睡眠后，线程将进入就绪状态
> 等待(Waiting)：如果调用wait方法，线程将处于等待状态，用于在两个或多个线程并发运行时
> 挂起(Suspended)：在临时停止或中断线程的执行时，线程就处于挂起状态
> 恢复(Resume)：在挂起的线程被恢复执行时，可以说它已被恢复
> 阻塞(Blocked)：在线程等待一个事件时(例如输入/输出操作），就称其处于阻塞状态。
> 死亡(Dead)：在run方法已完成执行后，线程处于死亡状态

### 19. servlet的生命周期

> web容器加载servlet，生命周期开始，
> 通过调用servlet的init()方法进行servlet的初始化
> 通过调用service()方法实现，根据请求的不同调用不同的doGet()或者doPost()方法。
> 结束服务，web容器调用servlet的destroy()方法。


### 20. 什么是反射？

> 1）对于任意一个类，可以知道这个类的属性和方法。
> 2）对于任意一个对象，可以地欧诺个用这个对象的任意方法。
> 提供的功能：
> 1.运行时判断任意对象的所属类；
> 2.运行时构造任意类的对象；
> 3.运行时判断和调用对象的成员变量和方法；
> 4.生成动态代理。

### 21. jsp有哪些内置对象？作用分别是什么?

> JSP有以下9中基本内置组件：
> request：用户端请求，此请求会包含来自GET/POST请求的参数
> response：网页传回用户端的回应
> pageContext：网页的属性是在这里管理
> session：与请求有关的会话
> application：servlet正在执行的内容
> out：用来传送回应的输出
> config：servlet的构架部件
> page：JSP网页本身
> exception：针对错误网页，未捕捉的例外

### 22.Object有哪些公用方法?

> 1.equals方法判断对象是否相等
> 2.clone方法进行对象的拷贝
> 3.getClass方法返回和当前对象相关的class对象
> 4.notify,notifyall,wait方法进行线程同步

### 23.Java的四种引用,用到的场景

> 1.强引用:程序代码中普遍存在的,只要强引用还在,垃圾收集器永远不会回收掉被引用的对象.
> 2.软引用(SoftReference):描述还有用但是并非必需的对象.当系统内存不足时会将这些对象进行回收.
> 3.弱引用(WeakReference):描述非必需的对象,但是比软引用更弱,被软引用的对象只能生存到下一次垃圾收集发生之前.
> 4.虚引用(PhantomReference):目的是在垃圾收集器回收该对象时收到一个系统通知,对其生存时间完全不构成影响.
>
> 5.使用场景:
>	1)利用软引用和弱引用解决OOM问题.
>	2)通过软引用和对象重获方法实现Java的高速缓存.

### 24.String,StringBuffer与StringBuilder的区别

> 1.String类型和StringBuffer类型的主要性能区别在于String是不可变对象
> 2.StringBuffer和StringBuilder的底层实现是char[]数组
> 3.StringBuffer是线程安全的,而StringBuilder是线程不安全的

### 25.抽象类和接口的区别

> 1.一个类只能继承单个类,但是可以实现多个接口
> 2.接口强调特定功能的实现,而抽象类强调所属关系
> 3.抽象类可以有普通成员变量,接口没有普通成员变量
> 4.抽象类可以有静态方法,接口不能有
> 5.抽象类可以有构造方法,接口没有构造方法
> 6.抽象类的方法可以是public,protected,接口方法只有public

### 26.解析XML的几种方法的原理和特点

> 1.DOM:内存消耗大:先把xml文档都读到内存中,然后再用DOM API来访问树形结构,并获取数据,这个写起来很简单,但是消耗内存.
> 2.SAX:解析效率高,占用内存少,基于事件驱动的:对文档进行顺序扫描,扫描到特定的地方时通知时间处理函数,由事件处理函数进行相应的动作.

### 27.Java中堆和栈的区别

> 1.堆主要用来存储对象,而栈用来存储局部变量表,方法出口等
> 2.堆是线程共享的,栈是线程独有的
> 3.堆存储空间不足抛出的异常是OutOfMemoryError,栈抛出的是StackOverFlowError
> 4.堆的内存空间远大于栈的空间

### 28.HashMap和HashTable的区别:

> 1.HashTable比较老,是基于Dictionary类实现的,HashMap是基于Map接口实现的
> 2.HashTable是线程安全的,HashMap是线程不安全的.
> 3.HashMap可以用null作为一对值的key或者value

### 29.实现线程同步的方式:

> 1.synchronized修饰方法或者代码块
> 2.使用volatile关键字修饰非final变量
> 3.使用concurrent包中的ReentrantLock重入锁.
> 4.ThreadLocal管理变量,使得每个使用该变量的线程都获得该变量的副本

### 30.ThreadLocal类的作用和实现原理

> 作用:解决多线程中相同变量的访问冲突问题
> 实现原理:为每一个使用该变量的线程提供一个变量值的副本,每个线程可以独立地改变自己的副本,而不会和其他线程的副本冲突

### 31.线程池的用法和优势

> 优势:
>	   1)降低资源消耗,通过重复利用已创建的线程降低线程创建和销毁造成的消耗.
>	   2)提高响应速度,当任务到达时,任务可以不需要等到线程创建就能立即执行.
>	   3)提高线程的可管理性,线程是稀缺资源,如果无线的创建,不仅会消耗系统资源还会降低系统的稳定性,使用线程池可以进行统一的分配,调优和监控.

### 32.sychronized和ReentrantLock的区别

> ReentrantLock比sychnronized多了几个高级功能:
> 1.等待可中断:在持有锁的线程长时间不释放锁的时候,等待线程可以选择放弃等待
> 2.公平锁:按照申请锁的顺序你来一次获得锁称为公平锁,sychnroized是非公平锁,而ReentrantLock可以通过构造函数实现公平锁
> 3.可以绑定多个condition:通过多个condition对象简单地实现比较复杂的线程同步的功能

### 33.Spring的IOC和AOP的实现

> IOC:控制反转主要是将对象的生命周期和对象间的关系交给spring容器来负责控制.实现形式主要有依赖查找和依赖注入(设值注入和构造注入)
> AOP:,面向切面编程,主要通过反射实现动态代理的方式实现(invocationhandler)

### 34.spring中bean的创建过程

> 在ApplicationContext初始化后,用户调用getBean()时的执行的操作:
> 1.Spring容器从BeanDefinitionRegistry中去除加工后的BeanDefinition,并调用InstantiationStrategy进行Bean实例化
> 2.实例化时,Spring容器使用BeanWrapper对Bean进行封装,BeanWrapper提供了很多以Java反射机制操作Bean的方法,它将结合Bean的BeanDefinition以及容器中的属性编辑器,完成bean属性的设置工作
> 3.利用容器中注册的BeanPostProcessor对已经完成属性设置工作的Bean进行后续加工,装配处一个准备就绪的Bean
