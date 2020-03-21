# Оператор SQL LIKE

LIKE используется вместе с WHERE для поиска указанного шаблона в столбце.

В сочетании с оператором LIKE часто используются два подстановочных знака:
-   % - знак процента представляет ноль, один или несколько символов
-   _ - Подчеркивание представляет один символ

> **Примечание:** MS Access использует звездочку (*) вместо знака процента (%) и знак вопроса (?) Вместо подчеркивания (_).

> **Примечание:** Вы также можете комбинировать любое количество условий, используя операторы И или ИЛИ.


## Синтаксис LIKE

``` SQL
SELECT column1, column2, ... FROM table_name WHERE  columnN LIKE pattern;
```
---
| Оператор LIKE| Описание |
|--|--|
| WHERE column LIKE 'a%' | Находит значения начинающиеся на "a" |
| WHERE column LIKE '%a' | Находит значения окончивающиеся на "a" |
| WHERE column LIKE '%or%' | Находит значения, которые имеют "or" в любой позиции |
| WHERE column LIKE '_or%' | Находит значения, которые имеют "r" во второй позиции |
| WHERE column LIKE 'a__%' | Находит значения, которые начинаются с "a" и имеют длину не менее 3 символов |
| WHERE column LIKE 'a%o' | Находит значения, которые начинаются на "a" и заканчиваются на "o" |
---


## Примеры

Выбрать все имена клиентов  CustomerName в таблице "Customers", начинающимся с «a»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE 'a%';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", оканчивающимся на «a»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '%a';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", которые имеют «or» в любой позиции:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '%or%';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", которые имеют «r» во второй позиции:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '_r%';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", которые начинаются с «a» и имеют длину не менее 3 символов:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE 'a__%';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", которые начинаются с «a» и заканчиваются на «o»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE 'a%o';
```
---

Выбрать все имена клиентов  CustomerName в таблице "Customers", которые НЕ начинаются с «a»:
``` SQL
SELECT * FROM Customers WHERE CustomerName NOT LIKE 'a%';
```
