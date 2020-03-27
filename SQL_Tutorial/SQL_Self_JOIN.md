# SQL  Self JOIN

Self JOIN - это обычное соединение, но таблица соединяется сама с собой.

## Self JOIN Синтаксис

``` SQL
SELECT column_name(s) 
FROM table1 T1, table1 T2
WHERE condition;
```
_T1_ и _T2_ - разные псевдонимы для одной и той же таблицы.

## Примеры

Выбрать всех клиентов из таблицы Customers из одно и того же города:
``` SQL
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER  BY A.City;
```

---

[НАЗАД](/SQL_Tutorial/SQL_FULL_JOIN.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_UNION.md)

