# SQL Ограничение PRIMARY KEY

Ограничение PRIMARY KEY автоматически имеет ограничение [UNIQUE](/SQL_DATABASE/SQL_UNIQUE.md), однако вы можете иметь много ограничений UNIQUE на таблицу, но только одно ограничение PRIMARY KEY на таблицу.

## SQL PRIMARY KEY в CREATE TABLE

Следующий SQL создает PRIMARY KEY в столбце «ID» при создании таблицы «Persons»:

**MySQL:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
PRIMARY KEY (ID)
);
```

**SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL PRIMARY KEY,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int
);
```

Чтобы обойти ограничения PRIMARY KEY и определить PRIMARY KEY для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Persons (
ID int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

> В приведенном выше примере используется только ОДИН PRIMARY KEY (PK_Person). Однако ЗНАЧЕНИЕ PRIMARY KEY состоит из ДВУХ КОЛОНН (ID + LastName).

## SQL PRIMARY KEY в ALTER TABLE

Чтобы создать ограничение PRIMARY KEY для столбца «ID», когда таблица уже создана, используйте следующий SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

Чтобы обойти ограничения PRIMARY KEY и определить PRIMARY KEY для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

> Если вы используете инструкцию ALTER TABLE для добавления PRIMARY KEY, то столбцы  в которые добавляется PRIMARY KEY должны быть уже объявлены и не содержать значений NULL.

## Удаление ограничения PRIMARY KEY

Чтобы удалить ограничение PRIMARY KEY, используйте следующий SQL:

**MySQL:**

``` SQL
ALTER TABLE Persons
DROP PRIMARY KEY;
```

**SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```
---

[НАЗАД](/SQL_DATABASE/SQL_UNIQUE.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_FOREIGN_KEY.md)

