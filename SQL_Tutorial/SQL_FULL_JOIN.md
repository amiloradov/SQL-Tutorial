# SQL  FULL OUTER JOIN

FULL OUTER JOIN возвращает все записи, когда есть совпадение в левой (table1) или правой (table2) табличных записях.

> **Примечание**. FULL OUTER JOIN потенциально может возвращать очень большие наборы результатов!
> FULL OUTER JOIN и FULL JOIN - это одно и то же.

![FULL OUTER JOIN](/Images/img_fulljoin.gif)

## FULL OUTER JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |
---

### Таблица "Orders"

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
|--|--|--|--|--|
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

## Примеры

Выбрать всех клиентов из таблицы Customers и все заказы из таблицы Orders:
``` SQL
SELECT Customers.CustomerName, Orders.OrderIDEmployees.FirstName
FROM Customers
FULL  OUTER  JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```

> **Примечание.** FULL OUTER JOIN возвращает все совпадающие записи из обеих таблиц, независимо от того, совпадает другая таблица или нет. Таким образом, если в «Customers» есть строки, у которых нет совпадений в «Orders», или если в «Orders» есть строки, у которых нет совпадений в «Customers», эти строки также будут перечислены.
