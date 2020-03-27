# SQL CREATE INDEX

CREATE INDEX используется для создания индексов в таблицах.

Индексы используются для получения данных из базы данных быстрее. Пользователи не могут видеть индексы, они просто используются для ускорения поиска/запросов.

> Обновление таблицы с индексами занимает больше времени, чем обновление таблицы без них (потому что индексы также нуждаются в обновлении). Поэтому создавайте индексы только для столбцов, по которым будет производиться частый поиск.

## Синтаксис CREATE INDEX

Создает индекс для таблицы. Допускаются повторяющиеся значения:

``` SQL
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

## Синтаксис CREATE UNIQUE INDEX

Создает уникальный индекс для таблицы. Дублирующиеся значения не допускаются:

``` SQL
CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);
```

> Синтаксис для создания индексов различается в разных базах данных. Поэтому: проверьте синтаксис для создания индексов в вашей базе данных.

## Пример создания

Приведенный ниже оператор SQL создает индекс с именем «idx_lastname» для столбца «LastName» в таблице «Persons»:

``` SQL
CREATE INDEX idx_lastname
ON Persons (LastName);
```

Если вы хотите создать индекс для нескольких столбцов, вы можете перечислить имена столбцов в скобках, разделенных запятыми:

``` SQL
CREATE INDEX idx_pname
ON Persons (LastName, FirstName);
```

## Удаление DROP INDEX

Оператор DROP INDEX используется для удаления индекса в таблице.

**MS Access:**

``` SQL
DROP INDEX index_name ON table_name;
```

**SQL Server:**

``` SQL
DROP INDEX table_name.index_name;
```

**DB2 / Oracle:**

``` SQL
DROP INDEX index_name;
```

**MySQL:**

``` SQL
ALTER TABLE table_name
DROP INDEX index_name;
```
---

[НАЗАД](/SQL_DATABASE/SQL_DEFAULT.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_AUTO_INCREMENT.md)

