# Операторы SQL ANY и ALL

ANY и ALL используются с WHERE или HAVING.

ANY  возвращает true, если какое-либо из значений подзапроса удовлетворяет условию.

ALL возвращает true, если все значения подзапроса удовлетворяют условию.

## ANY Синтаксис

``` SQL
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
(SELECT column_name FROM table_name WHERE condition);
```

## ALL Синтаксис

``` SQL
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL
(SELECT column_name FROM table_name WHERE condition);
```

### Таблица "Products"

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
|--|--|--|--|--|--|
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 2 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 2 | 2 | 36 boxes | 21.35 |
---

### Таблица "OrderDetails"

| OrderDetailID | OrderID | ProductID | Quantity |
|--|--|--|--|
| 1 | 10248 | 11 | 12 | 
| 2 | 10248 | 42 | 10 |
| 3 | 10248 | 72 | 5 | 
| 4 | 10249 | 14 | 5 | 
| 5 | 10249 | 51 | 40 | 

## Примеры ANY

Возвращает TRUE и перечисляет названия продуктов из таблицы "Products", если он находит ЛЮБЫЕ записи в таблице OrderDetails с количеством 
"Quantity" = 10:
``` SQL
SELECT ProductName  
FROM Products  
WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
```
---

Возвращает TRUE и перечисляет названия продуктов из таблицы "Products", если он находит ЛЮБЫЕ записи в таблице OrderDetails с количеством 
"Quantity" > 99:
``` SQL
SELECT ProductName  
FROM Products  
WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity > 99);
```

## Примеры ALL

Возвращает TRUE и перечисляет названия продуктов из таблицы "Products", если ВСЕ записи в таблице OrderDetails имеют количество Quantity = 10 (поэтому в этом примере будет возвращаться ЛОЖЬ, поскольку не ВСЕ записи в таблице OrderDetails имеют количество Quantity = 10, т.е. в нашем случае ничего не возвратиться):
``` SQL
SELECT ProductName  
FROM Products  
WHERE ProductID = ALL (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);
```
