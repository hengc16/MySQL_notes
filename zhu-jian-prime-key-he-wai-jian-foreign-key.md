# 主键\(prime key\)和外键\(foreign key\)

### SQL PRIMARY KEY Constraint

The `PRIMARY KEY` constraint uniquely identifies each record in a table.

Primary keys must contain UNIQUE values, and cannot contain NULL values.

A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns \(fields\).

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

### SQL FOREIGN KEY Constraint

The `FOREIGN KEY` constraint is used to prevent actions that would destroy links between tables.

A `FOREIGN KEY` is a field \(or collection of fields\) in one table, that refers to the [`PRIMARY KEY`](https://www.w3schools.com/sql/sql_primarykey.asp) in another table.

The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```

删除有外键关系的表的时候，必须要先删除引用别人的表\(从表\)，在删除被引用的表（主表）。

通过alter 去添加外键

```sql
ALTER TABLE Orders 
ADD CONSTRAINT `FK_PersonOrder` FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

不建议使用外键在数据库层面， 一切外键必须在应用层面解决。（java 去写）

**每次delete或者update都必须考虑外键约束，导致开发和测试极为不方便。**

