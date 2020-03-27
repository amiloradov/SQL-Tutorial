
# SQL INSERT INTO SELECT

INSERT INTO SELECT копирует данные из одной таблицы и вставляет их в другую таблицу.

-   INSERT INTO SELECT требует, чтобы типы данных в исходной и целевой таблицах совпадали
-   Существующие записи в целевой таблице не затрагиваются

## INSERT INTO SELECT Синтаксис

Скопировать все столбцы из одной таблицы в другую таблицу:
``` SQL
INSERT INTO table2 (column1, column2, column3, ...)
SELECT column1, column2, column3, ...
FROM table1
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

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |
---

### Таблица "Suppliers"

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd | Ann Arbor | 48104 | USA |
| 4 | Tokyo Traders | Yoshi Nagas | 9-8 Sekimai Musashino-shi | Tokyo | 100 | Japan |

## Примеры

Копировать «Suppliers» в «Customers» (столбцы, которые не заполнены данными, будут содержать NULL):
``` SQL
INSERT INTO Customers (CustomerName, City, Country)  
SELECT SupplierName, City, Country FROM Suppliers;
```
---

Копировать «Suppliers» в «Customers» (заполнить все столбцы):
``` SQL
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)  
SELECT SupplierName, ContactName, Address, City, PostalCode, Country FROM Suppliers;
```
---

Копировать только «немецких поставщиков» в «Customers»:
``` SQL
INSERT INTO Customers (CustomerName,  City, Country)  
SELECT SupplierName, City, Country FROM Suppliers  
WHERE Country='Germany';
```
