# SQL VIEWS


SQL VIEW - это виртуальная таблица, основанная на наборе результатов оператора SQL.

VIEW содержит строки и столбцы, как настоящая таблица. Поля в VIEW - это поля из одной или нескольких реальных таблиц в базе данных.

Вы можете добавить функции SQL, операторы WHERE и JOIN в VIEW и представить данные, как если бы данные приходили из одной таблицы.

## Синтаксис SQL VIEW

В VIEW всегда отображаются актуальные данные! Механизм базы данных воссоздает данные, используя оператор SQL VIEW, каждый раз, когда пользователь запрашивает представление.

``` SQL
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

## Примеры

Следующий SQL создает представление, которое показывает всех клиентов из Бразилии:

``` SQL
CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = "Brazil";
```

Мы можем запросить представление выше следующим образом:

``` SQL
SELECT * FROM [Brazil Customers];
```
---

Следующий SQL создает представление, которое выбирает каждый продукт в таблице «Products» по цене, превышающей среднюю цену:

``` SQL
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

Мы можем запросить представление выше следующим образом:

``` SQL
SELECT * FROM [Products Above Average Price];
```

## Обновление VIEW

VIEW может быть обновлен командой CREATE OR REPLACE VIEW.

``` SQL
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Следующий SQL добавляет столбец «City» в представление «Brazil Customers»:

``` SQL
CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName, City
FROM Customers  
WHERE Country = "Brazil";
```

##  Удаление VIEW

VIEW удаляется командой DROP VIEW.

``` SQL
DROP VIEW view_name;
```

Следующий SQL удаляет представление «Brazil Customers»:

``` SQL
DROP VIEW [Brazil Customers];
```
---

[НАЗАД](/SQL_DATABASE/SQL_DATE.md)  | [ВПЕРЁД](#)

