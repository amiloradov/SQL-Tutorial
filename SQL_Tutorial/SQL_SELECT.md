# Оператор SQL SELECT - выбор

Оператор SELECT используется для выбора данных из базы данных.

## SELECT Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name;
SELECT * FROM  table_name;
```

## Примеры

Выбрать столбцы «CustomerName» и «City» из таблицы «Customers»:
``` SQL
SELECT CustomerName, City FROM Customers;
```

Выбрать все столбцы из таблицы  «Customers»:
``` SQL
SELECT * FROM Customers;
```

---

[НАЗАД](/SQL_Tutorial/SQL_Comments.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_SELECT_DISTINCT.md)

