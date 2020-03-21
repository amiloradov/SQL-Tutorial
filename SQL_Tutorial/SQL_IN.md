# Оператор SQL IN

Оператор IN позволяет указать несколько значений в предложении WHERE.
Оператор IN является сокращением для нескольких условий ИЛИ.

## IN Синтаксис

``` SQL
SELECT  column_name(s) FROM table_name WHERE  column_name IN (value1, value2, ...);
```
### ИЛИ

``` SQL
SELECT  column_name(s) FROM table_name WHERE  column_name IN (SELECT STATEMENT);
```

## Примеры

Выбрать всех клиентов, которые находяться в Беларуси, России или Украине из таблицы "Customers":
``` SQL
SELECT * FROM Customers WHERE Country IN ('Belarus', 'Russia', 'Ukraine');
```
---

Выбрать всех клиентов, которые **НЕ** находяться в Беларуси, России или Украине из таблицы "Customers":
``` SQL
SELECT * FROM Customers WHERE Country NOT IN ('Belarus', 'Russia', 'Ukraine');
```
---

Выбрать всех клиентов  из тех же стран, что и поставщики из таблицы Suppliers:
``` SQL
SELECT * FROM Customers WHERE Country IN (SELECT Country FROM Suppliers);
```
