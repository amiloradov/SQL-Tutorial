
# SQL-tutorial
 - SQL расшифровывается как язык структурированных запросов
 - SQL позволяет получить доступ к базам данных и манипулировать ими

|  |  |
|--|--|
| [Comments](/SQL_Tutorial/SQL_Comments.md) | Комментарии используются для объяснения разделов операторов SQL или для предотвращения выполнения операторов SQL. |
| [SELECT](/SQL_Tutorial/SQL_SELECT.md) | Оператор SELECT используется для выбора данных из базы данных. |
| [SELECT DISTINCT](/SQL_Tutorial/SQL_SELECT_DISTINCT.md) | Оператор SELECT DISTINCT используется для возврата только разных значений. |
| [WHERE](/SQL_Tutorial/SQL_WHERE.md) | WHERE используется для извлечения только тех записей, которые удовлетворяют указанному условию. |
| [AND, OR и NOT](/SQL_Tutorial/SQL_AND_OR_NOT.md) | Операторы И, ИЛИ, НЕТ |
| [ORDER BY](/SQL_Tutorial/SQL_ORDER_BY.md) | ORDER BY используется для сортировки результатов в порядке возрастания или убывания. |
| [INSERT INTO](/SQL_Tutorial/SQL_INSERT_INTO.md) | INSERT INTO используется для вставки новых записей в таблицу. |
| [NULL](/SQL_Tutorial/SQL_NULL.md) | Поле со значением NULL является полем без значения. Как проверить значения NULL? |
| [UPDATE](/SQL_Tutorial/SQL_UPDATE.md) | UPDATE используется для изменения существующих записей в таблице. |
| [DELETE](/SQL_Tutorial/SQL_DELETE.md) | DELETE используется для удаления существующих записей в таблице. |
| [TOP, LIMIT, ROWNUM](/SQL_Tutorial/SQL_TOP_LIMIT_ROWNUM.md) | TOP, LIMIT или ROWNUM используются для указания количества возвращаемых записей. |
| [MIN, MAX](/SQL_Tutorial/SQL_MIN_MAX.md) | Функции MIN() и MAX() возвращают наименьшее или наибольшее значение из выбранного столбца. |
| [COUNT, AVG, SUM](/SQL_Tutorial/SQL_COUNT_AVG_SUM.md) | 	* COUNT() возвращает количество строк, соответствующих заданным критериям. * AVG () возвращает среднее значение числового столбца. * SUM () возвращает общую сумму числового столбца. |
| [LIKE](/SQL_Tutorial/SQL_LIKE.md) & [Wildcards - Подстановочные операторы](/SQL_Tutorial/SQL_Wildcard.md) | * LIKE используется вместе с WHERE для поиска указанного шаблона в столбце. * [Подстановочный оператор](/SQL_Tutorial/SQL_Wildcard.md) используется для замены одного или нескольких символов в строке. |
| [IN](/SQL_Tutorial/SQL_IN.md) | * IN позволяет указать несколько значений в предложении WHERE. * IN является сокращением для нескольких условий ИЛИ. |
| [BETWEEN](/SQL_Tutorial/SQL_BETWEEN.md) | BETWEEN выбирает значения в заданном диапазоне. Значения могут быть числами, текстом или датами. |
| [Aliases](/SQL_Tutorial/SQL_Aliases.md) | Псевдонимы SQL используются, чтобы дать таблице или столбцу в таблице временное имя для лучшей читабельности. |
| [Join](/SQL_Tutorial/SQL_Join.md) | JOIN используется для объединения строк из двух или более таблиц на основе связующего столбца между ними. |
| [INNER JOIN](/SQL_Tutorial/SQL_INNER_JOIN.md) | INNER JOIN возвращает записи, которые имеют совпадающие значения в обеих таблицах. |
| [LEFT JOIN](/SQL_Tutorial/SQL_LEFT_JOIN.md) | LEFT JOIN возвращает все записи из левой таблицы (table1) и соответствующие записи из правой таблицы (table2). |
| [RIGHT JOIN](/SQL_Tutorial/SQL_RIGHT_JOIN.md) | RIGHT JOIN возвращает все записи из правой таблицы (table2) и соответствующие записи из левой таблицы (table1). |
| [FULL OUTER JOIN](/SQL_Tutorial/SQL_FULL_JOIN.md) | FULL OUTER JOIN возвращает все записи, когда есть совпадение в левой (table1) или правой (table2) табличных записях. |
| [Self JOIN](/SQL_Tutorial/SQL_Self_JOIN.md) | Self JOIN - это обычное соединение, но таблица соединяется сама с собой. |
| [UNION](/SQL_Tutorial/SQL_UNION.md) | UNION используется для объединения результирующего набора из двух или более операторов SELECT. |
| [GROUP BY](/SQL_Tutorial/SQL_GROUP_BY.md) | GROUP BY группирует строки с одинаковыми значениями в итоговые строки, например, «найти количество клиентов в каждой стране». |
| [HAVING](/SQL_Tutorial/SQL_HAVING.md) | HAVING было добавлено в SQL, поскольку ключевое слово WHERE не может использоваться с агрегатными функциями. |
| [EXISTS](/SQL_Tutorial/SQL_EXISTS.md) | EXISTS используется для проверки существования любой записи в подзапросе. Возвращает true, если подзапрос возвращает одну или несколько записей. |
| [SELECT INTO](/SQL_Tutorial/SQL_SELECT_INTO.md) | SELECT INTO копирует данные из одной таблицы в новую таблицу. |
| [INSERT INTO SELECT](/SQL_Tutorial/SQL_INSERT_INTO_SELECT.md) | INSERT INTO SELECT копирует данные из одной таблицы и вставляет их в другую таблицу. |
| [CASE](/SQL_Tutorial/SQL_CASE.md) | Оператор CASE проходит через условия и возвращает значение при выполнении первого условия. |
| [NULL Function](/SQL_Tutorial/SQL_NULL_Function.md) | SQL IFNULL(), ISNULL(), COALESCE(), and NVL() функции, которые возвращают альтернативное значение. |
| [Stored Procedure](/SQL_Tutorial/SQL_NULL_Function.md) | Stored Procedures (Хранимая процедура) - это подготовленный код SQL, который вы можете сохранить, поэтому код можно использовать снова и снова. |

# База данных
- создание
- удаление
- изменение

|  |  |
|--|--|
| [CREATE DATABASE](/SQL_DATABASE/SQL_CREATE_DATABASE.md) | Оператор CREATE DATABASE используется для создания новой базы данных SQL. |
| [DROP DATABASE](/SQL_DATABASE/SQL_DROP_DATABASE.md) | Оператор DROP DATABASE используется для удаления существующей базы данных SQL. |
| [BACKUP DATABASE](/SQL_DATABASE/SQL_BACKUP_DATABASE.md) | BACKUP DATABASE используется в SQL Server для создания полной резервной копии существующей базы данных SQL. |
| [CREATE TABLE](/SQL_DATABASE/SQL_CREATE_TABLE.md) | Оператор CREATE TABLE используется для создания новой таблицы в базе данных. |
| [DROP TABLE, TRUNCATE TABLE](/SQL_DATABASE/SQL_DROP_TABLE.md) | Оператор DROP TABLE используется для удаления существующей таблицы в базе данных. Оператор TRUNCATE TABLE используется для удаления данных внутри таблицы, но не самой таблицы. |
| [ALTER TABLE](/SQL_DATABASE/SQL_ALTER_TABLE.md) | ALTER TABLE используется для добавления, удаления или изменения столбцов в существующей таблице, а также используется для добавления и удаления различных ограничений в существующей таблицы. |
| [Constraints (Ограничения)](/SQL_DATABASE/SQL_Constraints.md) | Ограничения SQL используются для указания правил для данных в таблице. |
| [Ограничение NOT NULL](/SQL_DATABASE/SQL_NOT_NULL.md) | Ограничение NOT NULL заставляет столбец НЕ принимать значения NULL. |
| [Ограничение UNIQUE](/SQL_DATABASE/SQL_UNIQUE.md) | Ограничение UNIQUE гарантирует, что все значения в столбце различны. |
| [Ограничение PRIMARY KEY](/SQL_DATABASE/SQL_PRIMARY_KEY.md) | Ограничение PRIMARY KEY автоматически имеет ограничение [UNIQUE](/SQL_DATABASE/SQL_UNIQUE.md), однако вы можете иметь много ограничений UNIQUE на таблицу, но только одно ограничение PRIMARY KEY на таблицу. |
| [Ограничение FOREIGN KEY](/SQL_DATABASE/SQL_FOREIGN_KEY.md) | FOREIGN KEY - это ключ, используемый для связи двух таблиц. |
| [Ограничение CHECK](/SQL_DATABASE/SQL_CHECK.md) | Ограничение CHECK используется для ограничения диапазона значений, который можно поместить в столбец. |
| [Ограничение DEFAULT](/SQL_DATABASE/SQL_DEFAULT.md) | Ограничение DEFAULT используется для предоставления значения по умолчанию для столбца. |
| [CREATE INDEX](/SQL_DATABASE/SQL_CREATE_INDEX.md) | CREATE INDEX используется для создания индексов в таблицах. |
| [AUTO INCREMENT](/SQL_DATABASE/SQL_AUTO_INCREMENT.md) | Автоинкремент позволяет автоматически генерировать уникальный номер при добавлении новой записи в таблицу. |
| [DATES](/SQL_DATABASE/SQL_DATE.md) | Работа с датами. |
| [VIEWS](/SQL_DATABASE/SQL_VIEW.md) | SQL VIEW - это виртуальная таблица, основанная на наборе результатов оператора SQL. |
| [Injection](/SQL_DATABASE/SQL_Injection.md) | SQL injection является одним из наиболее распространенных методов веб-хакерства. |
| [Hosting](/SQL_DATABASE/SQL_Hosting.md) | Если вы хотите, чтобы ваш веб-сайт мог хранить и извлекать данные из базы данных, ваш веб-сервер должен иметь доступ к системе баз данных, которая использует язык SQL. |










