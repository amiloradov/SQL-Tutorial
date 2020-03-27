# Вставка SQL  INSERT INTO

INSERT INTO используется для вставки новых записей в таблицу.

## INSERT INTO Синтаксис
Написать оператор INSERT INTO можно двумя способами.
Первый способ определяет имена столбцов и значения для вставки:
``` SQL
INSERT  INTO  table_name (column1, column2, column3, ...) VALUES (value1, value2, value3, ...);
```
Если вы добавляете значения для всех столбцов таблицы, вам не нужно указывать имена столбцов в запросе SQL. Однако убедитесь, что порядок значений соответствует порядку столбцов в таблице.
``` SQL
INSERT  INTO  table_name VALUES (value1, value2, value3, ...);
```

## Примеры

Вставить новую запись в таблицу «Customers»:
``` SQL
INSERT  INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Misha', 'MishaMisha', 'Pushkina 21', 'Minsk', '220645', 'Belarus');
```

---

[НАЗАД](/SQL_Tutorial/SQL_ORDER_BY.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_NULL.md)

