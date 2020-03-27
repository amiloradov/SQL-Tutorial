# SQL Wildcards - Подстановочные операторы

- Wildcards используется для замены одного или нескольких символов в строке.
- Подстановочные операторы используются с [оператором SQL LIKE](/SQL_Tutorial/SQL_LIKE.md) .
 -Все подстановочные операторы также могут быть использованы в комбинациях!

### Подстановочные операторы в MS Access
| Символ| Описание | Пример |
|--|--|--|
| * | Отображает ни одного или более символ | bl* найдёт bl, black, blue, and blob | 
| ? | Отображает один символ | h?t finds hot, hat, and hit |
| [] | Отображает один из указаных в скобках символов | h[oa]t найдет hot and hat, но не hit |
| ! | Отображает один любой символ **НЕ** указаный в скобках символов | h[!oa]t найдет hit, но не hot и hat |
| - | Отображает диапазон символов | c[a-b]t найдет cat и cbt |
| # | Отображает одну цифру | 2#5 найдет 205, 215, 225, 235, 245, 255, 265, 275, 285, и 295 |
---

### Подстановочные операторы в ### SQL Server
| Символ| Описание | Пример |
|--|--|--|
| % | Отображает ни одного или более символ | bl* найдёт bl, black, blue, and blob | 
| _ | Отображает один символ | h?t finds hot, hat, and hit |
| [] | Отображает один из указаных в скобках символов | h[oa]t найдет hot and hat, но не hit |
| ^ | Отображает один любой символ **НЕ** указаный в скобках символов | h[!oa]t найдет hit, но не hot и hat |
| - | Отображает диапазон символов | c[a-b]t найдет cat и cbt |
---

## Примеры

Выбрать всех клиентов  из города City в таблице "Customers", начинающимся с «ber»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE 'ber%';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые имеют «es» в любой позиции:

``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '%es%';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые начинаются с любого символа, за которым следует «ondon»:

``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '_ondon';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые начинаютя с «L», за которым следует любой символ, затем «n», затем любой символ и «on»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE 'L_n_on';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые начинаютя 
с «b», «s» или «p»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '[bsp]%';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые начинаютя 
с «a», «b» или «c»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '[a-c]%';
```
---

Выбрать всех клиентов  из города City в таблице "Customers", которые **НЕ** начинаютя 
с «b», «s» или «p»:
``` SQL
SELECT * FROM Customers WHERE CustomerName LIKE '[!bsp]%';
```
**ИЛИ**

``` SQL
SELECT * FROM Customers WHERE CustomerName not LIKE '[bsp]%';
```

---

[НАЗАД](/SQL_Tutorial/SQL_LIKE.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_IN.md)

