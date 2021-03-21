# CRUD

### create:

```java
public static void main(String[] args){
    Connection connection = null;
    PrepareStatement st = null;
    try{
        connection = DaoUtils.getConnection();
        String sql = "insert into users(id, `name`,`date`) values(?,?);
        //预先编译sql，不执行。
        st = connection.prepareStatement(sql);
        st.setInt(1,4) //下表为1， 赋值4.
        st.setString(2, "zhangsan");
        st.setDate(3, new java.sql.Date(new Date().getTime()));
        //执行
        st.excuteUpdate();
    }
    catch(SQLException e){
        e.printStackTrace();
    }finally{
        connection.close();
        st.close();
    }
    
}
```

### Delete



```java
public static void main(String[] args){
    Connection connection = null;
    PrepareStatement st = null;
    try{
        connection = DaoUtils.getConnection();
        String sql = "delete from users where id =?";
        
        //预先编译sql，不执行。
        st = connection.prepareStatement(sql);
        st.setInt(1,4) //下表为1， 删除id 为4 的user
        //执行
        st.excuteUpdate();
    }
    catch(SQLException e){
        e.printStackTrace();
    }finally{
        connection.close();
        st.close();
    }
    
}
```

### Update

```java
public static void main(String[] args){
    Connection connection = null;
    PrepareStatement st = null;
    try{
        connection = DaoUtils.getConnection();
        String sql = "update users set `NAME` =? where id=?";
        //预先编译sql，不执行。
        st = connection.prepareStatement(sql);
        st.setString(1,"zhangsan") //下表为1， 赋值4.
        st.setInt(2, 4);
        //执行
        st.excuteUpdate();
    }
    catch(SQLException e){
        e.printStackTrace();
    }finally{
        connection.close();
        st.close();
    }
    
```

### Read

```java
public static void main(String[] args){
    Connection connection = null;
    PrepareStatement st = null;
    ResultSet rs = null;
    try{
        connection = DaoUtils.getConnection();
        String sql = "select * from users where id = ?";
        //预先编译sql，不执行。
        st = connection.prepareStatement(sql);
        st.setInt(1,4) //下表为1， 赋值4.
        st.setString(2, "zhangsan");
        st.setDate(3, new java.sql.Date(new Date().getTime()));
        //执行
        st.excuteUpdate();
    }
    catch(SQLException e){
        e.printStackTrace();
    }finally{
        connection.close();
        st.close();
    }
    
}
```



