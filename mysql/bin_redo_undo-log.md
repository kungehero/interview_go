# 日志类型分析
## bin log
```
存储mysql的写操作日志记录，属于归档日志。
```
## redo log
```
保证事务的持久性
```
## undo log
```
保证事务的原子性，存储相反的操作语句，记录了数据的逻辑变化，回滚到事务之前的数据状态。
```
