# Оператор SQL DELETE

Оператор DELETE используется для удаления существующих записей в таблице.

## DELETE Синтаксис

``` SQL
DELETE FROM table_name WHERE condition;
```
>WHERE указывает, какие записи должны быть удалены. Если вы пропустите WHERE, все записи в таблице будут удалены!

## Примеры

Удалить клиента "Grisha" из таблицы "Customers":
``` SQL
DELETE FROM Customers WHERE CustomerName='Grisha';
```

Удалить все строки в таблице "Customers", не удаляя таблицу.
``` SQL
DELETE FROM Customers;
```

---

[НАЗАД](/SQL_Tutorial/SQL_UPDATE.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_TOP_LIMIT_ROWNUM.md)

