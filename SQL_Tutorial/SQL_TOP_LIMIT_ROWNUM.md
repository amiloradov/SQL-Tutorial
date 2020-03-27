# SQL TOP, LIMIT и ROWNUM

TOP, LIMIT и ROWNUM используется для указания количества возвращаемых записей.

>**Примечание.**  MySQL поддерживает предложение LIMIT для выбора ограниченного числа записей, в то время как Oracle использует ROWNUM. Остальные SELECT TOP.

## Синтаксис TOP (SQL Server / MS Access)

``` SQL
SELECT TOP number|percent column_name(s) FROM  table_name WHERE condition;
```

## Синтаксис LIMIT (MySQL)

``` SQL
SELECT column_name(s) FROM table_name WHERE  condition LIMIT number;
```

## Синтаксис ROWNUM (Oracle)

``` SQL
SELECT column_name(s) FROM table_name WHERE ROWNUM <= number;
```
## Примеры

Выбрать первые три записи из таблицы «Customers» с помощью TOP (для SQL Server / MS Access):
``` SQL
SELECT  TOP  3 * FROM Customers;
```
___
Выбрать первые три записи из таблицы «Customers»  с помощью LIMIT (для MySQL):
``` SQL
SELECT * FROM Customers LIMIT  3;
```
___
Выбрать первые три записи из таблицы «Customers»  с помощью ROWNUM (для Oracle):
``` SQL
SELECT * FROM Customers WHERE ROWNUM <= 3;
```
___________
Выбрать первые 50% записей из таблицы «Customers» (для SQL Server / MS Access):
``` SQL
SELECT  TOP  50  PERCENT * FROM Customers;
```
___
Выбрать первые три записи из таблицы «Customers», где страна - «Belarus» (для SQL Server / MS Access):
``` SQL
SELECT  TOP  3 * FROM Customers WHERE Country='Belarus';
```
___
Выбрать первые три записи из таблицы «Customers», где страна - «Belarus» с помощью ROWNUM (для Oracle):
``` SQL
SELECT * FROM Customers WHERE Country='Belarus'  AND ROWNUM <= 3;
```
