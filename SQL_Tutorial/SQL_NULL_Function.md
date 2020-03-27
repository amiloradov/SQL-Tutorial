
# SQL NULL функции

SQL IFNULL(), ISNULL(), COALESCE(), and NVL() функции, которые возвращают альтернативное значение.


### Таблица "Products"

| ProductID | ProductName | UnitPrice | UnitsInStock | UnitsOnOrder |
|--|--|--|--|--|
| 1 | Jarlsberg | 10.45 | 16 | 15 |
| 2 | Mascarpone | 32.56 | 23 |  |
| 3 | Gorgonzola | 15.67 | 9 | 20 |

В приведенном ниже примере, если любое из значений «UnitsOnOrder» равно NULL, результатом будет NULL:
``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + UnitsOnOrder)
FROM Products;
```

## Примеры решения (чтобы выводить альтернаивное значение, не NULL)

### **MySQL**

Функция MySQL [IFNULL ()](https://www.w3schools.com/sql/func_mysql_ifnull.asp) позволяет вам возвращать альтернативное значение, если выражение равно NULL:
``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products;
```
**или** мы можем использовать функцию [COALESCE ()](https://www.w3schools.com/sql/func_mysql_coalesce.asp) , например:

``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder, 0))
FROM Products;
```
---

### **SQL Server**

Функция SQL Server [ISNULL ()](https://www.w3schools.com/sql/func_sqlserver_isnull.asp) позволяет вам возвращать альтернативное значение, когда выражение равно NULL:
``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + ISNULL(UnitsOnOrder, 0))
FROM Products;
```
---

### **MS Access**

Функция MS Access [IsNull ()](https://www.w3schools.com/sql/func_msaccess_isnull.asp) возвращает TRUE (-1), если выражение является нулевым значением, в противном случае FALSE (0):
``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + IIF(IsNull(UnitsOnOrder), 0, UnitsOnOrder))
FROM Products;
```
---

### ****Oracle****

Функция Oracle NVL () достигает того же результата:
``` SQL
SELECT ProductName, UnitPrice * (UnitsInStock + NVL(UnitsOnOrder, 0))
FROM Products;
```

---

[НАЗАД](/SQL_Tutorial/SQL_CASE.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_Stored_Procedure.md)
