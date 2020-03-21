# SQL Ограничение UNIQUE


Ограничение UNIQUE гарантирует, что все значения в столбце различны.

Ограничения UNIQUE и PRIMARY KEY обеспечивают гарантию уникальности для столбца или набора столбцов.

Ограничение PRIMARY KEY автоматически имеет ограничение UNIQUE, однако вы можете иметь много ограничений UNIQUE на таблицу, но только одно ограничение PRIMARY KEY на таблицу.

## SQL UNIQUE в CREATE TABLE

Следующий SQL создает UNIQUE-ограничение для столбца «ID» при создании таблицы «Persons»:

``` SQL
CREATE TABLE Persons (
ID int NOT NULL UNIQUE,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int
);
```

Чтобы назвать ограничение UNIQUE для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**


``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

## SQL UNIQUE в ALTER TABLE

Чтобы создать ограничение UNIQUE для столбца «ID», когда таблица уже создана, используйте следующий SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons  
ADD UNIQUE (ID);
```

Чтобы создать ограничение UNIQUE для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE (ID,LastName);
```

## Удаление ограничения UNIQUE

Чтобы удалить ограничение UNIQUE, используйте следующий SQL:

**MySQL:**

``` SQL
ALTER TABLE Persons
DROP INDEX UC_Person;
```

**SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```
---

[НАЗАД](/SQL_DATABASE/SQL_NOT_NULL.md)  | [ВПЕРЁД](#)

