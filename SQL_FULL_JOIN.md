# SQL  FULL OUTER JOIN

FULL OUTER JOIN возвращает все записи, когда есть совпадение в левой (table1) или правой (table2) табличных записях.

> **Примечание**. FULL OUTER JOIN потенциально может возвращать очень большие наборы результатов!
> FULL OUTER JOIN и FULL JOIN - это одно и то же.

![FULL OUTER JOIN](/images/img_fulljoin.gif)

## FULL OUTER JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```

## Примеры

Выбрать всех клиентов из таблицы Customers и все заказы из таблицы Orders:
``` SQL
SELECT Customers.CustomerName, Orders.OrderIDEmployees.FirstName
FROM Customers
FULL  OUTER  JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```

> **Примечание.** FULL OUTER JOIN возвращает все совпадающие записи из обеих таблиц, независимо от того, совпадает другая таблица или нет. Таким образом, если в «Customers» есть строки, у которых нет совпадений в «Orders», или если в «Orders» есть строки, у которых нет совпадений в «Customers», эти строки также будут перечислены.
