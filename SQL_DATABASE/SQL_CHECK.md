# SQL Ограничение CHECK

Ограничение CHECK используется для ограничения диапазона значений, который можно поместить в столбец.

Если вы определяете ограничение CHECK для одного столбца, оно допускает только определенные значения для этого столбца.

Если вы определяете ограничение CHECK для таблицы, оно может ограничивать значения в определенных столбцах на основании значений в других столбцах.

## SQL CHECK в CREATE TABLE

Следующий SQL создает ограничение CHECK для столбца «Age» при создании таблицы «Persons». Ограничение CHECK гарантирует, что возраст человека должен быть 18 лет или старше:

**MySQL:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
CHECK (Age>=18)
);
```

**SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int CHECK (Age>=18)
);
```

Чтобы определить FOREIGN KEY для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
City varchar(255),
CONSTRAINT CHK_Person CHECK (Age>=18  AND City='Sandnes')
);
```

## SQL CHECK в ALTER TABLE

Чтобы создать ограничение CHECK для столбца «Age», когда таблица «Persons» уже создана, используйте следующий SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

Чтобы определить CHECK для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

## Удаление ограничения CHECK

Чтобы удалить ограничение CHECK, используйте следующий SQL:

**SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```

**MySQL:**

``` SQL
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```
---

[НАЗАД](/SQL_DATABASE/SQL_FOREIGN_KEY.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_DEFAULT.md)

