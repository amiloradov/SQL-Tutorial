# Оператор SQL SELECT DISTINCT - выбор

Оператор SELECT DISTINCT используется для возврата только различных значений.

## SELECT DISTINCT Синтаксис
``` SQL
SELECT DISTINCT  column1, column2, ... FROM  table_name;
```

## Примеры

Выбрать столбец «Country» из таблицы «Customers»:
``` SQL
SELECT DISTINCT Country FROM Customers;
```

Перечислить **количество** разных стран в таблице «Customers» (данный пример не поддерживается Firefox и Microsoft Edge):
``` SQL
SELECT COUNT(DISTINCT Country) * FROM Customers;
```
>Обходной путь для Firefox и Microsoft Edge:
>``` SQL
>SELECT  Count(*) AS DistinctCountries FROM (SELECT  DISTINCT Country FROM Customers);
>```

---

[НАЗАД](/SQL_Tutorial/SQL_SELECT.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_WHERE.md)

