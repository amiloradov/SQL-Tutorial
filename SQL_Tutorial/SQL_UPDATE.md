# Оператор SQL UPDATE

Оператор UPDATE используется для изменения существующих записей в таблице.

## UPDATE Синтаксис

``` SQL
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
```
>WHERE указывает, какие записи должны быть обновлены. Если вы пропустите WHERE, все записи в таблице будут обновлены!

## Примеры

Обновить первого клиента (CustomerID = 1) в таблице "Customers", c новым "CustomerName" и новым "Address".
``` SQL
UPDATE Customers SET ContactName = 'Pasha', City= 'Gomel' WHERE CustomerID = 1;
```

Изменить имя контакта на «Ololo» для всех записей, где страна - «Ukraine»:
``` SQL
UPDATE Customers SET ContactName='Ololo' WHERE Country='Ukraine';
```

---

[НАЗАД](/SQL_Tutorial/SQL_NULL.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_DELETE.md)

