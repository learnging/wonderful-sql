# 练习一：行转列
假设有如下比赛结果
```plain
+------------+-----------+
|    cdate   |   result  |
+------------+-----------+
|  2021-1-1  |     胜    |
|  2021-1-1  |     负    |
|  2021-1-3  |     胜    |
|  2021-1-3  |     负    |
|  2021-1-1  |     胜    |
|  2021-1-3  |     负    |
+------------+-----------+
```
请使用 SQL 将比赛结果转换为如下形式：
```plain
+------------+-----+-----|
|  比赛日期   | 胜  | 负  |
+------------+-----------+
|  2021-1-1  |  2  |  1  |
|  2021-1-2  |  2  |  1  |
+------------+-----------+
```
# 练习二：列转行
假设有如下比赛结果
```plain
+------------+-----+-----|
|  比赛日期   | 胜  | 负  |
+------------+-----------+
|  2021-1-1  |  2  |  1  |
|  2021-1-2  |  2  |  1  |
+------------+-----------+
```
请使用 SQL 将比赛结果转换为如下形式：
```plain
+------------+-----------+
|    cdate   |   result  |
+------------+-----------+
|  2021-1-1  |     胜    |
|  2021-1-1  |     负    |
|  2021-1-3  |     胜    |
|  2021-1-3  |     负    |
|  2021-1-1  |     胜    |
|  2021-1-3  |     负    |
+------------+-----------+
```
# 练习三：连续登录

有用户表行为记录表t_act_records表，包含两个字段：uid（用户ID），imp_date（日期）

1. 计算2021年每个月，每个用户连续登录的最多天数
2. 计算2021年每个月，连续2天都有登录的用户名单
3. 计算2021年每个月，连续5天都有登录的用户数

构造表mysql如下：
```sql
DROP TABLE if EXISTS t_act_records;
CREATE TABLE t_act_records
(uid  VARCHAR(20),
imp_date DATE);

INSERT INTO t_act_records VALUES('u1001', 20210101);
INSERT INTO t_act_records VALUES('u1002', 20210101);
INSERT INTO t_act_records VALUES('u1003', 20210101);
INSERT INTO t_act_records VALUES('u1003', 20210102);
INSERT INTO t_act_records VALUES('u1004', 20210101);
INSERT INTO t_act_records VALUES('u1004', 20210102);
INSERT INTO t_act_records VALUES('u1004', 20210103);
INSERT INTO t_act_records VALUES('u1004', 20210104);
INSERT INTO t_act_records VALUES('u1004', 20210105);
```
# 练习四：hive 数据倾斜的产生原因及优化策略？




















