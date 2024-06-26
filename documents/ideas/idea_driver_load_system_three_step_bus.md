# 思索：如何让驱动能够在运行时加载，或者更广泛的来讲，按需加载？

## 问题：
* 驱动与驱动之间会形成互相的依赖关系嘛？

## 思路一-运行时加载
对于运行时加载，常见的解决方案是设计一套二进制的约定，约定被加载的模块应该位于什么位置，有哪些入口方法

### 问题&难点：
* 这意味着我们还需要引入文件系统的概念
* 二进制约定这个很好解决，只要让模块能够返回驱动实例的创建函数与模块的描述信息即可。
* ..待进一步思索

## 思路二-可选编译
不如这样想：反正对于现代的语言工具链来说，临时编译一份并非难事，既然如此，为什么不即用即编译呢？

### 问题&难点：
* 需要引入处理编译的额外脚本，对于rust,虽然rust提供了强大的build.rs，但是可能仍然不太够，主要涉及到一些语法上的限制，比如trait object安全
  * 话说回来，真的有必要只使用rust嘛？
* ..待进一步思索

## 大体架构思路：
对于这类需要在一个系统主体上加载额外的模块(mod/plugin/extension)的需求，其应对策略可以说是百花齐放，不过大多都脱不开接下来的框架：

对于我们的系统，设计如下：

* 集合:
  * 模块集合(Module Collection)：其上应该存放各驱动的入口函数，系统可以在每次枚举设备的时候使用该总线，以获取合适的对应设备的驱动
  * 实体集合(Entity Collection)：其上存放被引用的数据结构，在我们的项目中，具体来说，里面包含的是设备的抽象结构(端点,设备描述符...etc)

* 加载流程:
  * 模块预初始化(PreInit): 在这一步，确定要加载的模块都有哪些，并在整理好他们的加载次序(可能存在互相依赖的关系) 后将其存入临时集合
  * 模块初始化(Init): 这一步比较简单-根据确定好的加载顺序进行模块的载入操作，具体的来说，将他们塞进模块集合.

### 设备枚举:
对于一个设备，可以这么进行他的设备初始化：
* 遍历：将模块集合遍历一遍，第一个能够有能力处理这个设备的就是我们要找的驱动
* 键值对：根据设备的特征(class,subclass,protocol)进行驱动的索引

注：这两种综合起来看其实都行，大差不差。

