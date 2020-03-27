# Оператор SQL ALTER TABLE

ALTER TABLE используется для добавления, удаления или изменения столбцов в существующей таблице.

ALTER TABLE также используется для добавления и удаления различных ограничений в существующей таблицы.

## ALTER TABLE - ADD Column

Чтобы добавить столбец в таблицу, используйте следующий синтаксис:

``` SQL
ALTER TABLE table_name 
ADD column_name datatype;
```

## Пример

Добавить столбец «Email» в таблицу «Customers»:

``` SQL
ALTER TABLE Customers  
ADD Email varchar(255);
```
---

## ALTER TABLE - DROP COLUMN

Чтобы удалить столбец в таблице, используйте следующий синтаксис (обратите внимание, что некоторые системы баз данных не позволяют удалять столбец):

``` SQL
ALTER TABLE table_name 
DROP COLUMN column_name;
```

## Пример

Удалить столбец «Email» из таблицы «Customers»:

``` SQL
ALTER TABLE Customers  
DROP COLUMN Email;
```
---

## ALTER TABLE - ALTER/MODIFY COLUMN

Чтобы изменить тип данных столбца в таблице, используйте следующий синтаксис:

**SQL Server / MS Access:**

``` SQL
ALTER TABLE table_name 
ALTER COLUMN column_name datatype;
```

**МySQL / Oracle (версия перед 10G):**

``` SQL
ALTER TABLE table_name 
MODIFY COLUMN column_name datatype;
```

**Oracle 10G и более поздние версии:**

``` SQL
ALTER TABLE table_name
MODIFY column_name datatype;
```

## Общие примеры

Добавить столбец с именем «DateOfBirth» в таблице «Persons».

### Таблица "Persons"
| ID | LastName | FirstName | Address | City |
|--|--|--|--|--|
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |

``` SQL
ALTER TABLE Persons  
ADD DateOfBirth date;
```

Таблица «Persons» теперь будет выглядеть так:

| ID | LastName | FirstName | Address | City | DateOfBirth |
|--|--|--|--|--|--|
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |
---

Изменить тип данных столбца с именем «DateOfBirth» в таблице «Persons».

``` SQL
ALTER TABLE Persons  
ALTER COLUMN DateOfBirth year;
```

> Cтолбец «DateOfBirth» теперь имеет тип year и будет содержать год в двух- или четырехзначном формате.
---

Удалить столбец с именем «DateOfBirth» в таблице «Persons».

``` SQL
ALTER TABLE Persons  
DROP COLUMN DateOfBirth;
```

Таблица «Персоны» теперь будет выглядеть так:

| ID | LastName | FirstName | Address | City |
|--|--|--|--|--|
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |

---

[НАЗАД](/SQL_DATABASE/SQL_DROP_TABLE.md)  | [ВПЕРЁД](#)

