H2在测试中的使用
===========

# 关注特性

前面我们介绍了H2的众多特性，其中有部分特性是我们关注的重点：

- java编写
- ++支持标准SQL，JDBC API++
- **支持嵌入式模式**和服务器模式，支持集群
- **兼容模式，适用于IBM DB2, Apache Derby, HSQLDB, MS SQL Server, MySQL, Oracle, and PostgreSQL**
- ++小巧(jar文件大概1.5 MB大小), 内存要求低++

# 适用场景

这几个特性，使得H2非常的适合用于数据库访问层的自动化，典型场景：

- 以嵌入式模式在Java测试案例中启动
- 模拟其他数据库如mysql/Oracle/PostgreSQL
- 提供标准JDBC支持，构建DataSource/Connection等
- 使得数据库访问层的代码可以在H2的基础上运行/测试/验证

在使用H2模拟mysq/oracle/postgresql等真实数据库之后，涉及数据库访问的功能模块的测试就变得方便而且容易自动化，在此基础上，持续集成/CI也就方便了。

# 限制

H2对其他数据库的替代，毕竟停留在模拟的层次上，不可能在所有的细节上都和原数据库完全一致。因此如果涉及到比较偏门的数据库独有特性，可能无法模拟。