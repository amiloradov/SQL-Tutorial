# Функции SQL MIN () и MAX ()


Функция MIN () возвращает наименьшее значение из выбранного столбца.

Функция MAX () возвращает наибольшее значение выбранного столбца.

## Синтаксис MIN ()

``` SQL
SELECT MIN(column_name) FROM table_name WHERE  condition;
```


## Синтаксис MAX ()

``` SQL
SELECT MAX(column_name) FROM table_name WHERE  condition;
```

## Примеры

Найти цену самого дешевого продукта из столбца "Price" в таблице "Products":
``` SQL
SELECT MIN(Price) AS SmallestPrice FROM Products;
```


Найти цену самого дорогого продукта из столбца "Price" в таблице "Products":
``` SQL
SELECT MAX(Price) AS LargestPrice FROM Products;
```

---

[НАЗАД](/SQL_Tutorial/SQL_TOP_LIMIT_ROWNUM.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_COUNT_AVG_SUM.md)

