# Оператор SQL  UNION

UNION используется для объединения результирующего набора из двух или более операторов SELECT.

-   Каждый оператор SELECT в UNION должен иметь одинаковое количество столбцов
-   Столбцы также должны иметь похожие типы данных.
-   Столбцы в каждом операторе SELECT также должны быть в том же порядке

## UNION Синтаксис

``` SQL
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

## UNION ALL Синтаксис
UNION выбирает только отдельные значения по умолчанию. Чтобы разрешить повторяющиеся значения, используйте UNION ALL:
``` SQL
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```
> **Примечание.** Имена столбцов в наборе результатов обычно совпадают с именами столбцов в первом операторе SELECT в UNION.

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |

### Таблица "Suppliers"

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd | Ann Arbor | 48104 | USA |
| 4 | Tokyo Traders | Yoshi Nagas | 9-8 Sekimai Musashino-shi | Tokyo | 100 | Japan |

## Примеры

Выбрать города (только отдельные значения) из таблицы «Customers» и «Suppliers»:
``` SQL
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER  BY City;
```
> **Примечание.** Если некоторые клиенты или поставщики имеют один и тот же город, каждый город будет указан только один раз, поскольку UNION выбирает только разные значения. Используйте UNION ALL, чтобы также выбрать повторяющиеся значения!
---

Выбрать города (также повторяющиеся значения) из таблицы «Customers» и «Suppliers»:
``` SQL
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers
ORDER  BY City;
```
---

Перечислить всех клиентов из таблицы «Customers» и всех постащиков из таблицы «Suppliers»:
``` SQL
SELECT 'Customer' As Type, ContactName, City, Country 
FROM Customers 
UNION 
SELECT 'Supplier', ContactName, City, Country 
FROM Suppliers;
```
> Здесь мы создали временный столбец с именем «Type», в котором указывается, является ли контактное лицо «Customers» или «Suppliers».
> 

### SQL UNION c WHERE
Выбрать города Германии (только отдельные значения) из таблицы «Customers» и «Suppliers»:
``` SQL
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers  
WHERE Country='Germany'
ORDER  BY City;
```
---

Выбрать города Германии (также повторяющиеся значения) из таблицы «Customers» и «Suppliers»:
``` SQL
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION ALL
SELECT City, Country FROM Suppliers  
WHERE Country='Germany'
ORDER  BY City;
```
