# SQL Injection



SQL injection - это метод внедрения кода, который может разрушить вашу базу данных.

SQL injection является одним из наиболее распространенных методов веб-хакерства.

SQL injection - это размещение вредоносного кода в операторах SQL через ввод веб-страниц.

## SQL в веб-страницах

Внедрение SQL обычно происходит, когда вы запрашиваете ввод данных у пользователя, например, его имя пользователя / ID пользователя, и вместо имени / идентификатора пользователь дает вам инструкцию SQL, которую вы будете **бессознательно** выполнять в своей базе данных.

Посмотрите на следующий пример, который создает инструкцию SELECT путем добавления переменной (txtUserId) к строке выбора. Переменная извлекается из пользовательского ввода (getRequestString):

### пример

``` SQL
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

В оставшейся части этой главы описываются потенциальные опасности использования пользовательского ввода в операторах SQL.

----------

## SQL-Injection, основанная на 1 = 1, всегда TRUE

Посмотрите на пример выше. Первоначальная цель кода заключалась в создании оператора SQL для выбора пользователя с заданным идентификатором пользователя.

Если нет ничего, что могло бы помешать пользователю ввести «неправильный» ввод, пользователь может ввести некоторый «умный» ввод, например так:

> ID пользователя: 105 OR 1=1

Тогда оператор SQL будет выглядеть так:

``` SQL
SELECT * FROM Users WHERE UserId = 105 OR 1=1;
```

Вышеприведенный SQL верен и вернет ВСЕ строки из таблицы «Users», так как **OR 1 = 1** всегда TRUE.

Выглядит ли приведенный выше пример опасным? Что если таблица «Users» содержит имена и пароли?

Выражение SQL выше очень похоже на это:

```SQL
SELECT UserId, Name, Password FROM Users WHERE UserId = 105 or 1=1;
```

Хакер может получить доступ ко всем именам пользователей и паролям в базе данных, просто вставив 105 ИЛИ 1 = 1 в поле ввода.

## SQL-Injection на основе "" = "" всегда верна

Вот пример входа пользователя на веб-сайте:

> Имя пользователя:  John Doe

> Пароль:  myPass

### Пример

```SQL
uName = getRequestString("username");
uPass = getRequestString("userpassword");
  
sql = 'SELECT * FROM Users WHERE Name ="' + uName + '" AND Pass ="' + uPass + '"'
```

### Результат

```SQL
SELECT * FROM Users WHERE Name ="John Doe" AND Pass ="myPass"
```

Хакер может получить доступ к именам пользователей и паролям в базе данных, просто вставив «OR» «=» в текстовое поле имени пользователя или пароля:

> Имя пользователя:  " or ""="

> Пароль:  " or ""="

Код на сервере создаст допустимый оператор SQL, например:

```SQL
SELECT  *  FROM  Users  WHERE  Name =""  or  ""=""  AND  Pass =""  or  ""=""
```

Вышеприведенный SQL действителен и будет возвращать все строки из таблицы «Users», поскольку **OR "" = ""** всегда TRUE.

----------

## SQL-Injection на основе пакетных операторов SQL

Большинство баз данных поддерживают пакетный оператор SQL.

Пакет операторов SQL - это группа из двух или более операторов SQL, разделенных точками с запятой.

Приведенный ниже оператор SQL вернет все строки из таблицы «Users», а затем удалит таблицу «Suppliers».

### Пример

```SQL
SELECT * FROM Users; DROP TABLE Suppliers
```

Посмотрите на следующий пример:

```SQL
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

И следующий ввод:

> ID пользователя: 

Действительный оператор SQL будет выглядеть так:

### Результат

SELECT  *  FROM  Users  WHERE  UserId =  105;  DROP  TABLE  Suppliers;

----------

## Параметры SQL для защиты

Чтобы защитить веб-сайт от внедрения SQL, вы можете использовать параметры SQL.

Параметры SQL - это значения, которые добавляются в запрос SQL во время выполнения, контролируемым образом.

### Пример использования ASP.NET Razor

```SQL
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = @0";
db.Execute(txtSQL,txtUserId);
```

Обратите внимание, что параметры представлены маркером @.

Механизм SQL проверяет каждый параметр, чтобы убедиться, что он корректен для своего столбца и обрабатывается буквально, а не как часть SQL, который должен быть выполнен.

### Другой пример

```SQL
txtNam = getRequestString("CustomerName");
txtAdd = getRequestString("Address");
txtCit = getRequestString("City");
txtSQL = "INSERT INTO Customers (CustomerName,Address,City) Values(@0,@1,@2)";
db.Execute(txtSQL,txtNam,txtAdd,txtCit);
```

## Примеры

В следующих примерах показано, как создавать параметризованные запросы на некоторых распространенных веб-языках.

SELECT в ASP.NET:

```SQL
txtUserId = getRequestString("UserId");
sql = "SELECT * FROM Customers WHERE CustomerId = @0";
command = new SqlCommand(sql);
command.Parameters.AddWithValue("@0",txtUserID);
command.ExecuteReader();
```

INSERT INTO в ASP.NET:

```SQL
txtNam = getRequestString("CustomerName");
txtAdd = getRequestString("Address");
txtCit = getRequestString("City");
txtSQL = "INSERT INTO Customers (CustomerName,Address,City) Values(@0,@1,@2)";
command = new SqlCommand(txtSQL);
command.Parameters.AddWithValue("@0",txtNam);
command.Parameters.AddWithValue("@1",txtAdd);
command.Parameters.AddWithValue("@2",txtCit);
command.ExecuteNonQuery();
```

INSERT INTO в PHP:

```PHP
$stmt = $dbh->prepare("INSERT INTO Customers (CustomerName,Address,City)
VALUES (:nam, :add, :cit)");
$stmt->bindParam(':nam', $txtNam);
$stmt->bindParam(':add', $txtAdd);
$stmt->bindParam(':cit', $txtCit);
$stmt->execute();
```
---

[НАЗАД](/SQL_DATABASE/SQL_VIEW.md)  | [ВПЕРЁД](/SQL_DATABASE/SQL_Hosting.md)

