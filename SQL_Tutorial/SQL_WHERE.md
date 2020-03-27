# Условие SQL WHERE

WHERE используется для извлечения только тех записей, которые удовлетворяют указанному условию.

##  WHERE Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name WHERE  condition;
```

## Примеры

Выбрать всех клиентов из страны «Belarus» в таблице «Customers»:
``` SQL
SELECT * FROM Customers WHERE Country='Belarus';
```

Числовые поля не должны заключаться в кавычки:
``` SQL
SELECT * FROM Customers WHERE CustomerID=1;
```

---

[НАЗАД](/SQL_Tutorial/SQL_SELECT_DISTINCT.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_AND_OR_NOT.md)

