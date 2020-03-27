# SQL  RIGHT JOIN

RIGHT JOIN возвращает все записи из правой таблицы (table2) и соответствующие записи из левой таблицы (table1). Результат равен NULL с левой стороны, когда нет совпадений.

> **Примечание**. В некоторых базах данных RIGHT JOIN называется RIGHT OUTER JOIN.
> 

![RIGHT JOIN](/Images/img_rightjoin.gif)

## RIGHT JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

### Таблица "Orders"

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
|--|--|--|--|--|
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |
---

### Таблица "Employees"
| EmployeeID | LastName | FirstName | BirthDate | Photo |
|--|--|--|--|--|
| 1 | Davolio | Nancy | 12/8/1968 | EmpID1.pic |
| 2 | Fuller | Andrew | 2/19/1952 | EmpID2.pic |
| 3 | Leverling | Janet | 8/30/1963 | EmpID3.pic |

## Примеры

Выбрать всех сотудников из таблицы Employees и любые заказы из таблицы Orders, которые они могут разместить :
``` SQL
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT  JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER  BY Orders.OrderID;
```

> Примечание. RIGHT JOIN возвращает все записи из правой таблицы (Сотрудники), даже если в левой таблице (Заказы) нет совпадений.

---

[НАЗАД](/SQL_Tutorial/SQL_LEFT_JOIN.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_FULL_JOIN.md)

