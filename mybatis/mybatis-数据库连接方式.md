
## 一、访问数据库的方式
### 1、使用 JDBC方式

#### 代码流程
```
1、注册数据库驱动类 ，明确指定数据库 URL 地址、数据库用户名、密码等连接信息 
2、通过 DriverManager 打开数据库连接
3、通过数据库连接创建 Statement对象
4、通过 Statement对象执行 SQL语句，得到 ResultSet对象。
5、通过 ResultSet 读取数据，并将数据转换成 JavaBean 对象
6、关闭 ResultSet、 Statement 对象以及数据库连接，释放相关资源
```

#### 问题
+ 上述的过程中，存在些许问题
##### 问题一
+ 步骤1-4以及6：
    + 在每次查询中都会出现，在保存、更新、删除等其他数据库操作中也存在类似的重复性代码，
    + 解决这个问题：将重复代码封装到一个类似的DBUtils中
+ 步骤5：
    + 关系模型到对象模型的转换
    + 解决这个问题：ORM框架，实现比较通用的方式封装这种复杂的转换是比较困难的

> ORM:Object Relational Mapping,对象关系映射

#### 2、使用 Hibernate 
+ Hibernate是一款Java世界中最著名的ORM框架之一,通过hbm.xml映射文件维护Java类与数据库表的映射关系。

#### 3、使用 Spring JDBC
+ SpringJDBC并不能算是一个ORM框架，它仅仅是使用模板方式对原生JDBC 进行了一层非常薄的封装

#### 4、Mybatis
> 前身为Apache支持的开源项目iBatis
+ mybatis通过映射配置文件或相应注解将ResultSet映射为Java对象，其映射规则可以嵌套其他映射规则以及子查询，从而实现复杂的映射逻辑，也可以实现一对一、一对多、多对多映射以及双向映射。


## 对比

<table>
    <tr>
        <td>连接方式</td>
        <td>性能方面</td>
        <td>可移植性</td>
        <td>开发效率</td>
    </tr>
    <tr>
        <td>SpringJDBC</td>
        <td >用原生SQL语句，优化空间比较大，但没有良好的缓存机制</td>
        <td rowspan = "2">暂无很好的支持</td>
        <td>通过 ORM 化的 Callback 的方式进行映射</td>
    </tr>
    <tr>
        <td>MyBatis</td>
      <td rowspan = "2">生成的SQL语句难以优化，有良好的缓存机制</td>
        <td rowspan = "2">都提供了XML 映射配置文件和注解两种方式实现映射</td>
         </tr>
          <tr>
        <td>Hibernate</td>
        <td>帮助开发人员屏蔽了底层数据</td>
    </tr>
</table>



### 参考资料
+ [https://blog.csdn.net/qq_18860653/article/details/80605690](https://blog.csdn.net/qq_18860653/article/details/80605690)
+ 《Mybatis技术内幕》
+ [官网文档](https://mybatis.org/mybatis-3/zh/index.html)
