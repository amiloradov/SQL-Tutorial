# SQL DATES

> Самое сложное при работе с датами - это убедиться, что формат даты, которую вы пытаетесь вставить, соответствует формату столбца даты в базе данных.

Пока ваши данные содержат только даты, ваши запросы будут работать как положено. Однако, если задействовано время, они усложняются.

## Типы данных SQL Date

**MySQL** поставляется со следующими типами данных для хранения даты или значения даты / времени в базе данных:

-   DATE - format YYYY-MM-DD
-   DATETIME - format: YYYY-MM-DD HH:MI:SS
-   TIMESTAMP - format: YYYY-MM-DD HH:MI:SS
-   YEAR - format YYYY or YY

**SQL Server** поставляется со следующими типами данных для хранения даты или значения даты / времени в базе данных:

-   DATE - format YYYY-MM-DD
-   DATETIME - format: YYYY-MM-DD HH:MI:SS
-   SMALLDATETIME - format: YYYY-MM-DD HH:MI:SS
-   TIMESTAMP - format: a unique number

> Типы даты выбираются для столбца при создании новой таблицы в вашей базе данных!
> Вы можете легко сравнить две даты, если не участвует временная составляющая!

## SQL Работа с датами

Предположим, у нас есть следующая таблица «Orders»:

### Таблица "Orders"

| OrderID | ProductName | OrderDate |
|--|--|--|
| 1 | Geitost | 2008-11-11 |
| 2 | Camembert Pierrot | 2008-11-09 |
| 3 | Mozzarella di Giovanni | 2008-11-11 |
| 4 | Mascarpone Fabioli | 2008-10-29 |

Теперь мы хотим выбрать записи с OrderDate «2008-11-11» из таблицы выше.

Мы используем инструкцию SELECT:

``` SQL
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```

Набор результатов будет выглядеть так:

| OrderID | ProductName | OrderDate |
|--|--|--|
| 1 | Geitost | 2008-11-11 |
| 3 | Mozzarella di Giovanni | 2008-11-11 |

Теперь предположим, что таблица «Orders» выглядит следующим образом (обратите внимание на компонент времени в столбце «OrderDate»):

| OrderID | ProductName | OrderDate |
|--|--|--|
| 1 | Geitost | 2008-11-11 13:23:44 |
| 2 | Camembert Pierrot | 2008-11-09 15:45:21 |
| 3 | Mozzarella di Giovanni | 2008-11-11 11:12:01 |
| 4 | Mascarpone Fabioli | 2008-10-29 14:56:59 |

Если мы используем тот же оператор SELECT, что и выше:

``` SQL
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```

мы не получим никакого результата! Это потому, что запрос ищет только даты без временной части.

>  Чтобы ваши запросы были простыми и легкими в обслуживании, не допускайте временных составляющих в ваших датах!
---

[НАЗАД](/SQL_DATABASE/SQL_AUTO_INCREMENT.md)  | [ВПЕРЁД](#)

