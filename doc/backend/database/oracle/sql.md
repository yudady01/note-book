# date


## oracle日期
```
TO_DATE('2012-07-18 13:27:18', 'YYYY-MM-DD HH24:MI:SS')
```


## 查询oracle登入者资讯
```

select to_char(timestamp,'YYYY-MM-DD HH24:MI:SS') as login_time , p.* from DBA_AUDIT_TRAIL p 
where timestamp > TO_DATE('2018-03-29 18:00:27', 'YYYY-MM-DD HH24:MI:SS') 
order by login_time desc;

```


## oracle flashback
```
SELECT * FROM PY_SYSTEM_CONFIG AS OF TIMESTAMP TO_TIMESTAMP('2018-03-31 09:20:00', 'YYYY-MM-DD HH:MI:SS')
```

## oracle db user drop and create
```
drop user myPay024 cascade;

create user myPay024 identified by myPay024;

GRANT ALL privileges TO myPay024;

GRANT sysdba TO myPay024;

GRANT dba TO myPay024;
```



## create dblink
CREATE DATABASE LINK mypay009 CONNECT TO myPay IDENTIFIED BY fSDd4860dj
USING
'(DESCRIPTION=(ADDRESS_LIST =(ADDRESS = (PROTOCOL = TCP)(HOST = 10.140.0.24)(PORT = 1521)))(CONNECT_DATA = (SERVICE_NAME =myPay)) )'

--SELECT * FROM py_order@mypay009

--DROP DATABASE LINK mypay009;

## oracle length

```
SELECT ORDER_NO,CLIENT_IP FROM PY_ORDER WHERE lengthb(CLIENT_IP) > 40;

```




cat /mnt/nfs/var/rd2/callback.log | grep 201804110090005041
cat /mnt/nfs/var/rd3/callback.log | grep 201804110090005041
cat /mnt/nfs/var/rd3-1/callback.log | grep 201804110090005041
cat /mnt/nfs/var/rd3-2/callback.log | grep 201804110090005041