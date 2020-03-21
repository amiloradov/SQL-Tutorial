# Оператор SQL  EXISTS

Оператор EXISTS используется для проверки существования любой записи в подзапросе.

Оператор EXISTS возвращает true, если подзапрос возвращает одну или несколько записей.

## EXISTS Синтаксис

``` SQL
SELECT column_name(s) 
FROM table_name
WHERE EXISTS
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

### Таблица "Suppliers"

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd | Ann Arbor | 48104 | USA |
| 4 | Tokyo Traders | Yoshi Nagas | 9-8 Sekimai Musashino-shi | Tokyo | 100 | Japan |


## Примеры

EXISTS возвращает TRUE и перечисляет поставщиков из таблицы "Suppliers" с ценой продукта (из таблицы "Products") ниже 20:
``` SQL
SELECT SupplierName
FROM Suppliers  
WHERE EXISTS (SELECT ProductName FROM Products  WHERE Products.SupplierID = Suppliers.SupplierID AND Price < 20);
```
---

EXISTS возвращает TRUE и перечисляет поставщиков из таблицы "Suppliers" с ценой продукта (из таблицы "Products") равной 22:
``` SQL
SELECT SupplierName
FROM Suppliers  
WHERE EXISTS (SELECT ProductName FROM Products  WHERE Products.SupplierID = Suppliers.SupplierID AND Price = 22);
```
