# SQL Ограничение FOREIGN KEY

FOREIGN KEY - это ключ, используемый для связи двух таблиц.

FOREIGN KEY - это поле (или набор полей) в одной таблице, которое ссылается на PRIMARY KEY в другой таблице.

Таблица, содержащая внешний ключ (FOREIGN KEY), называется дочерней таблицей, а таблица, содержащая ключ-кандидат, называется ссылочной или родительской таблицей.

Посмотрите на следующие две таблицы:

### Таблица "Persons"
| PersonID | LastName | FirstName | Age |
|--|--|--|--|
| 1 | Hansen | Ola | 30 |
| 2 | Svendson | Tove | 23 |
| 3 | Pettersen | Kari | 20 |

### Таблица "Orders"

| OrderID | OrderNumber | PersonID |
|--|--|--|
| 1 | 77895 | 3 |
| 2 | 44678 | 3 |
| 3 | 22456 | 2 |
| 4 | 24562 | 1 |

Обратите внимание, что столбец «PersonID» в таблице «Orders» указывает на столбец «PersonID» в таблице «Persons».

Столбец PersonID в таблице Persons является PRIMARY KEY в таблице Persons. Столбец PersonID в таблице «Orders» является FOREIGN KEY в таблице «Orders».

Ограничение FOREIGN KEY используется для предотвращения действий, которые разрушают связи между таблицами.

Ограничение FOREIGN KEY также предотвращает вставку недопустимых данных в столбец внешнего ключа, поскольку оно должно быть одним из значений, содержащихся в таблице, на которую оно указывает.

## SQL FOREIGN KEY в CREATE TABLE

Следующий SQL создает FOREIGN KEY в столбце «PersonID» при создании таблицы «Orders»:

**MySQL:**

``` SQL
CREATE TABLE Orders (
OrderID int NOT NULL,
OrderNumber int NOT NULL,
PersonID int,
PRIMARY KEY (OrderID),
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

**SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Orders (
OrderID int NOT NULL PRIMARY KEY,
OrderNumber int NOT NULL,
PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```

Чтобы обойти ограничения FOREIGN KEY и определить FOREIGN KEY для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
CREATE TABLE Orders (
OrderID int NOT NULL,
OrderNumber int NOT NULL,
PersonID int,
PRIMARY KEY (OrderID),
CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
REFERENCES Persons(PersonID)
);
```

## SQL FOREIGN KEY в ALTER TABLE

Чтобы создать ограничение FOREIGN KEY для столбца «PersonID», когда таблица «Orders» уже создана, используйте следующий SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

Чтобы обойти ограничения FOREIGN KEY и определить FOREIGN KEY для нескольких столбцов, используйте следующий синтаксис SQL:

**MySQL / SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

## Удаление ограничения FOREIGN KEY

Чтобы удалить ограничение FOREIGN KEY, используйте следующий SQL:

**MySQL:**

``` SQL
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

**SQL Server / Oracle / MS Access:**

``` SQL
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```
---

[НАЗАД](/SQL_DATABASE/SQL_PRIMARY_KEY.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_CHECK.md)

