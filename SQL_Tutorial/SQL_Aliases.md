# SQL Aliases
Псевдонимы SQL используются, чтобы дать таблице или столбцу в таблице временное имя для лучшей читабельности.

Псевдонимы могут быть полезны, когда:

-   В запросе участвует более одной таблицы
-   Функции используются в запросе
-   Названия столбцов большие или не очень читаемые
-   Два или более столбцов объединены вместе

## Aliases Синтаксис для столбца

``` SQL
SELECT column_name AS alias_name FROM table_name;
```

## Aliases Синтаксис для таблицы

``` SQL
SELECT column_name(s) FROM table_name AS alias_name;
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

### Таблица "Orders"

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
|--|--|--|--|--|
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

## Примеры

Создать два псевдонима, один для столбца CustomerID и один для столбца CustomerName:
``` SQL
SELECT CustomerID AS ID, CustomerName AS Customer FROM Customers;
```
---

Создать два псевдонима, один для столбца CustomerName и один для столбца ContactName:
``` SQL
SELECT CustomerName AS Customer, ContactName AS [Contact Person] FROM Customers;
```
>  **Примечание.** Требуются двойные кавычки или квадратные скобки, если псевдоним содержит пробелы.
---

Создать псевдоним «Address», который объединяет четыре столбца (Address, PostalCode, City и Country):
``` SQL
SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address FROM Customers;
```
> **Примечание.** Для MySQL, используйте следующее:
``` SQL
SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address FROM Customers;
```
---

Выбирать все заказы от клиента с CustomerID = 4 (Around the Horn). Мы используем таблицы «Customers» и «Orders» и присваиваем им псевдонимы таблиц «c» и «o» соответственно:
``` SQL
SELECT o.OrderID, o.OrderDate, c.CustomerName
FROM Customers AS c, Orders AS o
WHERE c.CustomerName="Around the Horn" AND c.CustomerID=o.CustomerID;
```
> Следующий оператор SQL такой же, как и выше, но без псевдонимов:
``` SQL
SELECT Orders.OrderID, Orders.OrderDate, Customers.CustomerName
FROM Customers, Orders
WHERE Customers.CustomerName="Around the Horn"  AND Customers.CustomerID=Orders.CustomerID;
```

---

[НАЗАД](/SQL_Tutorial/SQL_BETWEEN.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_Join.md)

