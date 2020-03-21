# SQL Stored Procedures

Stored Procedures (Хранимая процедура) - это подготовленный код SQL, который вы можете сохранить, поэтому код можно использовать снова и снова.

Поэтому, если у вас есть SQL-запрос, который вы пишете снова и снова, сохраните его как хранимую процедуру, а затем просто вызовите его, чтобы выполнить.

Вы также можете передать параметры в хранимую процедуру, чтобы хранимая процедура могла действовать в зависимости от значения (значений) параметра, которое передано.

## Синтаксис Stored Procedure
``` SQL
CREATE PROCEDURE procedure_name
AS  
sql_statement
GO;
```
Выполнение (запуск):
``` SQL
EXEC procedure_name;
```

### Таблица "Customers"

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|--|--|--|--|--|--|--|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22 | Sweden |

## Пример

Создать хранимую процедуру с именем «SelectAllCustomers», которая выбирает все записи из таблицы «Customers»:

``` SQL
CREATE PROCEDURE SelectAllCustomers  
AS
SELECT * FROM Customers
GO;
```
Запустим хранимую процедуру выше следующим образом:

``` SQL
EXEC SelectAllCustomers;
```
---

## Хранимая процедура с одним параметром

Создать хранимую процедуру, которая выбирает клиентов из определенного города из таблицы «Customers»:

``` SQL
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
AS
SELECT * FROM Customers WHERE City = @City  
GO;
```
Запустим хранимую процедуру выше следующим образом:

```SQL
EXEC SelectAllCustomers @City = "London";
```
---

## Хранимая процедура с несколькими параметрами

Настройка нескольких параметров очень проста. Просто перечислите каждый параметр и тип данных через запятую, как показано ниже.

Следующий оператор SQL создает хранимую процедуру, которая выбирает клиентов из определенного города с определенным почтовым индексом из таблицы «Customers»:

``` SQL
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)  
AS  
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode  
GO;
```
Запустим хранимую процедуру выше следующим образом:

```SQL
EXEC SelectAllCustomers @City = "London", @PostalCode = "WA1 1DP";
```
