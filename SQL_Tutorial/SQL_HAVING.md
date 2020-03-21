# SQL  HAVING

HAVING было добавлено в SQL, поскольку ключевое слово WHERE не может использоваться с агрегатными функциями.

## HAVING Синтаксис

``` SQL
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
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

Перечислить количество клиентов в каждой стране. Включите только страны с более чем 5 клиентами:
``` SQL
SELECT COUNT(CustomerID), Country
FROM Customers  
GROUP BY Country  
HAVING COUNT(CustomerID) > 5;
```
---

Перечислить количество клиентов в каждой стране, отсортированное по убыванию (только страны с более чем 5 клиентами):
``` SQL
SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country  
HAVING COUNT(CustomerID) > 5  
ORDER BY COUNT(CustomerID) DESC;
```
---

Перечислить сотрудников из таблицы "Employees", которые зарегистрировали более 10 заказов из таблицы "Orders":
``` SQL
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders  
FROM (Orders  
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)  
GROUP BY LastName  
HAVING COUNT(Orders.OrderID) > 10;
```
---

Указывает, зарегистрировали ли сотрудники «Davolio» или «Fuller» более 25 заказов:
``` SQL
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders  
FROM Orders  
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID  
WHERE LastName = 'Davolio' OR LastName = 'Fuller'  
GROUP BY LastName  
HAVING COUNT(Orders.OrderID) > 25;
```

