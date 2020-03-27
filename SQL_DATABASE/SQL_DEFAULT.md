# SQL Ограничение DEFAULT


Ограничение DEFAULT используется для предоставления значения по умолчанию для столбца.

Значение по умолчанию будет добавлено ко всем новым записям, если не указано другое значение.

## SQL DEFAULT в CREATE TABLE

Следующий SQL устанавливает значение DEFAULT для столбца «City» при создании таблицы «Persons»:

**MySQL/SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
City varchar(255) DEFAULT 'Sandnes'
);
```
Ограничение DEFAULT также можно использовать для вставки системных значений с помощью таких функций, как GETDATE () - берет дату и время системы:

``` SQL
CREATE TABLE Orders (
ID int NOT NULL,
OrderNumber int NOT NULL,
OrderDate date DEFAULT GETDATE()
);
```

## SQL DEFAULT в ALTER TABLE

Чтобы создать ограничение DEFAULT для столбца «City», когда таблица «Persons» уже создана, используйте следующий SQL:

**MySQL: **

``` SQL
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```

**SQL Server:**

``` SQL
ALTER TABLE Persons
ADD CONSTRAINT df_City
DEFAULT 'Sandnes' FOR City;
```

**MS Access:**

``` SQL
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'Sandnes';
```

**Oracle:**

``` SQL
ALTER TABLE Persons
MODIFY City DEFAULT 'Sandnes';
```

## Удаление ограничения DEFAULT

Чтобы удалить ограничение DEFAULT, используйте следующий SQL:

**SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```

**MySQL:**

``` SQL
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```
---

[НАЗАД](/SQL_DATABASE/SQL_CHECK.md)  | [ВПЕРЁД](#)

