# 聚合函数Aggregate function



**返回列合计值（SUM）：**注：sum只要ALL与DISTINCT两种计数规范，无\*。计算学生年龄之和：

```text
SELECT SUM(student_age) FROM t_student;
```

**返回列平均值（AVG）：**

计算学生平均年龄：

```text
SELECT AVG(student_age)FROM t_student;
```



**执行列、行计数（count）：**标准格式

```text
SELECT COUNT(<计数规范>) FROM <表名>
```

