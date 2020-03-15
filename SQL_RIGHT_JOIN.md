# SQL  RIGHT JOIN

RIGHT JOIN возвращает все записи из правой таблицы (table2) и соответствующие записи из левой таблицы (table1). Результат равен NULL с левой стороны, когда нет совпадений.

> **Примечание**. В некоторых базах данных RIGHT JOIN называется RIGHT OUTER JOIN.
> 

![RIGHT JOIN](/images/img_rightjoin.gif)

## RIGHT JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

## Примеры

Выбрать всех сотудников из таблицы Employees и любые заказы из таблицы Orders, которые они могут разместить :
``` SQL
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT  JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER  BY Orders.OrderID;
```

> Примечание. RIGHT JOIN возвращает все записи из правой таблицы (Сотрудники), даже если в левой таблице (Заказы) нет совпадений.
