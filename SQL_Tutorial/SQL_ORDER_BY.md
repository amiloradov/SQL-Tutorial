# Сортировка SQL  ORDER BY

ORDER BY сортирует записи по возрастанию по умолчанию. Чтобы отсортировать записи в порядке убывания, используйте ключевое слово DESC.

## ORDER BY Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name ORDER BY column1, column2, ... ASC|DESC;
```

## Примеры

Выбрать всех клиентов из таблицы «Customers», отсортированных по столбцу «Country»:
``` SQL
SELECT * FROM Customers ORDER  BY Country;
```

Выбрать всех клиентов из таблицы «Customers», отсортированных по убыванию по столбцу «Country»:
``` SQL
SELECT * FROM Customers ORDER  BY Country DESC;
```

Выбрать всех клиентов из таблицы «Customers», отсортированных по столбцам «Country» и «CustomerName»:
``` SQL
SELECT * FROM Customers ORDER  BY Country, CustomerName;
```

Выбрать всех клиентов из таблицы «Customers», отсортированных по возрастанию по столбцу «Country» и по убыванию по столбцу «CustomerName»:
``` SQL
SELECT * FROM Customers ORDER  BY Country ASC, CustomerName DESC;
```

---

[НАЗАД](/SQL_Tutorial/SQL_AND_OR_NOT.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_INSERT_INTO.md)

