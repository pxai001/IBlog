### 格式化
```java
SimpleDateFormat oldFormatter=new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.sss");
Date date=new Date();
oldFormatter.format(date);
DateTimeFormatter newFormatter=DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss.sss");
LocalDateTime date=LocalDateTime.now();
date2.format(newFormatter);
```
### 解析
```java
String dateStr="2022-01-01 08:00:00.000";
SimpleDateFormat oldFormatter=new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.sss");
Date oldDate=oldFormatter.parse(dateStr);
DateTimeFormatter newFormatter=DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss.sss");
LocalDateTime localDateTime=LocalDateTime.parse(dateStr,newFormatter);
// 转换
Date date=Date.from(localDateTime.atZone(ZoneId.systemDefault()).toInstant());
LocalDateTime localDateTime=
new Date().toInstant().atZone(ZoneId.systemDefault()).toLocalDateTime();
```