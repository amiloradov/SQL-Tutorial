# Функции SQL COUNT(), AVG() и SUM()

* Функция COUNT () возвращает количество строк, соответствующих заданным критериям.
* Функция AVG () возвращает среднее значение числового столбца.
* Функция SUM () возвращает общую сумму числового столбца.

## Синтаксис COUNT()

``` SQL
SELECT COUNT(column_name) FROM table_name WHERE  condition;
```

## Синтаксис AVG()

``` SQL
SELECT AVG(column_name) FROM table_name WHERE  condition;
```

## Синтаксис SUM()

``` SQL
SELECT SUM(column_name) FROM table_name WHERE  condition;
```

## Примеры
### COUNT
Найти количество всех продуктов в таблице "Products":
``` SQL
SELECT  COUNT(ProductID) FROM Products;
```
> **Примечание:** значения NULL не учитываются.
---

### AVG
Найти среднюю цену всех продуктов в таблице "Products":
``` SQL
SELECT  AVG(ProductID) FROM Products;
```
> **Примечание:** значения NULL не учитываются.
---

### SUM
Найти сумму цен (столбец "Price") всех продуктов в таблице "Products":
``` SQL
SELECT  SUM(Price) FROM Products;
```
