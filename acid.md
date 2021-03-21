# 事务\(transaction\)ACID



* **Atomic** – Transaction acting on several pieces of information complete only if all pieces successfully save.   Here, “all or nothing” applies to the transaction.
* **Consistent** – The saved data cannot violate the integrity of the database. Interrupted modifications are rolled back to ensure the database is in a state before the change takes place.
* **Isolation** – No other transactions take place and affect the transaction in question.   This prevents “mid-air collisions.”
* **Durable** – System failures or restarts do not affect committed transactions. 

### 原子性\(atomic\)

* 要么都成功，要么都失败

### 一致性\(consistent\)

* 事务前后数据保持一致，如转账总额不变。

### 持久性\(Durable\)

* 一旦提交不可逆，数据将持久化到数据库中

### 隔离性\(isolation\)

* 多个用户并发访问数据时，数据库为每个用户开启一个事务，彼此之间相互隔离。有4种隔离等级。

### 隔离性问题：

**脏读：dirty read**

* 指一个事务读取了另外一个事务未提交数据。

**不可重复读：unrepeatable read**

* 在一个事务内读取表中的某一行数据，多次读取结果不同。

**幻读：phantom read**

* 指在一个事务内读取了别的事务插入的数据，导致前后不一致。

![](.gitbook/assets/image%20%2826%29.png)

