# Операторы SQL  AND, OR and NOT

-   Оператор И отображает запись, если все условия, разделенные И - ИСТИНА.
-   Оператор ИЛИ отображает запись, если любое из условий, разделенных ИЛИ, имеет значение ИСТИНА.
- Оператор NOT отображает запись, если условие  НЕ ИСТИННО.

##  AND Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name WHERE condition1 AND condition2 AND condition3...;
```
##  OR Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name WHERE condition1 OR condition2 OR condition3...;
```
##  NOT Синтаксис
``` SQL
SELECT  column1, column2, ... FROM  table_name WHERE  NOT condition;
```

## Примеры

Выбрать всех клиентов из таблицы «Customers», где страна - «Belarus», а город - «Minsk»:
``` SQL
SELECT * FROM Customers WHERE Country='Belarus' AND City='Minsk';
```

Выбрать всех клиентов из таблицы «Customers», где город - «Minsk» или «Mogilev»:
``` SQL
SELECT * FROM Customers WHERE City='Minsk'  OR City='Mogilev';
```

Выбрать всех клиентов из таблицы «Customers», где страна не «Belarus»:
``` SQL
SELECT * FROM Customers WHERE NOT Country='Belarus';
```

Выбрать всех клиентов из таблицы «Customers», где страна - «Belarus», а город - «Minsk» или «Mogilev»:
``` SQL
SELECT * FROM Customers WHERE Country='Belarus'  AND (City='Minsk' OR City='Mogilev');
```

Выбрать всех клиентов из таблицы «Customers», где страна не «Belarus» и не «Russia»:
``` SQL
SELECT * FROM Customers WHERE NOT Country='Belarus' AND NOT Country='Russia';
```

---

[НАЗАД](/SQL_Tutorial/SQL_WHERE.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_ORDER_BY.md)

