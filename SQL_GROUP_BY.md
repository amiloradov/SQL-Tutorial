# Оператор SQL  GROUP BY

GROUP BY группирует строки с одинаковыми значениями в итоговые строки, например, «найти количество клиентов в каждой стране».

-   Оператор GROUP BY часто используется с агрегатными функциями (COUNT, MAX, MIN, SUM, AVG) для группировки набора результатов по одному или нескольким столбцам.

## GROUP BY Синтаксис

``` SQL
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |


## Примеры

Указывает количество клиентов в каждой стране из таблицы «Customers»:
``` SQL
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;
```
---

Перечислить количество клиентов в каждой стране, отсортированное по убыванию:
``` SQL
SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country  
ORDER BY COUNT(CustomerID) DESC;
```

### GROUP BY c JOIN

Перечислить количество заказов (Order), отправленных каждым грузоотправителем (Shippers):
``` SQL
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders 
FROM  Orders  
LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID  
GROUP BY ShipperName;
```
