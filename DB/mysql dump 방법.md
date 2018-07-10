# mysql dump 방법
## export
mysqldump database이름 -u 유저id -p -h localhost > dump.sql

## import
mysql -u username -p –database=guestdb < guestTbl.sql

### mysqlworkbench도 가능
server -> data export