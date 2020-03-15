# SQL  INNER JOIN

INNER JOIN выбирает записи, которые имеют совпадающие значения в обеих таблицах.

> **Примечание**. INNER JOIN выбирает все строки из обеих таблиц, если между столбцами есть совпадение. Если в первой таблице есть записи, у которых нет совпадений во второй таблицей, эти результаты не будут отображаться!

![INNER JOIN](/images/img_innerjoin.gif)

## INNER JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
INNER JOIN table2 
ON table1.column_name = table2.column_name;
```

## Примеры

Выбрать все заказы из таблицы Orders с информацией о клиенте из таблицы Customers:
``` SQL
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER  JOIN  Customers ON Orders.CustomerID = Customers.CustomerID;
```
---

Выбрать все заказы из таблицы Orders с информацией о клиенте из таблицы Customers и грузоотправителе из таблицы Shippers:
``` SQL
SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM  ((Orders
INNER  JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER  JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
```
