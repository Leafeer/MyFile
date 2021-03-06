## C#学习记录
这里做一下随意的C#学习记录，可能会有些零散  
大概截止到11.10号，期望目标是  
1. 完成菜鸟教程的文档
2. 完成五道算法题目

今天是11.6号
1. 目前菜鸟文档已经看完了三分之一
2. 试图理解哈希表算法的实际运用中
这个页面会随时动态更新，不会留档

---
### C# 封装
1. public：所有对象都可以访问；
2. private：对象本身在对象内部可以访问；
3. protected：只有该类对象及其子类对象可以访问
4. internal：同一个程序集的对象可以访问；
5. protected internal：访问限于当前程序集或派生自包含类的类型。 
   
- public事件，地球人都知道，全公开
- protected事件，A，B，D知道（A和他的所有儿子知道，妻子C不知道）
- private事件，只有A知道（隐私？心事？）
- internal事件，A，B，C知道（A家里人都知道，私生子D不知道）
- protected internal事件，A，B，C，D都知道,其它人不知道
---
### C#方法
int型参数

int 型参数通过值传递的方式将数值传入方法中，即我们在Java中常见的方法。


一个用关键字 ref 标示，一个用 out 标示。

牵扯到数据是引用类型还是值类型。

一般用这两个关键字你是想调用一个函数将某个值类型的数据通过一个函数后进行更改。传 out 定义的参数进去的时候这个参数在函数内部必须初始化。否则是不能进行编译的。ref 和 out 都是传递数据的地址，正因为传了地址，才能对源数据进行修改。

一般情况下不加 ref 或者 out 的时候，传值类型的数据进去实际上传进去的是源数据的一个副本，也就是在内存中新开辟了一块空间，这里面存的值是与源数据相等的，这也就是为什么在传值类型数据的时候你如果不用 return 是无法修改原值的原因。但是你如果用了 ref,或者 out，这一切问题都解决了，因为他们传的是地址。

out 比起 ref 来说，还有一个用法就是可以作为多返回值来用，都知道函数只能有一个返回值，C#里，如果你想让一个函数有多个返回值，那么OUT能很容易解决。

ref型参数

该种类型的参数传递变量地址给方法（引用传递），传递前变量必须初始化。


该类型与out型的区别在与：

 1. ref 型传递变量前，变量必须初始化，否则编译器会报错, 而 out 型则不需要初始化
 2. ref 型传递变量，数值可以传入方法中，而 out 型无法将数据传入方法中。换而言之，ref 型有进有出，out 型只出不进。
out 型参数

与 ref 型类似，仅用于传回结果。

注意：

1. out型数据在方法中必须要赋值，否则编译器会报错。

eg:如下图若将代码中的sum1方法的方法体

改为 a+=b; 则编译器会报错。原因：out 型只出不进，在没给 a 赋值前是不能使用的

改为 b+=b+2; 编译器也会报错。原因：out 型数据在方法中必须要赋值。

2. 重载方法时若两个方法的区别仅限于一个参数类型为ref 另一个方法中为out，编译器会报错

eg：若将下面的代码中将方法名 vsum1 改为 sum（或者将方法名 sum 改为 sum1），编译器会报错。