
# Оператор SQL  SELECT INTO

SELECT INTO копирует данные из одной таблицы в новую таблицу.

> Новая таблица будет создана с именами и типами столбцов, как определено в старой таблице. Вы можете создавать новые имена столбцов, используя предложение AS.

## SELECT INTO Синтаксис

Скопировать все столбцы в новую таблицу:
``` SQL
SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```
---

Скопировать только несколько столбцов в новую таблицу:
``` SQL
SELECT column1, column2, column3, ...
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```

## Примеры

Создать резервную копию клиентов из таблицы «Customers»:
``` SQL
SELECT * INTO CustomersBackup2017
FROM Customers;
```
---

IN используется для копирования таблицы в новую таблицу в другой базе данных:
``` SQL
SELECT * INTO CustomersBackup2017 IN 'Backup.mdb'
FROM Customers;
```
---

Копировать только несколько столбцов в новую таблицу:
``` SQL
SELECT CustomerName, ContactName INTO CustomersBackup2017
FROM Customers;
```
---

Копировать только новых клиентов из Германии в новую таблицу:
``` SQL
SELECT * INTO CustomersGermany
FROM Customers
WHERE Country = 'Germany';
```
---

Копировать данные из нескольких таблиц в новую таблицу:
``` SQL
SELECT Customers.CustomerName, Orders.OrderID
INTO CustomersOrderBackup2017
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```

---

[НАЗАД](/SQL_Tutorial/SQL_EXISTS.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_INSERT_INTO_SELECT.md)

