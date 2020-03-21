# Оператор SQL BETWEEN

Оператор BETWEEN выбирает значения в заданном диапазоне. Значения могут быть числами, текстом или датами.

## BETWEEN Синтаксис

``` SQL
SELECT  column_name(s) FROM table_name WHERE  column_name BETWEEN value1 AND value2;
```

## Примеры

Выбрать все продукты с ценами от 10 до 20 из таблицы "Products":
``` SQL
SELECT * FROM Products WHERE Price BETWEEN  10  AND  20;
```
---

Выбрать все продукты за пределами диапазона цен от 10 до 20 из таблицы "Products":
``` SQL
SELECT * FROM Products WHERE Price NOT BETWEEN  10  AND  20;
```
---

Выбрать все продукты с ценами между 10 и 20, но не показывать продукты с CategoryID 1,2 или 3:
``` SQL
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20 AND CategoryID NOT  IN (1,2,3);
```
---

Выбрать все продукты с ProductName МЕЖДУ "Carnarvon Tigers" и "Mozzarella di Giovanni":
``` SQL
SELECT * FROM Products WHERE ProductName BETWEEN  'Carnarvon Tigers' AND 'Mozzarella di Giovanni' ORDER BY ProductName;
```
---

Выбрать все продукты с ProductName  НЕ МЕЖДУ "Carnarvon Tigers" и "Mozzarella di Giovanni":
``` SQL
SELECT * FROM Products WHERE ProductName BETWEEN  'Carnarvon Tigers' AND 'Mozzarella di Giovanni' ORDER BY ProductName;
```
---

Выбрать все заказы с OrderDate между '01 -July-1996' и '31 -July-1996':
``` SQL
SELECT * FROM Orders WHERE OrderDate BETWEEN #01/07/1996# AND #31/07/1996#;
```
или
``` SQL
SELECT * FROM Orders WHERE OrderDate BETWEEN  '1996-07-01'  AND  '1996-07-31';
```
