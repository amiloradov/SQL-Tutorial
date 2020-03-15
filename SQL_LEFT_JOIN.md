# SQL  LEFT JOIN

LEFT JOIN возвращает все записи из левой таблицы (table1) и соответствующие записи из правой таблицы (table2). Результат равен NULL с правой стороны, если совпадений нет.

> **Примечание**. В некоторых базах данных LEFT JOIN называется LEFT OUTER JOIN.
> 

![LEFT JOIN](/images/img_leftjoin.gif)

## LEFT JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

## Примеры

Выбрать всех клиентов из таблицы Customers и любые заказы из таблицы Orders, которые они могут иметь :
``` SQL
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT  JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER  BY Customers.CustomerName;
```

> LEFT JOIN возвращает все записи из левой таблицы (Клиенты), даже если в правой таблице нет совпадений (Заказы).
