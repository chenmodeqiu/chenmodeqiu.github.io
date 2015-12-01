# diandi.github.io
点滴blog
# oc和c语言对比
---

##1.源文件对比
- C语言中常见源文件.h头文件，.c文件

|文件扩展名|源类型|
|---|---|
|.h|头文件，用于存放函数声明|
|.c|C语言源文件，用于实现头文件中声明的方法|

- OC中的源文件.h头文件，.m与.mm的实现文件

|文件扩展名|源类型|
|---|---|
|.h|头文件，头文件包含类、方法、属性的声明。|
|.m/.mm|类的实现文件，参与编译的文件，用来实现类中声明的方法|

—

##2.关键字对比
- C语言的关键字都可以在OC源程序中使用
- OC新增的关键字在使用时,注意部分关键字以"@“开头

##3.数据类型对比
- C语言数据类型

![](http://7xj0kx.com1.z0.glb.clouddn.com/数据类型.png)
- OC数据类型

![](http://7xj0kx.com1.z0.glb.clouddn.com/数据类型2.png)

|类型|描述|
|---|---|
|BOOL|只有两个取值真和假|
|NSObject *|OC中的对象类型|
|id|动态对象类型，万能指针|
|SEL|选择器数据类型|
|block|代码块数据类型|

##4.流程控制语句对比
- OC增强for循环
```
for (NSString * name in NSArray){
    NSLog(@”%@”,name);
}
```


- 注意: 方法只能写在类里面, 而函数可以写在任何地方
    + 对象方法，使用对象调用的方法
    + 类方法，使用类名调用的方法

```
对象方法
- (id)initWithString: (NSString * )name;

类方法
+ (MyClass *)createMyClassWithString: (NSString *)name;
```

##5.面向对象新增语法
- 属性生成器
    + @property
    + @synthesize

```
//声明属性
@property (nonatomic,strong)NSString * name;

//合成属性
@synthesize name = _name;
```
- 分类
    + 分类与继承
    + 使用分类扩展类,无需子类化

```
@interface NSString (MyNSString)

- (NSString *) encryptWithMD5;

@end
```
- 协议
    + 使用协议声明方法
    + 协议类似于C#，java中的接口

```
@protocol MyProtocol

- (void)myProtocolMethod;

@end
```
---

##6.新增异常处理
- 用于处理错误信息
- 格式:
    + @try .... @catch .... @finally

- 示例

```
//创建对象car
Car *car = [Car new];
@try {
//调用一个没有实现的方法
[car test];
 }@catch (NSException *exception) {
       NSLog(@"%@",exception.name);
}@finally {
 NSLog(@"继续执行!\n");
}
```
---
