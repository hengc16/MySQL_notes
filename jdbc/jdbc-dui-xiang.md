# jdbc对象

### Connection：

连接数据库，connection代表数据库对象。

```java
Connection connection = DriverManager.getConnection(url,username,password);
connection.rollback();
connection.commit();
connection.setAutoCommit();
```

### Statement:

![](../.gitbook/assets/image%20%2835%29.png)

执行sql的对象。

```java
Statement statement = connection.createStatement();
statement.excuteQuery() //查询操作返回resultset
statement.exucte() //执行任何sql
statement.executeUpdate() // 更新。插入，删除，都要用这个。
```

### ResultSet

结果对象

```java
String sql = "SELECT * FROM users";
ResultSet resultSet = statement.excuteQuery(sql);
//拿结果
resultSet.getObject();
//遍历
resultSet.next();
```

### 释放资源

```java
resultSet.close();
statement.close();
connection.close();
```

