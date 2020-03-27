
# Оператор SQL CASE


Оператор CASE проходит через условия и возвращает значение при выполнении первого условия (например, оператор IF-THEN-ELSE). Таким образом, если условие выполнено, оно прекращает чтение и возвращает результат. Если никакие условия не выполняются, он возвращает значение в предложении ELSE.

Если нет ELSE-части и условия не выполняются, возвращается NULL.

## CASE Синтаксис

``` SQL
CASE
WHEN condition1 THEN result1
WHEN condition2 THEN result2
WHEN conditionN THEN resultN
ELSE result
END;
```

### Таблица "OrderDetails"

| OrderDetailID | OrderID | ProductID | Quantity |
|--|--|--|--|
| 1 | 10248 | 11 | 12 | 
| 2 | 10248 | 42 | 10 |
| 3 | 10248 | 72 | 5 | 
| 4 | 10249 | 14 | 5 | 
| 5 | 10249 | 51 | 40 | 

## Примеры

Пройти через условия и возвратить значение при выполнении первого условия:
``` SQL
SELECT OrderID, Quantity,
CASE
WHEN Quantity > 30 THEN "The quantity is greater than 30"
WHEN Quantity = 30 THEN "The quantity is 30"
ELSE "The quantity is under 30"
END AS QuantityText
FROM OrderDetails;
```
---

Упорядочить клиентов по городам. Однако, если Город НЕДЕЙСТВИТЕЛЕН (City IS NULL), тогда заказ по Стране :
``` SQL
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
(CASE
WHEN City IS NULL THEN Country
ELSE City
END);
```

---

[НАЗАД](/SQL_Tutorial/SQL_INSERT_INTO_SELECT.md)  | [ВПЕРЁД](/SQL_Tutorial/SQL_NULL_Function.md)

