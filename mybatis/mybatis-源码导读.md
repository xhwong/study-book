[toc]


### 一、Mybatis架构划分

+ 整体架构分为三层，分别是**基础支持层**、**核心处理层**和**接口层**，如下所示：

1. 接口层：定义了Mybatis暴露给应用程序调用的API，与上次交互的桥梁。
2. 核心处理层：实现了Mybaits的核心处理流程，其中包括Mybatis的初始化以及完成一次数据库操作涉及的全部流程
3. 基础支持层：包含整个Mybatis的基础模块，这些模块为核心处理层的功能提供了良好的支撑
![基础架构图](https://user-images.githubusercontent.com/18548200/68659957-3e21c580-0573-11ea-8b2a-2f4138af4c8d.png)


### 二、源码分析
+ 首次读源码，最好结合自身的使用经验来看，理清主线，其他的边角功能平时很少用到，了解其功能即可，主要细节暂时跳过。

#### 1、配置初始化
+ config文件解析（☆☆☆☆☆）
+ mapper文件解析（☆☆☆☆☆）
+ statement配置~SQL节点解析（☆☆☆☆☆）
+ Binding模块（☆☆☆☆☆）
+ 解析器模块（☆☆☆）
+ 反射模块（☆☆☆）
+ 注解模块（☆☆）
+ 数据源模块（☆）
+ IO资源加载模块（☆）
+ 事务模块（☆）

#### 2、SQL语句与执行
> 这一部分表示都很重要（☆☆☆☆☆）

+ SQL语句与参数值组装
+ SQL执行
+ SQL结果解析

#### 3、其他
+ Mybatis-plus（☆☆☆）
+ Mybatis-spring（☆☆☆）
+ 插件模块（☆）

### 参考资料
+ 《Mybatis技术内幕》
+ [https://mybatis.org/mybatis-3/zh/index.html](https://mybatis.org/mybatis-3/zh/index.html)

