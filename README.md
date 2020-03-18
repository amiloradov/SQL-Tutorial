# SQL
 - SQL расшифровывается как язык структурированных запросов
 - SQL позволяет получить доступ к базам данных и манипулировать ими


* [Comments](/SQL_Comments.md)
	* Комментарии используются для объяснения разделов операторов SQL или для предотвращения выполнения операторов SQL.

* [SELECT](/SQL_SELECT.md)
	* Оператор SELECT используется для выбора данных из базы данных.

* [SELECT DISTINCT](/SQL_SELECT_DISTINCT.md)
	* Оператор SELECT DISTINCT используется для возврата только разных значений.

* [WHERE](/SQL_WHERE.md)
	* WHERE используется для извлечения только тех записей, которые удовлетворяют указанному условию.

* [AND, OR и NOT](/SQL_AND_OR_NOT.md)
	* Операторы И, ИЛИ, НЕТ

* [ORDER BY](/SQL_ORDER_BY.md)
	* ORDER BY используется для сортировки результатов в порядке возрастания или убывания.

* [INSERT INTO](/SQL_INSERT_INTO.md)
	* INSERT INTO используется для вставки новых записей в таблицу.

* [NULL](/SQL_NULL.md)
	* Поле со значением NULL является полем без значения. Как проверить значения NULL?

* [UPDATE](/SQL_UPDATE.md)
	* UPDATE используется для изменения существующих записей в таблице.

* [DELETE](/SQL_DELETE.md)
	* DELETE используется для удаления существующих записей в таблице.

* [TOP, LIMIT, ROWNUM](/SQL_TOP_LIMIT_ROWNUM.md)
	* TOP, LIMIT или ROWNUM используются для указания количества возвращаемых записей.

* [MIN, MAX](/SQL_MIN_MAX.md)
	* Функции MIN() и MAX() возвращают наименьшее или наибольшее значение из выбранного столбца.

* [COUNT, AVG, SUM](/SQL_COUNT_AVG_SUM.md)
	* COUNT() возвращает количество строк, соответствующих заданным критериям.
	* AVG () возвращает среднее значение числового столбца.
	* SUM () возвращает общую сумму числового столбца.

* [LIKE](/SQL_LIKE.md) || [Wildcards - Подстановочные операторы](/SQL_Wildcard.md)
	* LIKE используется вместе с WHERE для поиска указанного шаблона в столбце.
	*Подстановочный оператор используется для замены одного или нескольких символов в строке.

* [IN](/SQL_IN.md)
	* IN позволяет указать несколько значений в предложении WHERE.
	* IN является сокращением для нескольких условий ИЛИ.

* [BETWEEN](/SQL_BETWEEN.md)
	* BETWEEN выбирает значения в заданном диапазоне. Значения могут быть числами, текстом или датами.

* [Aliases](/SQL_Aliases.md)
	* Псевдонимы SQL используются, чтобы дать таблице или столбцу в таблице временное имя для лучшей читабельности.

* [Join](/SQL_Join.md)
	* JOIN используется для объединения строк из двух или более таблиц на основе связующего столбца между ними.
		* [INNER JOIN](/SQL_INNER_JOIN.md)
			* INNER JOIN возвращает записи, которые имеют совпадающие значения в обеих таблицах.
		* [LEFT JOIN](/SQL_LEFT_JOIN.md)
			* LEFT JOIN возвращает все записи из левой таблицы (table1) и соответствующие записи из правой таблицы (table2).
		* [RIGHT JOIN](/SQL_RIGHT_JOIN.md)
			* RIGHT JOIN возвращает все записи из правой таблицы (table2) и соответствующие записи из левой таблицы (table1).
		* [FULL OUTER JOIN](/SQL_FULL_JOIN.md)
			* FULL OUTER JOIN возвращает все записи, когда есть совпадение в левой (table1) или правой (table2) табличных записях.
		* [Self JOIN](/SQL_Self_JOIN.md)
			* Self JOIN - это обычное соединение, но таблица соединяется сама с собой.
* [UNION](/SQL_UNION.md)
	* UNION используется для объединения результирующего набора из двух или более операторов SELECT.

* [GROUP BY](/SQL_GROUP_BY.md)
	* GROUP BY группирует строки с одинаковыми значениями в итоговые строки, например, «найти количество клиентов в каждой стране».

* [HAVING](/SQL_HAVING.md)
	* HAVING было добавлено в SQL, поскольку ключевое слово WHERE не может использоваться с агрегатными функциями.

* [EXISTS](/SQL_EXISTS.md)
	* EXISTS используется для проверки существования любой записи в подзапросе. Возвращает true, если подзапрос возвращает одну или несколько записей.

* [SELECT INTO](/SQL_SELECT_INTO.md)
	* SELECT INTO копирует данные из одной таблицы в новую таблицу.

* [INSERT INTO SELECT](/SQL_INSERT_INTO_SELECT.md)
	* INSERT INTO SELECT копирует данные из одной таблицы и вставляет их в другую таблицу.

* [CASE](/SQL_CASE.md)
	* Оператор CASE проходит через условия и возвращает значение при выполнении первого условия.

* [NULL Function](/SQL_NULL_Function.md)
	* SQL IFNULL(), ISNULL(), COALESCE(), and NVL() функции, которые возвращают альтернативное значение.

* [Stored Procedure](/SQL_NULL_Function.md)
	* Stored Procedures (Хранимая процедура) - это подготовленный код SQL, который вы можете сохранить, поэтому код можно использовать снова и снова.


























