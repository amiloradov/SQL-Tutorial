# SQL  INNER JOIN

INNER JOIN выбирает записи, которые имеют совпадающие значения в обеих таблицах.

> **Примечание**. INNER JOIN выбирает все строки из обеих таблиц, если между столбцами есть совпадение. Если в первой таблице есть записи, у которых нет совпадений во второй таблицей, эти результаты не будут отображаться!

![INNER JOIN](/Images/img_innerjoin.gif)

## INNER JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
INNER JOIN table2 
ON table1.column_name = table2.column_name;
```

### Таблица "Orders"

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
|--|--|--|--|--|
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |
---

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |

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

---

[НАЗАД](/SQL_Tutorial/SQL_Join.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_LEFT_JOIN.md)

