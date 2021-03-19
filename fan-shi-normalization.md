# 范式\(normalization）

[https://zhuanlan.zhihu.com/p/20028672](https://zhuanlan.zhihu.com/p/20028672)

**1NF的定义为：符合1NF的关系中的每个属性都不可再分。**

  
但是仅仅符合1NF的设计，仍然会存在数据冗余过大，插入异常，删除异常，修改异常的问题，例如对于**表3**中的设计：

![](.gitbook/assets/image%20%2810%29.png)

