# SQL NULL
## Проверка значения NULL
Невозможно проверить значения NULL с помощью операторов сравнения, таких как =, <или <>.
Вместо этого нам придется использовать операторы IS NULL и IS NOT NULL.

## IS NULL Синтаксис

``` SQL
SELECT column_names FROM table_name WHERE column_name IS NULL;
```
## IS NOT NULL Синтаксис

``` SQL
SELECT column_names FROM table_name WHERE column_name IS NOT NULL;
```

## Примеры

Оператор IS NULL используется для проверки пустых значений (значений NULL).
``` SQL
SELECT CustomerName, ContactName, Address FROM Customers WHERE Address IS NULL;
```

Оператор IS NOT NULL используется для проверки непустых значений (значений NOT NULL).
``` SQL
SELECT CustomerName, ContactName, Address FROM Customers WHERE Address IS NOT NULL;
```
