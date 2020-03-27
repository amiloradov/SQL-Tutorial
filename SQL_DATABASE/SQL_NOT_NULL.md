# SQL Ограничение NOT NULL

По умолчанию столбец может содержать значения NULL. Ограничение NOT NULL заставляет столбец НЕ принимать значения NULL.

Это обязывает поле всегда содержать значение, что означает, что вы не можете вставить новую запись или обновить запись без добавления значения в это поле.

## SQL NOT NULL в CREATE TABLE

Следующий SQL-код гарантирует, что столбцы «ID», «LastName» и «FirstName» НЕ примут значения NULL при создании таблицы «Persons»:

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255) NOT NULL,
Age int
);
```

## SQL NOT NULL в ALTER TABLE

Чтобы создать ограничение NOT NULL для столбца «Age», когда таблица «Persons» уже создана, используйте следующий SQL:

``` SQL
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

---

[НАЗАД](/SQL_DATABASE/SQL_Constraints.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_UNIQUE.md)

