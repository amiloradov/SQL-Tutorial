# Оператор SQL CREATE TABLE

Оператор CREATE TABLE используется для создания новой таблицы в базе данных.

## Синтаксис CREATE TABLE

``` SQL
CREATE TABLE table_name (
column1 datatype,
column2 datatype,
column3 datatype,
...
);
```

## Пример

Создать таблицу с именем «Persons», которая содержит пять столбцов: PersonID, LastName, FirstName, Address и City:

``` SQL
CREATE TABLE Persons (
PersonID int,
LastName varchar(255),
FirstName varchar(255),
Address varchar(255),
City varchar(255)
);
```

> [Параметр типа данных](https://www.w3schools.com/sql/sql_datatypes.asp) указывает тип данных, которые может содержать столбец (например, varchar, integer, date и т. Д.).
> Теперь пустая таблица «Persons» может быть заполнена данными с помощью оператора SQL [INSERT INTO](/SQL_Tutorial/SQL_INSERT_INTO.md) .

## Создание таблицы, используя другую таблицу.

Копия существующей таблицы также может быть создана с помощью CREATE TABLE.

Новая таблица получает те же определения столбцов. Могут быть выбраны все столбцы или конкретные столбцы .

Если вы создаете новую таблицу с использованием существующей таблицы, новая таблица будет заполнена существующими значениями из старой таблицы.

## Синтаксис

``` SQL
CREATE TABLE new_table_name AS
SELECT column1, column2,... 
FROM existing_table_name
WHERE ...;
```

## Пример

Создать новую таблицу с именем «TestTables» (которая является копией таблицы «Customers»):

``` SQL
CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;
```

---

[НАЗАД](/SQL_DATABASE/SQL_BACKUP_DATABASE.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_DROP_TABLE.md)

