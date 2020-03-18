# SQL  LEFT JOIN

LEFT JOIN возвращает все записи из левой таблицы (table1) и соответствующие записи из правой таблицы (table2). Результат равен NULL с правой стороны, если совпадений нет.

> **Примечание**. В некоторых базах данных LEFT JOIN называется LEFT OUTER JOIN.
> 

![LEFT JOIN](/Images/img_leftjoin.gif)

## LEFT JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
LEFT JOIN table2
ON table1.column_name = table2.column_name;
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

Выбрать всех клиентов из таблицы Customers и любые заказы из таблицы Orders, которые они могут иметь :
``` SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT  JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER  BY Customers.CustomerName;
```

> LEFT JOIN возвращает все записи из левой таблицы (Клиенты), даже если в правой таблице нет совпадений (Заказы).
