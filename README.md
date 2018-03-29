# xmappr-extend
扩展xmappr支持对应的xml路径映射
使用说明地址：https://www.jianshu.com/p/772e9b823aab
Xmappr功能扩展说明

												---- 余家奎
一、Xmappr介绍
Xmappr是一个使用纯Java编写的处理XML的类库，提供一种非常简单的方式来处理XML，可以将任意XML与Java类相映射，具体可以参考https://code.google.com/archive/p/xmappr/

主要特性：
（1）映射通过注释或外部配置实现
（2）可以缓存未映射元素
（3）保持XML元素顺序
（3）可以自定义类型转换器
（4）完全支持XML命名空间
（5）线程安全（设计用于多线程使用）
（6）不包含任何依赖关系
（7）整个类库大小只有80kb
（8）	采用BSD许可
二、需求
尽管Xmappr本身已经提供了很大的功能，但是其不能跨越XML对应的层次结构进行XML和java bean进行映射，比如下面的场景：
 
传统的Xmappr就会是一个XML节点就要和java bean中的属性进行映射，但是实际情况是不能按照XML节点来定义自己的java bean，有些XML对应的节点可能在java bean并不存在与之对应的属性，因为需要一个指定xml路径与java bean之间映射的功能，如下面配置所示：
 

三、改造
改造思路是将每一个XML节点对应的父节点的路径传下来，这样就能使用XML对应的从根一直下来的绝对路径来表示。
对应上面的java类：
 
 
 
四、使用说明
1. mvn坐标
已经将修改之后的代码上传到私仓中，对应的mvn坐标为：
<dependency>
			<groupId>org.xmappr</groupId>
			<artifactId>xmappr</artifactId>
			<version>0.9.5-ctim</version>
</dependency>
2. 调用说明
 


