# MySQL SQL

---

## What is SQL?

SQL is the standard language for dealing with Relational Databases.

SQL is used to insert, search, update, and delete database records.

---

## How to Use SQL

The following SQL statement selects all the records in the "Customers" table:

### Example

SELECT \* FROM Customers;

---

## Keep in Mind That...

* SQL keywords are NOT case sensitive: `select` is the same as `SELECT`

In this tutorial we will write all SQL keywords in upper-case.

---

## Semicolon after SQL Statements?

Some database systems require a semicolon at the end of each SQL statement.

Semicolon is the standard way to separate each SQL statement in database
systems that allow more than one SQL statement to be executed in the same call
to the server.

In this tutorial, we will use semicolon at the end of each SQL statement.

---

## Some of The Most Important SQL Commands

* `SELECT` - extracts data from a database
* `UPDATE` - updates data in a database
* `DELETE` - deletes data from a database
* `INSERT INTO` - inserts new data into a database
* `CREATE DATABASE` - creates a new database
* `ALTER DATABASE` - modifies a database
* `CREATE TABLE` - creates a new table
* `ALTER TABLE` - modifies a table
* `DROP TABLE` - deletes a table
* `CREATE INDEX` - creates an index (search key)
* `DROP INDEX` - deletes an index



---

# MySQL SELECT Statement

---

## The MySQL SELECT Statement

The `SELECT` statement is used to select data from a database.

The data returned is stored in a result table, called the result-set.

### SELECT Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*;

Here, column1, column2, ... are the field names of the table you want to
select data from. If you
want to select all the fields available in the table, use the following syntax:

SELECT \* FROM *table\_name*;

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

## SELECT Columns Example

The following SQL statement selects the "CustomerName", "City", and "Country" columns from the "Customers" table:

### Example

SELECT CustomerName, City, Country FROM Customers;

---

## SELECT \* Example

The following SQL statement selects ALL the columns from the "Customers" table:

### Example

SELECT \* FROM Customers;

---

---

## The MySQL SELECT DISTINCT Statement

The `SELECT DISTINCT` statement is used to return only distinct (different) values.

Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

### SELECT DISTINCT Syntax

SELECT DISTINCT *column1*, *column2, ...*  
FROM *table\_name*;

---

## SELECT Example Without DISTINCT

The following SQL statement selects all (including the duplicates) values from the "Country" column in the "Customers" table:

### Example

SELECT Country FROM Customers;

Now, let us use the `SELECT DISTINCT` statement and see the result.

---

## SELECT DISTINCT Examples

The following SQL statement selects only the DISTINCT values from the "Country" column in the "Customers" table:

### Example

SELECT DISTINCT Country FROM Customers;

The following SQL statement counts and returns the number of different (distinct)
countries in the "Customers" table:

### Example

SELECT COUNT(DISTINCT Country) FROM Customers;



---

# MySQL WHERE Clause

---

## The MySQL WHERE Clause

The `WHERE` clause is used to filter records.

It is used to extract only those records that fulfill a specified
condition.

### WHERE Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*  
WHERE *condition*;

**Note:** The `WHERE` clause is not only used in `SELECT` statements, it is also used in `UPDATE`,
`DELETE`, etc.!

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

---

## WHERE Clause Example

The following SQL statement selects all the customers from
"Mexico":

### Example

SELECT \* FROM Customers  
WHERE Country = 'Mexico';

---

## Text Fields vs. Numeric Fields

SQL requires single quotes around text values (most database systems will
also allow double quotes).

However, numeric fields should not be enclosed in quotes:

### Example

SELECT \* FROM Customers  
WHERE CustomerID = 1;

---

## Operators in The WHERE Clause

The following operators can be used in the `WHERE` clause:

| Operator | Description | Example |
| --- | --- | --- |
| = | Equal | [Try it](trymysql.asp?filename=trysql_op_equal_to) |
| > | Greater than | [Try it](trymysql.asp?filename=trysql_op_greater_than) |
| < | Less than | [Try it](trymysql.asp?filename=trysql_op_less_than) |
| >= | Greater than or equal | [Try it](trymysql.asp?filename=trysql_op_greater_than2) |
| <= | Less than or equal | [Try it](trymysql.asp?filename=trysql_op_less_than2) |
| <> | Not equal. **Note:** In some versions of SQL this operator may be written as != | [Try it](trymysql.asp?filename=trysql_op_not_equal_to) |
| BETWEEN | Between a certain range | [Try it](trymysql.asp?filename=trysql_op_between) |
| LIKE | Search for a pattern | [Try it](trymysql.asp?filename=trysql_op_like) |
| IN | To specify multiple possible values for a column | [Try it](trymysql.asp?filename=trysql_op_in) |



---

# MySQL AND, OR and NOT Operators

---

## The MySQL AND, OR and NOT Operators

The `WHERE` clause can be combined with `AND`, `OR`, and `NOT` operators.

The `AND` and `OR` operators are used to filter records based on more than one
condition:

* The `AND` operator displays a record if all the conditions separated by `AND`
  are TRUE.
* The `OR` operator displays a record if any of the conditions separated by `OR` is TRUE.

The `NOT` operator displays a record if the condition(s) is NOT TRUE.

### AND Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*  
WHERE *condition1* AND *condition2* AND *condition3 ...*;

### OR Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*  
WHERE *condition1* OR *condition2* OR *condition3 ...*;

### NOT Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*  
WHERE NOT *condition*;

---

## Demo Database

The table below shows the complete "Customers" table from the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |
| 6 | Blauer See Delikatessen | Hanna Moos | Forsterstr. 57 | Mannheim | 68306 | Germany |
| 7 | Blondel pÃ¨re et fils | FrÃ©dÃ©rique Citeaux | 24, place KlÃ©ber | Strasbourg | 67000 | France |
| 8 | BÃ³lido Comidas preparadas | MartÃ­n Sommer | C/ Araquil, 67 | Madrid | 28023 | Spain |
| 9 | Bon app' | Laurence Lebihans | 12, rue des Bouchers | Marseille | 13008 | France |
| 10 | Bottom-Dollar Marketse | Elizabeth Lincoln | 23 Tsawassen Blvd. | Tsawassen | T2F 8M4 | Canada |
| 11 | B's Beverages | Victoria Ashworth | Fauntleroy Circus | London | EC2 5NT | UK |
| 12 | Cactus Comidas para llevar | Patricio Simpson | Cerrito 333 | Buenos Aires | 1010 | Argentina |
| 13 | Centro comercial Moctezuma | Francisco Chang | Sierras de Granada 9993 | MÃ©xico D.F. | 05022 | Mexico |
| 14 | Chop-suey Chinese | Yang Wang | Hauptstr. 29 | Bern | 3012 | Switzerland |
| 15 | ComÃ©rcio Mineiro | Pedro Afonso | Av. dos LusÃ­adas, 23 | SÃ£o Paulo | 05432-043 | Brazil |
| 16 | Consolidated Holdings | Elizabeth Brown | Berkeley Gardens 12 Brewery | London | WX1 6LT | UK |
| 17 | Drachenblut Delikatessend | Sven Ottlieb | Walserweg 21 | Aachen | 52066 | Germany |
| 18 | Du monde entier | Janine Labrune | 67, rue des Cinquante Otages | Nantes | 44000 | France |
| 19 | Eastern Connection | Ann Devon | 35 King George | London | WX3 6FW | UK |
| 20 | Ernst Handel | Roland Mendel | Kirchgasse 6 | Graz | 8010 | Austria |
| 21 | Familia Arquibaldo | Aria Cruz | Rua OrÃ³s, 92 | SÃ£o Paulo | 05442-030 | Brazil |
| 22 | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel | C/ Moralzarzal, 86 | Madrid | 28034 | Spain |
| 23 | Folies gourmandes | Martine RancÃ© | 184, chaussÃ©e de Tournai | Lille | 59000 | France |
| 24 | Folk och fÃ¤ HB | Maria Larsson | Ãkergatan 24 | BrÃ¤cke | S-844 67 | Sweden |
| 25 | Frankenversand | Peter Franken | Berliner Platz 43 | MÃ¼nchen | 80805 | Germany |
| 26 | France restauration | Carine Schmitt | 54, rue Royale | Nantes | 44000 | France |
| 27 | Franchi S.p.A. | Paolo Accorti | Via Monte Bianco 34 | Torino | 10100 | Italy |
| 28 | Furia Bacalhau e Frutos do Mar | Lino Rodriguez | Jardim das rosas n. 32 | Lisboa | 1675 | Portugal |
| 29 | GalerÃ­a del gastrÃ³nomo | Eduardo Saavedra | Rambla de CataluÃ±a, 23 | Barcelona | 08022 | Spain |
| 30 | Godos Cocina TÃ­pica | JosÃ© Pedro Freyre | C/ Romero, 33 | Sevilla | 41101 | Spain |
| 31 | Gourmet Lanchonetes | AndrÃ© Fonseca | Av. Brasil, 442 | Campinas | 04876-786 | Brazil |
| 32 | Great Lakes Food Market | Howard Snyder | 2732 Baker Blvd. | Eugene | 97403 | USA |
| 33 | GROSELLA-Restaurante | Manuel Pereira | 5Âª Ave. Los Palos Grandes | Caracas | 1081 | Venezuela |
| 34 | Hanari Carnes | Mario Pontes | Rua do PaÃ§o, 67 | Rio de Janeiro | 05454-876 | Brazil |
| 35 | HILARIÃN-Abastos | Carlos HernÃ¡ndez | Carrera 22 con Ave. Carlos Soublette #8-35 | San CristÃ³bal | 5022 | Venezuela |
| 36 | Hungry Coyote Import Store | Yoshi Latimer | City Center Plaza 516 Main St. | Elgin | 97827 | USA |
| 37 | Hungry Owl All-Night Grocers | Patricia McKenna | 8 Johnstown Road | Cork |  | Ireland |
| 38 | Island Trading | Helen Bennett | Garden House Crowther Way | Cowes | PO31 7PJ | UK |
| 39 | KÃ¶niglich Essen | Philip Cramer | Maubelstr. 90 | Brandenburg | 14776 | Germany |
| 40 | La corne d'abondance | Daniel Tonini | 67, avenue de l'Europe | Versailles | 78000 | France |
| 41 | La maison d'Asie | Annette Roulet | 1 rue Alsace-Lorraine | Toulouse | 31000 | France |
| 42 | Laughing Bacchus Wine Cellars | Yoshi Tannamuri | 1900 Oak St. | Vancouver | V3F 2K1 | Canada |
| 43 | Lazy K Kountry Store | John Steel | 12 Orchestra Terrace | Walla Walla | 99362 | USA |
| 44 | Lehmanns Marktstand | Renate Messner | Magazinweg 7 | Frankfurt a.M. | 60528 | Germany |
| 45 | Let's Stop N Shop | Jaime Yorres | 87 Polk St. Suite 5 | San Francisco | 94117 | USA |
| 46 | LILA-Supermercado | Carlos GonzÃ¡lez | Carrera 52 con Ave. BolÃ­var #65-98 Llano Largo | Barquisimeto | 3508 | Venezuela |
| 47 | LINO-Delicateses | Felipe Izquierdo | Ave. 5 de Mayo Porlamar | I. de Margarita | 4980 | Venezuela |
| 48 | Lonesome Pine Restaurant | Fran Wilson | 89 Chiaroscuro Rd. | Portland | 97219 | USA |
| 49 | Magazzini Alimentari Riuniti | Giovanni Rovelli | Via Ludovico il Moro 22 | Bergamo | 24100 | Italy |
| 50 | Maison Dewey | Catherine Dewey | Rue Joseph-Bens 532 | Bruxelles | B-1180 | Belgium |
| 51 | MÃ¨re Paillarde | Jean FresniÃ¨re | 43 rue St. Laurent | MontrÃ©al | H1J 1C3 | Canada |
| 52 | Morgenstern Gesundkost | Alexander Feuer | Heerstr. 22 | Leipzig | 04179 | Germany |
| 53 | North/South | Simon Crowther | South House 300 Queensbridge | London | SW7 1RZ | UK |
| 54 | OcÃ©ano AtlÃ¡ntico Ltda. | Yvonne Moncada | Ing. Gustavo Moncada 8585 Piso 20-A | Buenos Aires | 1010 | Argentina |
| 55 | Old World Delicatessen | Rene Phillips | 2743 Bering St. | Anchorage | 99508 | USA |
| 56 | Ottilies KÃ¤seladen | Henriette Pfalzheim | Mehrheimerstr. 369 | KÃ¶ln | 50739 | Germany |
| 57 | Paris spÃ©cialitÃ©s | Marie Bertrand | 265, boulevard Charonne | Paris | 75012 | France |
| 58 | Pericles Comidas clÃ¡sicas | Guillermo FernÃ¡ndez | Calle Dr. Jorge Cash 321 | MÃ©xico D.F. | 05033 | Mexico |
| 59 | Piccolo und mehr | Georg Pipps | Geislweg 14 | Salzburg | 5020 | Austria |
| 60 | Princesa Isabel Vinhoss | Isabel de Castro | Estrada da saÃºde n. 58 | Lisboa | 1756 | Portugal |
| 61 | Que DelÃ­cia | Bernardo Batista | Rua da Panificadora, 12 | Rio de Janeiro | 02389-673 | Brazil |
| 62 | Queen Cozinha | LÃºcia Carvalho | Alameda dos CanÃ rios, 891 | SÃ£o Paulo | 05487-020 | Brazil |
| 63 | QUICK-Stop | Horst Kloss | TaucherstraÃe 10 | Cunewalde | 01307 | Germany |
| 64 | Rancho grande | Sergio GutiÃ©rrez | Av. del Libertador 900 | Buenos Aires | 1010 | Argentina |
| 65 | Rattlesnake Canyon Grocery | Paula Wilson | 2817 Milton Dr. | Albuquerque | 87110 | USA |
| 66 | Reggiani Caseifici | Maurizio Moroni | Strada Provinciale 124 | Reggio Emilia | 42100 | Italy |
| 67 | Ricardo Adocicados | Janete Limeira | Av. Copacabana, 267 | Rio de Janeiro | 02389-890 | Brazil |
| 68 | Richter Supermarkt | Michael Holz | Grenzacherweg 237 | GenÃ¨ve | 1203 | Switzerland |
| 69 | Romero y tomillo | Alejandra Camino | Gran VÃ­a, 1 | Madrid | 28001 | Spain |
| 70 | SantÃ© Gourmet | Jonas Bergulfsen | Erling Skakkes gate 78 | Stavern | 4110 | Norway |
| 71 | Save-a-lot Markets | Jose Pavarotti | 187 Suffolk Ln. | Boise | 83720 | USA |
| 72 | Seven Seas Imports | Hari Kumar | 90 Wadhurst Rd. | London | OX15 4NB | UK |
| 73 | Simons bistro | Jytte Petersen | VinbÃ¦ltet 34 | KÃ¸benhavn | 1734 | Denmark |
| 74 | SpÃ©cialitÃ©s du monde | Dominique Perrier | 25, rue Lauriston | Paris | 75016 | France |
| 75 | Split Rail Beer & Ale | Art Braunschweiger | P.O. Box 555 | Lander | 82520 | USA |
| 76 | SuprÃªmes dÃ©lices | Pascale Cartrain | Boulevard Tirou, 255 | Charleroi | B-6000 | Belgium |
| 77 | The Big Cheese | Liz Nixon | 89 Jefferson Way Suite 2 | Portland | 97201 | USA |
| 78 | The Cracker Box | Liu Wong | 55 Grizzly Peak Rd. | Butte | 59801 | USA |
| 79 | Toms SpezialitÃ¤ten | Karin Josephs | Luisenstr. 48 | MÃ¼nster | 44087 | Germany |
| 80 | Tortuga Restaurante | Miguel Angel Paolino | Avda. Azteca 123 | MÃ©xico D.F. | 05033 | Mexico |
| 81 | TradiÃ§Ã£o Hipermercados | Anabela Domingues | Av. InÃªs de Castro, 414 | SÃ£o Paulo | 05634-030 | Brazil |
| 82 | Trail's Head Gourmet Provisioners | Helvetius Nagy | 722 DaVinci Blvd. | Kirkland | 98034 | USA |
| 83 | Vaffeljernet | Palle Ibsen | SmagslÃ¸get 45 | Ãrhus | 8200 | Denmark |
| 84 | Victuailles en stock | Mary Saveley | 2, rue du Commerce | Lyon | 69004 | France |
| 85 | Vins et alcools Chevalier | Paul Henriot | 59 rue de l'Abbaye | Reims | 51100 | France |
| 86 | Die Wandernde Kuh | Rita MÃ¼ller | Adenauerallee 900 | Stuttgart | 70563 | Germany |
| 87 | Wartian Herkku | Pirkko Koskitalo | Torikatu 38 | Oulu | 90110 | Finland |
| 88 | Wellington Importadora | Paula Parente | Rua do Mercado, 12 | Resende | 08737-363 | Brazil |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |

---

---

## AND Example

The following SQL statement selects all fields from "Customers" where country is "Germany" AND city is "Berlin":

### Example

SELECT \* FROM Customers  
WHERE Country = 'Germany'
AND City = 'Berlin';

---

## OR Example

The following SQL statement selects all fields from "Customers" where city is "Berlin" OR "Stuttgart":

### Example

SELECT \* FROM Customers  
WHERE City = 'Berlin'
OR City = 'Stuttgart';

The following SQL statement selects all fields from "Customers" where country is "Germany" OR "Spain":

### Example

SELECT \* FROM Customers  
WHERE Country = 'Germany'
OR Country = 'Spain';

---

## NOT Example

The following SQL statement selects all fields from "Customers" where country is NOT "Germany":

### Example

SELECT \* FROM Customers  
WHERE
NOT Country = 'Germany';

---

## Combining AND, OR and NOT

You can also combine the `AND`, `OR` and `NOT` operators.

The following SQL statement selects all fields from "Customers" where country is "Germany" AND city must be "Berlin"
OR "Stuttgart" (use parenthesis to form complex expressions):

### Example

SELECT \* FROM Customers  
WHERE Country = 'Germany'
AND (City = 'Berlin' OR City = 'Stuttgart');

The following SQL statement selects all fields from "Customers" where country is
NOT "Germany" and NOT "USA":

### Example

SELECT \* FROM Customers  
WHERE NOT Country = 'Germany'
AND NOT Country = 'USA';



---

# MySQL ORDER BY Keyword

---

## The MySQL ORDER BY Keyword

The `ORDER BY` keyword is used to sort the result-set in ascending or
descending order.

The `ORDER BY` keyword sorts the records in ascending order by default. To sort the records in descending order, use the `DESC` keyword.

### ORDER BY Syntax

SELECT *column1*, *column2, ...*  
FROM *table\_name*  
ORDER BY *column1, column2, ...* ASC|DESC;

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

## ORDER BY Example

The following SQL statement selects all customers from the "Customers" table,
sorted by the "Country" column:

### Example

SELECT \* FROM Customers  
ORDER BY Country;

---

---

## ORDER BY DESC Example

The following SQL statement selects all customers from the "Customers" table,
sorted DESCENDING by the "Country" column:

### Example

SELECT \* FROM Customers  
ORDER BY Country DESC;

---

## ORDER BY Several Columns Example

The following SQL statement selects all customers from the "Customers" table,
sorted by the "Country" and the "CustomerName" column. This means that it orders
by Country, but if some rows have the same Country, it orders them by
CustomerName:

### Example

SELECT \* FROM Customers  
ORDER BY Country, CustomerName;

---

## ORDER BY Several Columns Example 2

The following SQL statement selects all customers from the "Customers" table,
sorted ascending by the "Country" and descending by the "CustomerName" column:

### Example

SELECT \* FROM Customers  
ORDER BY Country ASC, CustomerName DESC;



---

# MySQL INSERT INTO Statement

---

## The MySQL INSERT INTO Statement

The `INSERT INTO` statement is used to insert new records in a table.

### INSERT INTO Syntax

It is possible to write the `INSERT INTO`
statement in two ways:

1. Specify both the column names and the values to be inserted:

INSERT INTO *table\_name* (*column1*, *column2*, *column3*, ...)  
VALUES (*value1*, *value2*, *value3*, ...);

2. If you are adding values for all the columns of the table, you do not need to
specify the column names in the SQL query. However, make sure the order of the
values is in the same order as the columns in the table. Here, the `INSERT INTO` syntax
would be as follows:

INSERT INTO *table\_name*  
VALUES (*value1*, *value2*, *value3*, ...);

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind
sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |

---

---

## INSERT INTO Example

The following SQL statement inserts a new record in the "Customers" table:

### Example

INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)  
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |
| 92 | Cardinal | Tom B. Erichsen | Skagen 21 | Stavanger | 4006 | Norway |

**Did you notice that we did not insert any number into the CustomerID
field?**  
The CustomerID column is
an [auto-increment](mysql_autoincrement.asp) field and will be
generated automatically when a new record is inserted into the table.

---

## Insert Data Only in Specified Columns

It is also possible to only insert data in specific columns.

The following SQL statement will insert a new record, but only insert data in the "CustomerName",
"City", and "Country" columns (CustomerID will
be updated automatically):

### Example

INSERT INTO Customers (CustomerName, City, Country)  
VALUES ('Cardinal', 'Stavanger', 'Norway');

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |
| 92 | Cardinal | null | null | Stavanger | null | Norway |



---

# MySQL NULL Values

---

## What is a NULL Value?

A field with a NULL value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or
update a record without adding a value to this field. Then, the field will be
saved with a NULL value.

**Note:** A NULL value is different from a zero value or a field that
contains spaces. A field with a NULL value is one that has been left blank
during record creation!

---

## How to Test for NULL Values?

It is not possible to test for NULL values with comparison operators, such as
=, <, or <>.

We will have to use the `IS NULL` and `IS NOT NULL` operators instead.

### IS NULL Syntax

SELECT *column\_names*FROM *table\_name*  
WHERE *column\_name* IS NULL;

### IS NOT NULL Syntax

SELECT *column\_names*FROM *table\_name*  
WHERE *column\_name* IS NOT NULL;

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample
database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

---

## The IS NULL Operator

The `IS NULL` operator is used to test for empty values (NULL values).

The following SQL lists all customers with a NULL value in the "Address" field:

### Example

SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address
IS NULL;

**Tip:** Always use IS NULL to look for NULL values.

---

## The IS NOT NULL Operator

The `IS NOT NULL` operator is used to test for non-empty values (NOT NULL
values).

The following SQL lists all customers with a value in the "Address" field:

### Example

SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address
IS NOT NULL;



---

# MySQL UPDATE Statement

---

## The MySQL UPDATE Statement

The `UPDATE` statement is used to modify the existing records in a table.

### UPDATE Syntax

UPDATE *table\_name*  
SET *column1* = *value1*, *column2* = *value2*, ...  
WHERE *condition*;

**Note:** Be careful when updating records in a table! Notice the `WHERE` clause in the `UPDATE` statement.
The `WHERE` clause specifies which record(s) that should be updated. If
you omit the `WHERE` clause, all records in the table will be updated!

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |

---

## UPDATE Table

The following SQL statement updates the first customer (CustomerID = 1) with a new contact person *and*
a new city.

### Example

UPDATE Customers  
SET ContactName = 'Alfred Schmidt', City = 'Frankfurt'  
WHERE CustomerID = 1;

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Alfred Schmidt | Obere Str. 57 | Frankfurt | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |

---

---

## UPDATE Multiple Records

It is the `WHERE` clause that determines how many records will be updated.

The following SQL statement will
update the PostalCode to 00000 for all records where country is "Mexico":

### Example

UPDATE Customers  
SET PostalCode = 00000  
WHERE Country = 'Mexico';

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Alfred Schmidt | Obere Str. 57 | Frankfurt | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 00000 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 00000 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |

---

## Update Warning!

Be careful when updating records. If you omit the `WHERE` clause, ALL records
will be updated!

### Example

UPDATE Customers  
SET PostalCode = 00000;

The selection from the "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Alfred Schmidt | Obere Str. 57 | Frankfurt | 00000 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 00000 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 00000 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | 00000 | UK |



---

# MySQL DELETE Statement

---

## The MySQL DELETE Statement

The `DELETE` statement is used to delete existing records in a table.

### DELETE Syntax

DELETE FROM *table\_name* WHERE *condition*;

**Note:** Be careful when deleting records in a table! Notice the `WHERE` clause in the
`DELETE` statement.
The `WHERE` clause specifies which record(s) should be deleted. If
you omit the `WHERE` clause, all records in the table will be deleted!

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample
database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

---

## SQL DELETE Example

The following SQL statement deletes the customer "Alfreds Futterkiste" from
the "Customers" table:

### Example

DELETE FROM Customers
WHERE CustomerName='Alfreds Futterkiste';

The "Customers" table will now look like this:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

## Delete All Records

It is possible to delete all rows in a table without deleting the table. This
means that the table structure, attributes, and indexes will be intact:

DELETE FROM *table\_name*;

The following SQL statement deletes all rows in the "Customers" table,
without deleting the table:

### Example

DELETE FROM Customers;



---

# MySQL LIMIT Clause

---

## The MySQL LIMIT Clause

The `LIMIT` clause is used to specify the number of records to return.

The `LIMIT` clause is useful on large tables with thousands of
records. Returning a large number of records can impact performance.

### LIMIT Syntax

SELECT *column\_name(s)*  
FROM *table\_name*WHERE *condition*  
LIMIT *number*;

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

---

## MySQL LIMIT Examples

The following SQL statement selects the first three records from the "Customers" table:

### Example

SELECT \* FROM Customers  
LIMIT 3;

What if we want to select records 4 - 6 (inclusive)?

MySQL provides a way to handle this: by using OFFSET.

The SQL query below says "return only 3 records, start on record 4 (OFFSET
3)":

### Example

SELECT \* FROM Customers  
LIMIT 3 OFFSET 3;

---

## ADD a WHERE CLAUSE

The following SQL statement selects the first three records from the "Customers" table,
where the country is "Germany":

### Example

SELECT \* FROM Customers  
WHERE Country='Germany'  
LIMIT 3;

---

## ADD an ORDER BY CLAUSE

The following SQL statement sorts the customers by country before returning the first three records from the selection:

### Example

SELECT \* FROM Customers  
ORDER BY Country  
LIMIT 3;



---

# MySQL MIN() and MAX() Functions

---

## MySQL MIN() and MAX() Functions

The `MIN()` function returns the smallest value of the selected column.

The `MAX()` function returns the largest value of the selected column.

### MIN() Syntax

SELECT MIN(*column\_name*)  
FROM *table\_name*  
WHERE *condition*;

### MAX() Syntax

SELECT MAX(*column\_name*)  
FROM *table\_name*  
WHERE *condition*;

---

## Demo Database

Below is a selection from the "Products" table in the Northwind sample database:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| --- | --- | --- | --- | --- | --- |
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 2 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 2 | 2 | 36 boxes | 21.35 |

---

## MIN() Example

The following SQL statement finds the price of the cheapest product:

### Example

SELECT MIN(Price) AS SmallestPrice  
FROM Products;

---

---

## MAX() Example

The following SQL statement finds the price of the most expensive product:

### Example

SELECT MAX(Price) AS LargestPrice  
FROM Products;



---

# MySQL COUNT(), AVG() and SUM() Functions

---

## MySQL COUNT(), AVG() and SUM() Functions

The `COUNT()` function returns the number of rows that matches a specified criterion.

### COUNT() Syntax

SELECT COUNT(*column\_name*)  
FROM *table\_name*  
WHERE *condition*;

The `AVG()` function returns the average value of a numeric column.

### AVG() Syntax

SELECT AVG(*column\_name*)  
FROM *table\_name*  
WHERE *condition*;

The `SUM()` function returns the total sum of a numeric column.

### SUM() Syntax

SELECT SUM(*column\_name*)  
FROM *table\_name*  
WHERE *condition*;

---

## Demo Database

Below is a selection from the "Products" table in the Northwind sample database:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| --- | --- | --- | --- | --- | --- |
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 2 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 2 | 2 | 36 boxes | 21.35 |

---

---

## COUNT() Example

The following SQL statement finds the number of products:

### Example

SELECT COUNT(ProductID)  
FROM Products;

**Note:** NULL values are not counted.

---

## AVG() Example

The following SQL statement finds the average price of all products:

### Example

SELECT AVG(Price)  
FROM Products;

**Note:** NULL values are ignored.

---

## Demo Database

Below is a selection from the "OrderDetails" table in the Northwind
sample database:

| OrderDetailID | OrderID | ProductID | Quantity |
| --- | --- | --- | --- |
| 1 | 10248 | 11 | 12 |
| 2 | 10248 | 42 | 10 |
| 3 | 10248 | 72 | 5 |
| 4 | 10249 | 14 | 9 |
| 5 | 10249 | 51 | 40 |

---

## SUM() Example

The following SQL statement finds the sum of the "Quantity" fields
in the "OrderDetails" table:

### Example

SELECT SUM(Quantity)  
FROM OrderDetails;

**Note:** NULL values are ignored.



---

# MySQL LIKE Operator

---

## The MySQL LIKE Operator

The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the `LIKE` operator:

* The percent sign (%) represents zero, one, or multiple characters
* The underscore sign (\_) represents one, single character

The percent sign and the underscore can also be used in combinations!

### LIKE Syntax

SELECT *column1, column2, ...*  
FROM *table\_name*  
WHERE *columnN* LIKE *pattern*;

**Tip:** You can also combine any number of conditions using `AND` or `OR` operators.

Here are some examples showing different `LIKE` operators with '%' and '\_' wildcards:

| LIKE Operator | Description |
| --- | --- |
| WHERE CustomerName LIKE 'a%' | Finds any values that start with "a" |
| WHERE CustomerName LIKE '%a' | Finds any values that end with "a" |
| WHERE CustomerName LIKE '%or%' | Finds any values that have "or" in any position |
| WHERE CustomerName LIKE '\_r%' | Finds any values that have "r" in the second position |
| WHERE CustomerName LIKE 'a\_%' | Finds any values that start with "a" and are at least 2 characters in length |
| WHERE CustomerName LIKE 'a\_\_%' | Finds any values that start with "a" and are at least 3 characters in length |
| WHERE ContactName LIKE 'a%o' | Finds any values that start with "a" and ends with "o" |

---

## Demo Database

The table below shows the complete "Customers" table from the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |
| 6 | Blauer See Delikatessen | Hanna Moos | Forsterstr. 57 | Mannheim | 68306 | Germany |
| 7 | Blondel pÃ¨re et fils | FrÃ©dÃ©rique Citeaux | 24, place KlÃ©ber | Strasbourg | 67000 | France |
| 8 | BÃ³lido Comidas preparadas | MartÃ­n Sommer | C/ Araquil, 67 | Madrid | 28023 | Spain |
| 9 | Bon app' | Laurence Lebihans | 12, rue des Bouchers | Marseille | 13008 | France |
| 10 | Bottom-Dollar Marketse | Elizabeth Lincoln | 23 Tsawassen Blvd. | Tsawassen | T2F 8M4 | Canada |
| 11 | B's Beverages | Victoria Ashworth | Fauntleroy Circus | London | EC2 5NT | UK |
| 12 | Cactus Comidas para llevar | Patricio Simpson | Cerrito 333 | Buenos Aires | 1010 | Argentina |
| 13 | Centro comercial Moctezuma | Francisco Chang | Sierras de Granada 9993 | MÃ©xico D.F. | 05022 | Mexico |
| 14 | Chop-suey Chinese | Yang Wang | Hauptstr. 29 | Bern | 3012 | Switzerland |
| 15 | ComÃ©rcio Mineiro | Pedro Afonso | Av. dos LusÃ­adas, 23 | SÃ£o Paulo | 05432-043 | Brazil |
| 16 | Consolidated Holdings | Elizabeth Brown | Berkeley Gardens 12 Brewery | London | WX1 6LT | UK |
| 17 | Drachenblut Delikatessend | Sven Ottlieb | Walserweg 21 | Aachen | 52066 | Germany |
| 18 | Du monde entier | Janine Labrune | 67, rue des Cinquante Otages | Nantes | 44000 | France |
| 19 | Eastern Connection | Ann Devon | 35 King George | London | WX3 6FW | UK |
| 20 | Ernst Handel | Roland Mendel | Kirchgasse 6 | Graz | 8010 | Austria |
| 21 | Familia Arquibaldo | Aria Cruz | Rua OrÃ³s, 92 | SÃ£o Paulo | 05442-030 | Brazil |
| 22 | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel | C/ Moralzarzal, 86 | Madrid | 28034 | Spain |
| 23 | Folies gourmandes | Martine RancÃ© | 184, chaussÃ©e de Tournai | Lille | 59000 | France |
| 24 | Folk och fÃ¤ HB | Maria Larsson | Ãkergatan 24 | BrÃ¤cke | S-844 67 | Sweden |
| 25 | Frankenversand | Peter Franken | Berliner Platz 43 | MÃ¼nchen | 80805 | Germany |
| 26 | France restauration | Carine Schmitt | 54, rue Royale | Nantes | 44000 | France |
| 27 | Franchi S.p.A. | Paolo Accorti | Via Monte Bianco 34 | Torino | 10100 | Italy |
| 28 | Furia Bacalhau e Frutos do Mar | Lino Rodriguez | Jardim das rosas n. 32 | Lisboa | 1675 | Portugal |
| 29 | GalerÃ­a del gastrÃ³nomo | Eduardo Saavedra | Rambla de CataluÃ±a, 23 | Barcelona | 08022 | Spain |
| 30 | Godos Cocina TÃ­pica | JosÃ© Pedro Freyre | C/ Romero, 33 | Sevilla | 41101 | Spain |
| 31 | Gourmet Lanchonetes | AndrÃ© Fonseca | Av. Brasil, 442 | Campinas | 04876-786 | Brazil |
| 32 | Great Lakes Food Market | Howard Snyder | 2732 Baker Blvd. | Eugene | 97403 | USA |
| 33 | GROSELLA-Restaurante | Manuel Pereira | 5Âª Ave. Los Palos Grandes | Caracas | 1081 | Venezuela |
| 34 | Hanari Carnes | Mario Pontes | Rua do PaÃ§o, 67 | Rio de Janeiro | 05454-876 | Brazil |
| 35 | HILARIÃN-Abastos | Carlos HernÃ¡ndez | Carrera 22 con Ave. Carlos Soublette #8-35 | San CristÃ³bal | 5022 | Venezuela |
| 36 | Hungry Coyote Import Store | Yoshi Latimer | City Center Plaza 516 Main St. | Elgin | 97827 | USA |
| 37 | Hungry Owl All-Night Grocers | Patricia McKenna | 8 Johnstown Road | Cork |  | Ireland |
| 38 | Island Trading | Helen Bennett | Garden House Crowther Way | Cowes | PO31 7PJ | UK |
| 39 | KÃ¶niglich Essen | Philip Cramer | Maubelstr. 90 | Brandenburg | 14776 | Germany |
| 40 | La corne d'abondance | Daniel Tonini | 67, avenue de l'Europe | Versailles | 78000 | France |
| 41 | La maison d'Asie | Annette Roulet | 1 rue Alsace-Lorraine | Toulouse | 31000 | France |
| 42 | Laughing Bacchus Wine Cellars | Yoshi Tannamuri | 1900 Oak St. | Vancouver | V3F 2K1 | Canada |
| 43 | Lazy K Kountry Store | John Steel | 12 Orchestra Terrace | Walla Walla | 99362 | USA |
| 44 | Lehmanns Marktstand | Renate Messner | Magazinweg 7 | Frankfurt a.M. | 60528 | Germany |
| 45 | Let's Stop N Shop | Jaime Yorres | 87 Polk St. Suite 5 | San Francisco | 94117 | USA |
| 46 | LILA-Supermercado | Carlos GonzÃ¡lez | Carrera 52 con Ave. BolÃ­var #65-98 Llano Largo | Barquisimeto | 3508 | Venezuela |
| 47 | LINO-Delicateses | Felipe Izquierdo | Ave. 5 de Mayo Porlamar | I. de Margarita | 4980 | Venezuela |
| 48 | Lonesome Pine Restaurant | Fran Wilson | 89 Chiaroscuro Rd. | Portland | 97219 | USA |
| 49 | Magazzini Alimentari Riuniti | Giovanni Rovelli | Via Ludovico il Moro 22 | Bergamo | 24100 | Italy |
| 50 | Maison Dewey | Catherine Dewey | Rue Joseph-Bens 532 | Bruxelles | B-1180 | Belgium |
| 51 | MÃ¨re Paillarde | Jean FresniÃ¨re | 43 rue St. Laurent | MontrÃ©al | H1J 1C3 | Canada |
| 52 | Morgenstern Gesundkost | Alexander Feuer | Heerstr. 22 | Leipzig | 04179 | Germany |
| 53 | North/South | Simon Crowther | South House 300 Queensbridge | London | SW7 1RZ | UK |
| 54 | OcÃ©ano AtlÃ¡ntico Ltda. | Yvonne Moncada | Ing. Gustavo Moncada 8585 Piso 20-A | Buenos Aires | 1010 | Argentina |
| 55 | Old World Delicatessen | Rene Phillips | 2743 Bering St. | Anchorage | 99508 | USA |
| 56 | Ottilies KÃ¤seladen | Henriette Pfalzheim | Mehrheimerstr. 369 | KÃ¶ln | 50739 | Germany |
| 57 | Paris spÃ©cialitÃ©s | Marie Bertrand | 265, boulevard Charonne | Paris | 75012 | France |
| 58 | Pericles Comidas clÃ¡sicas | Guillermo FernÃ¡ndez | Calle Dr. Jorge Cash 321 | MÃ©xico D.F. | 05033 | Mexico |
| 59 | Piccolo und mehr | Georg Pipps | Geislweg 14 | Salzburg | 5020 | Austria |
| 60 | Princesa Isabel Vinhoss | Isabel de Castro | Estrada da saÃºde n. 58 | Lisboa | 1756 | Portugal |
| 61 | Que DelÃ­cia | Bernardo Batista | Rua da Panificadora, 12 | Rio de Janeiro | 02389-673 | Brazil |
| 62 | Queen Cozinha | LÃºcia Carvalho | Alameda dos CanÃ rios, 891 | SÃ£o Paulo | 05487-020 | Brazil |
| 63 | QUICK-Stop | Horst Kloss | TaucherstraÃe 10 | Cunewalde | 01307 | Germany |
| 64 | Rancho grande | Sergio GutiÃ©rrez | Av. del Libertador 900 | Buenos Aires | 1010 | Argentina |
| 65 | Rattlesnake Canyon Grocery | Paula Wilson | 2817 Milton Dr. | Albuquerque | 87110 | USA |
| 66 | Reggiani Caseifici | Maurizio Moroni | Strada Provinciale 124 | Reggio Emilia | 42100 | Italy |
| 67 | Ricardo Adocicados | Janete Limeira | Av. Copacabana, 267 | Rio de Janeiro | 02389-890 | Brazil |
| 68 | Richter Supermarkt | Michael Holz | Grenzacherweg 237 | GenÃ¨ve | 1203 | Switzerland |
| 69 | Romero y tomillo | Alejandra Camino | Gran VÃ­a, 1 | Madrid | 28001 | Spain |
| 70 | SantÃ© Gourmet | Jonas Bergulfsen | Erling Skakkes gate 78 | Stavern | 4110 | Norway |
| 71 | Save-a-lot Markets | Jose Pavarotti | 187 Suffolk Ln. | Boise | 83720 | USA |
| 72 | Seven Seas Imports | Hari Kumar | 90 Wadhurst Rd. | London | OX15 4NB | UK |
| 73 | Simons bistro | Jytte Petersen | VinbÃ¦ltet 34 | KÃ¸benhavn | 1734 | Denmark |
| 74 | SpÃ©cialitÃ©s du monde | Dominique Perrier | 25, rue Lauriston | Paris | 75016 | France |
| 75 | Split Rail Beer & Ale | Art Braunschweiger | P.O. Box 555 | Lander | 82520 | USA |
| 76 | SuprÃªmes dÃ©lices | Pascale Cartrain | Boulevard Tirou, 255 | Charleroi | B-6000 | Belgium |
| 77 | The Big Cheese | Liz Nixon | 89 Jefferson Way Suite 2 | Portland | 97201 | USA |
| 78 | The Cracker Box | Liu Wong | 55 Grizzly Peak Rd. | Butte | 59801 | USA |
| 79 | Toms SpezialitÃ¤ten | Karin Josephs | Luisenstr. 48 | MÃ¼nster | 44087 | Germany |
| 80 | Tortuga Restaurante | Miguel Angel Paolino | Avda. Azteca 123 | MÃ©xico D.F. | 05033 | Mexico |
| 81 | TradiÃ§Ã£o Hipermercados | Anabela Domingues | Av. InÃªs de Castro, 414 | SÃ£o Paulo | 05634-030 | Brazil |
| 82 | Trail's Head Gourmet Provisioners | Helvetius Nagy | 722 DaVinci Blvd. | Kirkland | 98034 | USA |
| 83 | Vaffeljernet | Palle Ibsen | SmagslÃ¸get 45 | Ãrhus | 8200 | Denmark |
| 84 | Victuailles en stock | Mary Saveley | 2, rue du Commerce | Lyon | 69004 | France |
| 85 | Vins et alcools Chevalier | Paul Henriot | 59 rue de l'Abbaye | Reims | 51100 | France |
| 86 | Die Wandernde Kuh | Rita MÃ¼ller | Adenauerallee 900 | Stuttgart | 70563 | Germany |
| 87 | Wartian Herkku | Pirkko Koskitalo | Torikatu 38 | Oulu | 90110 | Finland |
| 88 | Wellington Importadora | Paula Parente | Rua do Mercado, 12 | Resende | 08737-363 | Brazil |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |

---

---

## SQL LIKE Examples

The following SQL statement selects all customers with a CustomerName starting with
"a":

### Example

SELECT \* FROM Customers  
WHERE CustomerName LIKE 'a%';

The following SQL statement selects all customers with a CustomerName ending with "a":

### Example

SELECT \* FROM Customers  
WHERE CustomerName LIKE '%a';

The following SQL statement selects all customers with a CustomerName that
have "or" in any position:

### Example

SELECT \* FROM Customers  
WHERE CustomerName LIKE '%or%';

The following SQL statement selects all customers with a CustomerName that
have "r" in the second position:

### Example

SELECT \* FROM Customers  
WHERE CustomerName LIKE '\_r%';

The following SQL statement selects all customers with a CustomerName that
starts with "a" and are at least 3 characters in length:

### Example

SELECT \* FROM Customers  
WHERE CustomerName LIKE 'a\_\_%';

The following SQL statement selects all customers with a ContactName that
starts with "a" and ends with "o":

### Example

SELECT \* FROM Customers  
WHERE ContactName LIKE 'a%o';

The following SQL statement selects all customers with a CustomerName that
does
NOT start with "a":

### Example

SELECT \* FROM Customers  
WHERE CustomerName NOT LIKE 'a%';



---

# MySQL Wildcards

---

## MySQL Wildcard Characters

A wildcard character is used to substitute one or more characters in a string.

Wildcard characters are used with the `LIKE`
operator. The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

### Wildcard Characters in MySQL

| Symbol | Description | Example |
| --- | --- | --- |
| % | Represents zero or more characters | bl% finds bl, black, blue, and blob |
| \_ | Represents a single character | h\_t finds hot, hat, and hit |

The wildcards can also be used in combinations!

Here are some examples showing different `LIKE` operators with '%' and '\_' wildcards:

| LIKE Operator | Description |
| --- | --- |
| WHERE CustomerName LIKE 'a%' | Finds any values that starts with "a" |
| WHERE CustomerName LIKE '%a' | Finds any values that ends with "a" |
| WHERE CustomerName LIKE '%or%' | Finds any values that have "or" in any position |
| WHERE CustomerName LIKE '\_r%' | Finds any values that have "r" in the second position |
| WHERE CustomerName LIKE 'a\_%\_%' | Finds any values that starts with "a" and are at least 3 characters in length |
| WHERE ContactName LIKE 'a%o' | Finds any values that starts with "a" and ends with "o" |

---

## Demo Database

The table below shows the complete "Customers" table from the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |
| 6 | Blauer See Delikatessen | Hanna Moos | Forsterstr. 57 | Mannheim | 68306 | Germany |
| 7 | Blondel pÃ¨re et fils | FrÃ©dÃ©rique Citeaux | 24, place KlÃ©ber | Strasbourg | 67000 | France |
| 8 | BÃ³lido Comidas preparadas | MartÃ­n Sommer | C/ Araquil, 67 | Madrid | 28023 | Spain |
| 9 | Bon app' | Laurence Lebihans | 12, rue des Bouchers | Marseille | 13008 | France |
| 10 | Bottom-Dollar Marketse | Elizabeth Lincoln | 23 Tsawassen Blvd. | Tsawassen | T2F 8M4 | Canada |
| 11 | B's Beverages | Victoria Ashworth | Fauntleroy Circus | London | EC2 5NT | UK |
| 12 | Cactus Comidas para llevar | Patricio Simpson | Cerrito 333 | Buenos Aires | 1010 | Argentina |
| 13 | Centro comercial Moctezuma | Francisco Chang | Sierras de Granada 9993 | MÃ©xico D.F. | 05022 | Mexico |
| 14 | Chop-suey Chinese | Yang Wang | Hauptstr. 29 | Bern | 3012 | Switzerland |
| 15 | ComÃ©rcio Mineiro | Pedro Afonso | Av. dos LusÃ­adas, 23 | SÃ£o Paulo | 05432-043 | Brazil |
| 16 | Consolidated Holdings | Elizabeth Brown | Berkeley Gardens 12 Brewery | London | WX1 6LT | UK |
| 17 | Drachenblut Delikatessend | Sven Ottlieb | Walserweg 21 | Aachen | 52066 | Germany |
| 18 | Du monde entier | Janine Labrune | 67, rue des Cinquante Otages | Nantes | 44000 | France |
| 19 | Eastern Connection | Ann Devon | 35 King George | London | WX3 6FW | UK |
| 20 | Ernst Handel | Roland Mendel | Kirchgasse 6 | Graz | 8010 | Austria |
| 21 | Familia Arquibaldo | Aria Cruz | Rua OrÃ³s, 92 | SÃ£o Paulo | 05442-030 | Brazil |
| 22 | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel | C/ Moralzarzal, 86 | Madrid | 28034 | Spain |
| 23 | Folies gourmandes | Martine RancÃ© | 184, chaussÃ©e de Tournai | Lille | 59000 | France |
| 24 | Folk och fÃ¤ HB | Maria Larsson | Ãkergatan 24 | BrÃ¤cke | S-844 67 | Sweden |
| 25 | Frankenversand | Peter Franken | Berliner Platz 43 | MÃ¼nchen | 80805 | Germany |
| 26 | France restauration | Carine Schmitt | 54, rue Royale | Nantes | 44000 | France |
| 27 | Franchi S.p.A. | Paolo Accorti | Via Monte Bianco 34 | Torino | 10100 | Italy |
| 28 | Furia Bacalhau e Frutos do Mar | Lino Rodriguez | Jardim das rosas n. 32 | Lisboa | 1675 | Portugal |
| 29 | GalerÃ­a del gastrÃ³nomo | Eduardo Saavedra | Rambla de CataluÃ±a, 23 | Barcelona | 08022 | Spain |
| 30 | Godos Cocina TÃ­pica | JosÃ© Pedro Freyre | C/ Romero, 33 | Sevilla | 41101 | Spain |
| 31 | Gourmet Lanchonetes | AndrÃ© Fonseca | Av. Brasil, 442 | Campinas | 04876-786 | Brazil |
| 32 | Great Lakes Food Market | Howard Snyder | 2732 Baker Blvd. | Eugene | 97403 | USA |
| 33 | GROSELLA-Restaurante | Manuel Pereira | 5Âª Ave. Los Palos Grandes | Caracas | 1081 | Venezuela |
| 34 | Hanari Carnes | Mario Pontes | Rua do PaÃ§o, 67 | Rio de Janeiro | 05454-876 | Brazil |
| 35 | HILARIÃN-Abastos | Carlos HernÃ¡ndez | Carrera 22 con Ave. Carlos Soublette #8-35 | San CristÃ³bal | 5022 | Venezuela |
| 36 | Hungry Coyote Import Store | Yoshi Latimer | City Center Plaza 516 Main St. | Elgin | 97827 | USA |
| 37 | Hungry Owl All-Night Grocers | Patricia McKenna | 8 Johnstown Road | Cork |  | Ireland |
| 38 | Island Trading | Helen Bennett | Garden House Crowther Way | Cowes | PO31 7PJ | UK |
| 39 | KÃ¶niglich Essen | Philip Cramer | Maubelstr. 90 | Brandenburg | 14776 | Germany |
| 40 | La corne d'abondance | Daniel Tonini | 67, avenue de l'Europe | Versailles | 78000 | France |
| 41 | La maison d'Asie | Annette Roulet | 1 rue Alsace-Lorraine | Toulouse | 31000 | France |
| 42 | Laughing Bacchus Wine Cellars | Yoshi Tannamuri | 1900 Oak St. | Vancouver | V3F 2K1 | Canada |
| 43 | Lazy K Kountry Store | John Steel | 12 Orchestra Terrace | Walla Walla | 99362 | USA |
| 44 | Lehmanns Marktstand | Renate Messner | Magazinweg 7 | Frankfurt a.M. | 60528 | Germany |
| 45 | Let's Stop N Shop | Jaime Yorres | 87 Polk St. Suite 5 | San Francisco | 94117 | USA |
| 46 | LILA-Supermercado | Carlos GonzÃ¡lez | Carrera 52 con Ave. BolÃ­var #65-98 Llano Largo | Barquisimeto | 3508 | Venezuela |
| 47 | LINO-Delicateses | Felipe Izquierdo | Ave. 5 de Mayo Porlamar | I. de Margarita | 4980 | Venezuela |
| 48 | Lonesome Pine Restaurant | Fran Wilson | 89 Chiaroscuro Rd. | Portland | 97219 | USA |
| 49 | Magazzini Alimentari Riuniti | Giovanni Rovelli | Via Ludovico il Moro 22 | Bergamo | 24100 | Italy |
| 50 | Maison Dewey | Catherine Dewey | Rue Joseph-Bens 532 | Bruxelles | B-1180 | Belgium |
| 51 | MÃ¨re Paillarde | Jean FresniÃ¨re | 43 rue St. Laurent | MontrÃ©al | H1J 1C3 | Canada |
| 52 | Morgenstern Gesundkost | Alexander Feuer | Heerstr. 22 | Leipzig | 04179 | Germany |
| 53 | North/South | Simon Crowther | South House 300 Queensbridge | London | SW7 1RZ | UK |
| 54 | OcÃ©ano AtlÃ¡ntico Ltda. | Yvonne Moncada | Ing. Gustavo Moncada 8585 Piso 20-A | Buenos Aires | 1010 | Argentina |
| 55 | Old World Delicatessen | Rene Phillips | 2743 Bering St. | Anchorage | 99508 | USA |
| 56 | Ottilies KÃ¤seladen | Henriette Pfalzheim | Mehrheimerstr. 369 | KÃ¶ln | 50739 | Germany |
| 57 | Paris spÃ©cialitÃ©s | Marie Bertrand | 265, boulevard Charonne | Paris | 75012 | France |
| 58 | Pericles Comidas clÃ¡sicas | Guillermo FernÃ¡ndez | Calle Dr. Jorge Cash 321 | MÃ©xico D.F. | 05033 | Mexico |
| 59 | Piccolo und mehr | Georg Pipps | Geislweg 14 | Salzburg | 5020 | Austria |
| 60 | Princesa Isabel Vinhoss | Isabel de Castro | Estrada da saÃºde n. 58 | Lisboa | 1756 | Portugal |
| 61 | Que DelÃ­cia | Bernardo Batista | Rua da Panificadora, 12 | Rio de Janeiro | 02389-673 | Brazil |
| 62 | Queen Cozinha | LÃºcia Carvalho | Alameda dos CanÃ rios, 891 | SÃ£o Paulo | 05487-020 | Brazil |
| 63 | QUICK-Stop | Horst Kloss | TaucherstraÃe 10 | Cunewalde | 01307 | Germany |
| 64 | Rancho grande | Sergio GutiÃ©rrez | Av. del Libertador 900 | Buenos Aires | 1010 | Argentina |
| 65 | Rattlesnake Canyon Grocery | Paula Wilson | 2817 Milton Dr. | Albuquerque | 87110 | USA |
| 66 | Reggiani Caseifici | Maurizio Moroni | Strada Provinciale 124 | Reggio Emilia | 42100 | Italy |
| 67 | Ricardo Adocicados | Janete Limeira | Av. Copacabana, 267 | Rio de Janeiro | 02389-890 | Brazil |
| 68 | Richter Supermarkt | Michael Holz | Grenzacherweg 237 | GenÃ¨ve | 1203 | Switzerland |
| 69 | Romero y tomillo | Alejandra Camino | Gran VÃ­a, 1 | Madrid | 28001 | Spain |
| 70 | SantÃ© Gourmet | Jonas Bergulfsen | Erling Skakkes gate 78 | Stavern | 4110 | Norway |
| 71 | Save-a-lot Markets | Jose Pavarotti | 187 Suffolk Ln. | Boise | 83720 | USA |
| 72 | Seven Seas Imports | Hari Kumar | 90 Wadhurst Rd. | London | OX15 4NB | UK |
| 73 | Simons bistro | Jytte Petersen | VinbÃ¦ltet 34 | KÃ¸benhavn | 1734 | Denmark |
| 74 | SpÃ©cialitÃ©s du monde | Dominique Perrier | 25, rue Lauriston | Paris | 75016 | France |
| 75 | Split Rail Beer & Ale | Art Braunschweiger | P.O. Box 555 | Lander | 82520 | USA |
| 76 | SuprÃªmes dÃ©lices | Pascale Cartrain | Boulevard Tirou, 255 | Charleroi | B-6000 | Belgium |
| 77 | The Big Cheese | Liz Nixon | 89 Jefferson Way Suite 2 | Portland | 97201 | USA |
| 78 | The Cracker Box | Liu Wong | 55 Grizzly Peak Rd. | Butte | 59801 | USA |
| 79 | Toms SpezialitÃ¤ten | Karin Josephs | Luisenstr. 48 | MÃ¼nster | 44087 | Germany |
| 80 | Tortuga Restaurante | Miguel Angel Paolino | Avda. Azteca 123 | MÃ©xico D.F. | 05033 | Mexico |
| 81 | TradiÃ§Ã£o Hipermercados | Anabela Domingues | Av. InÃªs de Castro, 414 | SÃ£o Paulo | 05634-030 | Brazil |
| 82 | Trail's Head Gourmet Provisioners | Helvetius Nagy | 722 DaVinci Blvd. | Kirkland | 98034 | USA |
| 83 | Vaffeljernet | Palle Ibsen | SmagslÃ¸get 45 | Ãrhus | 8200 | Denmark |
| 84 | Victuailles en stock | Mary Saveley | 2, rue du Commerce | Lyon | 69004 | France |
| 85 | Vins et alcools Chevalier | Paul Henriot | 59 rue de l'Abbaye | Reims | 51100 | France |
| 86 | Die Wandernde Kuh | Rita MÃ¼ller | Adenauerallee 900 | Stuttgart | 70563 | Germany |
| 87 | Wartian Herkku | Pirkko Koskitalo | Torikatu 38 | Oulu | 90110 | Finland |
| 88 | Wellington Importadora | Paula Parente | Rua do Mercado, 12 | Resende | 08737-363 | Brazil |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |

---

---

## Using the % Wildcard

The following SQL statement selects all customers with a City starting with "ber":

### Example

SELECT \* FROM Customers  
WHERE City LIKE 'ber%';

The following SQL statement selects all customers with a City containing the
pattern "es":

### Example

SELECT \* FROM Customers  
WHERE City LIKE '%es%';

---

## Using the \_ Wildcard

The following SQL statement selects all customers with a City starting with any character, followed by "ondon":

### Example

SELECT \* FROM Customers  
WHERE City LIKE '\_ondon';

The following SQL statement selects all customers with a City starting with
"L", followed by any character, followed by "n", followed by any character, followed by "on":

### Example

SELECT \* FROM Customers  
WHERE City LIKE 'L\_n\_on';



---

# MySQL IN Operator

---

## The MySQL IN Operator

The `IN` operator allows you to specify multiple values in a `WHERE` clause.

The `IN` operator is a shorthand for multiple `OR` conditions.

### IN Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE *column\_name* IN (*value1*, *value2*, ...);

or:

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE *column\_name* IN (*SELECT STATEMENT*);

---

## Demo Database

The table below shows the complete "Customers" table from the Northwind sample database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |
| 6 | Blauer See Delikatessen | Hanna Moos | Forsterstr. 57 | Mannheim | 68306 | Germany |
| 7 | Blondel pÃ¨re et fils | FrÃ©dÃ©rique Citeaux | 24, place KlÃ©ber | Strasbourg | 67000 | France |
| 8 | BÃ³lido Comidas preparadas | MartÃ­n Sommer | C/ Araquil, 67 | Madrid | 28023 | Spain |
| 9 | Bon app' | Laurence Lebihans | 12, rue des Bouchers | Marseille | 13008 | France |
| 10 | Bottom-Dollar Marketse | Elizabeth Lincoln | 23 Tsawassen Blvd. | Tsawassen | T2F 8M4 | Canada |
| 11 | B's Beverages | Victoria Ashworth | Fauntleroy Circus | London | EC2 5NT | UK |
| 12 | Cactus Comidas para llevar | Patricio Simpson | Cerrito 333 | Buenos Aires | 1010 | Argentina |
| 13 | Centro comercial Moctezuma | Francisco Chang | Sierras de Granada 9993 | MÃ©xico D.F. | 05022 | Mexico |
| 14 | Chop-suey Chinese | Yang Wang | Hauptstr. 29 | Bern | 3012 | Switzerland |
| 15 | ComÃ©rcio Mineiro | Pedro Afonso | Av. dos LusÃ­adas, 23 | SÃ£o Paulo | 05432-043 | Brazil |
| 16 | Consolidated Holdings | Elizabeth Brown | Berkeley Gardens 12 Brewery | London | WX1 6LT | UK |
| 17 | Drachenblut Delikatessend | Sven Ottlieb | Walserweg 21 | Aachen | 52066 | Germany |
| 18 | Du monde entier | Janine Labrune | 67, rue des Cinquante Otages | Nantes | 44000 | France |
| 19 | Eastern Connection | Ann Devon | 35 King George | London | WX3 6FW | UK |
| 20 | Ernst Handel | Roland Mendel | Kirchgasse 6 | Graz | 8010 | Austria |
| 21 | Familia Arquibaldo | Aria Cruz | Rua OrÃ³s, 92 | SÃ£o Paulo | 05442-030 | Brazil |
| 22 | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel | C/ Moralzarzal, 86 | Madrid | 28034 | Spain |
| 23 | Folies gourmandes | Martine RancÃ© | 184, chaussÃ©e de Tournai | Lille | 59000 | France |
| 24 | Folk och fÃ¤ HB | Maria Larsson | Ãkergatan 24 | BrÃ¤cke | S-844 67 | Sweden |
| 25 | Frankenversand | Peter Franken | Berliner Platz 43 | MÃ¼nchen | 80805 | Germany |
| 26 | France restauration | Carine Schmitt | 54, rue Royale | Nantes | 44000 | France |
| 27 | Franchi S.p.A. | Paolo Accorti | Via Monte Bianco 34 | Torino | 10100 | Italy |
| 28 | Furia Bacalhau e Frutos do Mar | Lino Rodriguez | Jardim das rosas n. 32 | Lisboa | 1675 | Portugal |
| 29 | GalerÃ­a del gastrÃ³nomo | Eduardo Saavedra | Rambla de CataluÃ±a, 23 | Barcelona | 08022 | Spain |
| 30 | Godos Cocina TÃ­pica | JosÃ© Pedro Freyre | C/ Romero, 33 | Sevilla | 41101 | Spain |
| 31 | Gourmet Lanchonetes | AndrÃ© Fonseca | Av. Brasil, 442 | Campinas | 04876-786 | Brazil |
| 32 | Great Lakes Food Market | Howard Snyder | 2732 Baker Blvd. | Eugene | 97403 | USA |
| 33 | GROSELLA-Restaurante | Manuel Pereira | 5Âª Ave. Los Palos Grandes | Caracas | 1081 | Venezuela |
| 34 | Hanari Carnes | Mario Pontes | Rua do PaÃ§o, 67 | Rio de Janeiro | 05454-876 | Brazil |
| 35 | HILARIÃN-Abastos | Carlos HernÃ¡ndez | Carrera 22 con Ave. Carlos Soublette #8-35 | San CristÃ³bal | 5022 | Venezuela |
| 36 | Hungry Coyote Import Store | Yoshi Latimer | City Center Plaza 516 Main St. | Elgin | 97827 | USA |
| 37 | Hungry Owl All-Night Grocers | Patricia McKenna | 8 Johnstown Road | Cork |  | Ireland |
| 38 | Island Trading | Helen Bennett | Garden House Crowther Way | Cowes | PO31 7PJ | UK |
| 39 | KÃ¶niglich Essen | Philip Cramer | Maubelstr. 90 | Brandenburg | 14776 | Germany |
| 40 | La corne d'abondance | Daniel Tonini | 67, avenue de l'Europe | Versailles | 78000 | France |
| 41 | La maison d'Asie | Annette Roulet | 1 rue Alsace-Lorraine | Toulouse | 31000 | France |
| 42 | Laughing Bacchus Wine Cellars | Yoshi Tannamuri | 1900 Oak St. | Vancouver | V3F 2K1 | Canada |
| 43 | Lazy K Kountry Store | John Steel | 12 Orchestra Terrace | Walla Walla | 99362 | USA |
| 44 | Lehmanns Marktstand | Renate Messner | Magazinweg 7 | Frankfurt a.M. | 60528 | Germany |
| 45 | Let's Stop N Shop | Jaime Yorres | 87 Polk St. Suite 5 | San Francisco | 94117 | USA |
| 46 | LILA-Supermercado | Carlos GonzÃ¡lez | Carrera 52 con Ave. BolÃ­var #65-98 Llano Largo | Barquisimeto | 3508 | Venezuela |
| 47 | LINO-Delicateses | Felipe Izquierdo | Ave. 5 de Mayo Porlamar | I. de Margarita | 4980 | Venezuela |
| 48 | Lonesome Pine Restaurant | Fran Wilson | 89 Chiaroscuro Rd. | Portland | 97219 | USA |
| 49 | Magazzini Alimentari Riuniti | Giovanni Rovelli | Via Ludovico il Moro 22 | Bergamo | 24100 | Italy |
| 50 | Maison Dewey | Catherine Dewey | Rue Joseph-Bens 532 | Bruxelles | B-1180 | Belgium |
| 51 | MÃ¨re Paillarde | Jean FresniÃ¨re | 43 rue St. Laurent | MontrÃ©al | H1J 1C3 | Canada |
| 52 | Morgenstern Gesundkost | Alexander Feuer | Heerstr. 22 | Leipzig | 04179 | Germany |
| 53 | North/South | Simon Crowther | South House 300 Queensbridge | London | SW7 1RZ | UK |
| 54 | OcÃ©ano AtlÃ¡ntico Ltda. | Yvonne Moncada | Ing. Gustavo Moncada 8585 Piso 20-A | Buenos Aires | 1010 | Argentina |
| 55 | Old World Delicatessen | Rene Phillips | 2743 Bering St. | Anchorage | 99508 | USA |
| 56 | Ottilies KÃ¤seladen | Henriette Pfalzheim | Mehrheimerstr. 369 | KÃ¶ln | 50739 | Germany |
| 57 | Paris spÃ©cialitÃ©s | Marie Bertrand | 265, boulevard Charonne | Paris | 75012 | France |
| 58 | Pericles Comidas clÃ¡sicas | Guillermo FernÃ¡ndez | Calle Dr. Jorge Cash 321 | MÃ©xico D.F. | 05033 | Mexico |
| 59 | Piccolo und mehr | Georg Pipps | Geislweg 14 | Salzburg | 5020 | Austria |
| 60 | Princesa Isabel Vinhoss | Isabel de Castro | Estrada da saÃºde n. 58 | Lisboa | 1756 | Portugal |
| 61 | Que DelÃ­cia | Bernardo Batista | Rua da Panificadora, 12 | Rio de Janeiro | 02389-673 | Brazil |
| 62 | Queen Cozinha | LÃºcia Carvalho | Alameda dos CanÃ rios, 891 | SÃ£o Paulo | 05487-020 | Brazil |
| 63 | QUICK-Stop | Horst Kloss | TaucherstraÃe 10 | Cunewalde | 01307 | Germany |
| 64 | Rancho grande | Sergio GutiÃ©rrez | Av. del Libertador 900 | Buenos Aires | 1010 | Argentina |
| 65 | Rattlesnake Canyon Grocery | Paula Wilson | 2817 Milton Dr. | Albuquerque | 87110 | USA |
| 66 | Reggiani Caseifici | Maurizio Moroni | Strada Provinciale 124 | Reggio Emilia | 42100 | Italy |
| 67 | Ricardo Adocicados | Janete Limeira | Av. Copacabana, 267 | Rio de Janeiro | 02389-890 | Brazil |
| 68 | Richter Supermarkt | Michael Holz | Grenzacherweg 237 | GenÃ¨ve | 1203 | Switzerland |
| 69 | Romero y tomillo | Alejandra Camino | Gran VÃ­a, 1 | Madrid | 28001 | Spain |
| 70 | SantÃ© Gourmet | Jonas Bergulfsen | Erling Skakkes gate 78 | Stavern | 4110 | Norway |
| 71 | Save-a-lot Markets | Jose Pavarotti | 187 Suffolk Ln. | Boise | 83720 | USA |
| 72 | Seven Seas Imports | Hari Kumar | 90 Wadhurst Rd. | London | OX15 4NB | UK |
| 73 | Simons bistro | Jytte Petersen | VinbÃ¦ltet 34 | KÃ¸benhavn | 1734 | Denmark |
| 74 | SpÃ©cialitÃ©s du monde | Dominique Perrier | 25, rue Lauriston | Paris | 75016 | France |
| 75 | Split Rail Beer & Ale | Art Braunschweiger | P.O. Box 555 | Lander | 82520 | USA |
| 76 | SuprÃªmes dÃ©lices | Pascale Cartrain | Boulevard Tirou, 255 | Charleroi | B-6000 | Belgium |
| 77 | The Big Cheese | Liz Nixon | 89 Jefferson Way Suite 2 | Portland | 97201 | USA |
| 78 | The Cracker Box | Liu Wong | 55 Grizzly Peak Rd. | Butte | 59801 | USA |
| 79 | Toms SpezialitÃ¤ten | Karin Josephs | Luisenstr. 48 | MÃ¼nster | 44087 | Germany |
| 80 | Tortuga Restaurante | Miguel Angel Paolino | Avda. Azteca 123 | MÃ©xico D.F. | 05033 | Mexico |
| 81 | TradiÃ§Ã£o Hipermercados | Anabela Domingues | Av. InÃªs de Castro, 414 | SÃ£o Paulo | 05634-030 | Brazil |
| 82 | Trail's Head Gourmet Provisioners | Helvetius Nagy | 722 DaVinci Blvd. | Kirkland | 98034 | USA |
| 83 | Vaffeljernet | Palle Ibsen | SmagslÃ¸get 45 | Ãrhus | 8200 | Denmark |
| 84 | Victuailles en stock | Mary Saveley | 2, rue du Commerce | Lyon | 69004 | France |
| 85 | Vins et alcools Chevalier | Paul Henriot | 59 rue de l'Abbaye | Reims | 51100 | France |
| 86 | Die Wandernde Kuh | Rita MÃ¼ller | Adenauerallee 900 | Stuttgart | 70563 | Germany |
| 87 | Wartian Herkku | Pirkko Koskitalo | Torikatu 38 | Oulu | 90110 | Finland |
| 88 | Wellington Importadora | Paula Parente | Rua do Mercado, 12 | Resende | 08737-363 | Brazil |
| 89 | White Clover Markets | Karl Jablonski | 305 - 14th Ave. S. Suite 3B | Seattle | 98128 | USA |
| 90 | Wilman Kala | Matti Karttunen | Keskuskatu 45 | Helsinki | 21240 | Finland |
| 91 | Wolski | Zbyszek | ul. Filtrowa 68 | Walla | 01-012 | Poland |

---

---

## IN Operator Examples

The following SQL statement selects all customers that are located in "Germany", "France"
or "UK":

### Example

SELECT \* FROM Customers  
WHERE Country IN ('Germany', 'France', 'UK');

The following SQL statement selects all customers that are NOT located in "Germany", "France" or "UK":

### Example

SELECT \* FROM Customers  
WHERE Country NOT IN ('Germany', 'France', 'UK');

The following SQL statement selects all customers that are from the same
countries as the suppliers:

### Example

SELECT \* FROM Customers  
WHERE Country IN (SELECT Country FROM Suppliers);



---

# MySQL BETWEEN Operator

---

## The MySQL BETWEEN Operator

The `BETWEEN` operator selects values within a given range. The values can be numbers, text, or dates.

The `BETWEEN` operator is inclusive: begin and end values are included.

### BETWEEN Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE *column\_name* BETWEEN *value1* AND *value2;*

---

## Demo Database

Below is a selection from the "Products" table in the Northwind
sample database:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| --- | --- | --- | --- | --- | --- |
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 1 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 1 | 2 | 36 boxes | 21.35 |

---

## BETWEEN Example

The following SQL statement selects all products with a price between 10 and 20:

### Example

SELECT \* FROM Products  
WHERE Price BETWEEN 10 AND 20;

---

---

## NOT BETWEEN Example

To display the products outside the range of the previous example, use `NOT BETWEEN`:

### Example

SELECT \* FROM Products  
WHERE Price NOT BETWEEN 10 AND 20;

---

## BETWEEN with IN Example

The following SQL statement selects all products with a price between 10 and
20. In addition; do not show products with a CategoryID of 1,2, or 3:

### Example

SELECT \* FROM Products  
WHERE Price BETWEEN 10 AND 20  
AND CategoryID NOT IN (1,2,3);

---

## BETWEEN Text Values Example

The following SQL statement selects all products with a ProductName between "Carnarvon
Tigers" and "Mozzarella di Giovanni":

### Example

SELECT \* FROM Products  
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella
di Giovanni'  
ORDER BY ProductName;

The following SQL statement selects all products with a ProductName between "Carnarvon
Tigers" and "Chef Anton's Cajun Seasoning":

### Example

SELECT \* FROM Products  
WHERE ProductName BETWEEN "Carnarvon Tigers" AND
"Chef Anton's Cajun Seasoning"  
ORDER BY ProductName;

---

## NOT BETWEEN Text Values Example

The following SQL statement selects all products with a ProductName not
between "Carnarvon
Tigers" and "Mozzarella di Giovanni":

### Example

SELECT \* FROM Products  
WHERE ProductName NOT BETWEEN 'Carnarvon Tigers' AND 'Mozzarella
di Giovanni'  
ORDER BY ProductName;

---

## Sample Table

Below is a selection from the "Orders" table in the Northwind
sample database:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10248 | 90 | 5 | 7/4/1996 | 3 |
| 10249 | 81 | 6 | 7/5/1996 | 1 |
| 10250 | 34 | 4 | 7/8/1996 | 2 |
| 10251 | 84 | 3 | 7/9/1996 | 1 |
| 10252 | 76 | 4 | 7/10/1996 | 2 |

---

## BETWEEN Dates Example

The following SQL statement selects all orders with an OrderDate between '01-July-1996' and
'31-July-1996':

### Example

SELECT \* FROM Orders  
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';



---

# MySQL Aliases

---

## MySQL Aliases

Aliases are used to give a table, or a column in a table, a temporary name.

Aliases are often used to make column names more readable.

An alias only exists for the duration of that query.

An alias is created with the `AS` keyword.

### Alias Column Syntax

SELECT *column\_name* AS *alias\_name*  
FROM *table\_name;*

### Alias Table Syntax

SELECT *column\_name(s)*  
FROM *table\_name* AS *alias\_name;*

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |

And a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10354 | 58 | 8 | 1996-11-14 | 3 |
| 10355 | 4 | 6 | 1996-11-15 | 1 |
| 10356 | 86 | 6 | 1996-11-18 | 2 |

---

---

## Alias for Columns Examples

The following SQL statement creates two aliases, one for the CustomerID
column and one for the CustomerName column:

### Example

SELECT CustomerID AS ID, CustomerName AS Customer  
FROM Customers;

The following SQL statement creates two aliases, one for the CustomerName
column and one for the ContactName column. **Note:** Single or double quotation marks
are required if the alias name contains spaces:

### Example

SELECT CustomerName AS Customer, ContactName AS "Contact Person"  
FROM Customers;

The following SQL statement creates an alias named "Address" that combine four columns (Address, PostalCode,
City and Country):

### Example

SELECT CustomerName, CONCAT\_WS(', ', Address, PostalCode, City, Country)
AS Address  
FROM Customers;

---

## Alias for Tables Example

The following SQL statement selects all the orders from the customer with
CustomerID=4 (Around the Horn). We use the "Customers" and "Orders" tables, and
give them the table aliases of "c" and "o" respectively (Here we use
aliases to make the SQL shorter):

### Example

SELECT o.OrderID, o.OrderDate, c.CustomerName  
FROM Customers AS c, Orders AS o  
WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;

The following SQL statement is the same as above, but without aliases:

### Example

SELECT Orders.OrderID, Orders.OrderDate, Customers.CustomerName  
FROM Customers, Orders  
WHERE Customers.CustomerName='Around the Horn' AND Customers.CustomerID=Orders.CustomerID;

Aliases can be useful when:

* There are more than one table involved in a query
* Functions are used in the query
* Column names are big or not very readable
* Two or more columns are combined together



---

# MySQL Joins

---

## MySQL Joining Tables

A `JOIN` clause is used to combine rows from two or more tables, based on
a related column between them.

Let's look at a selection from the "Orders" table:

| OrderID | CustomerID | OrderDate |
| --- | --- | --- |
| 10308 | 2 | 1996-09-18 |
| 10309 | 37 | 1996-09-19 |
| 10310 | 77 | 1996-09-20 |

Then, look at a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Country |
| --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mexico |

Notice that the "CustomerID" column in the "Orders" table refers to the
"CustomerID" in the "Customers" table. The relationship between the two tables above
is the "CustomerID" column.

Then, we can create the following SQL statement (that contains an `INNER JOIN`),
that selects records that have matching values in both tables:

### Example

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate  
FROM Orders  
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;

and it will produce something like this:

| OrderID | CustomerName | OrderDate |
| --- | --- | --- |
| 10308 | Ana Trujillo Emparedados y helados | 9/18/1996 |
| 10365 | Antonio Moreno TaquerÃ­a | 11/27/1996 |
| 10383 | Around the Horn | 12/16/1996 |
| 10355 | Around the Horn | 11/15/1996 |
| 10278 | Berglunds snabbkÃ¶p | 8/12/1996 |

---

---

## Supported Types of Joins in MySQL

* `INNER JOIN`: Returns records that have matching values in both tables
* `LEFT JOIN`: Returns all records from the left table, and the matched records from the right table
* `RIGHT JOIN`: Returns all records from the right table, and the matched records from the left table
* `CROSS JOIN`: Returns all records from both
  tables

![MySQL INNER JOIN](img_inner_join.png) 
![MySQL LEFT JOIN](img_left_join.png) 
![MySQL RIGHT JOIN](img_right_join.png) 
![MySQL CROSS JOIN](img_cross_join.png)



---

# MySQL INNER JOIN Keyword

---

## MySQL INNER JOIN Keyword

The `INNER JOIN` keyword selects records that have matching values in both tables.

![MySQL INNER JOIN](img_inner_join.png)

### INNER JOIN Syntax

SELECT *column\_name(s)*  
FROM *table1*  
INNER JOIN *table2* ON *table1.column\_name* = *table2.column\_name*;

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

And a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

---

---

## MySQL INNER JOIN Example

The following SQL statement selects all orders with customer information:

### Example

SELECT Orders.OrderID, Customers.CustomerName  
FROM Orders  
INNER JOIN
Customers ON Orders.CustomerID = Customers.CustomerID;

**Note:** The `INNER JOIN` keyword selects all rows from both
tables as long as there is a match between the columns. If there are records in the
"Orders" table that do not have matches in "Customers", these orders will not
be shown!

---

## JOIN Three Tables

The following SQL statement selects all orders with customer and shipper
information:

### Example

SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName  
FROM
((Orders  
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)  
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);



---

# MySQL LEFT JOIN Keyword

---

## MySQL LEFT JOIN Keyword

The `LEFT JOIN` keyword returns all records
from the left table (table1), and the matching records (if any) from the right table (table2).

![MySQL LEFT JOIN](img_left_join.png)

### LEFT JOIN Syntax

SELECT *column\_name(s)*  
FROM *table1*  
LEFT JOIN *table2* ON *table1.column\_name* = *table2.column\_name*;

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

And a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

---

## MySQL LEFT JOIN Example

The following SQL statement will select all customers, and any orders they might have:

### Example

SELECT Customers.CustomerName, Orders.OrderID  
FROM Customers  
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID  
ORDER BY Customers.CustomerName;

**Note:** The `LEFT JOIN` keyword returns all records from the
left table (Customers), even if there are no matches in the right table (Orders).



---

# MySQL RIGHT JOIN Keyword

---

## MySQL RIGHT JOIN Keyword

The `RIGHT JOIN` keyword returns all records from the right table (table2), and the
matching records (if any) from the left table (table1).

![MySQL RIGHT JOIN](img_right_join.png)

### RIGHT JOIN Syntax

SELECT *column\_name(s)*  
FROM *table1*  
RIGHT JOIN *table2* ON *table1.column\_name* = *table2.column\_name*;

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

And a selection from the "Employees" table:

| EmployeeID | LastName | FirstName | BirthDate | Photo |
| --- | --- | --- | --- | --- |
| 1 | Davolio | Nancy | 12/8/1968 | EmpID1.pic |
| 2 | Fuller | Andrew | 2/19/1952 | EmpID2.pic |
| 3 | Leverling | Janet | 8/30/1963 | EmpID3.pic |

---

## MySQL RIGHT JOIN Example

The following SQL statement will return all employees, and any orders they
might have placed:

### Example

SELECT Orders.OrderID, Employees.LastName, Employees.FirstName  
FROM Orders  
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID  
ORDER BY Orders.OrderID;

**Note:** The `RIGHT JOIN` keyword returns all records from the
right table (Employees), even if there are no matches in the left table
(Orders).

---



---

# MySQL CROSS JOIN Keyword

---

## SQL CROSS JOIN Keyword

The `CROSS JOIN` keyword returns all records
from both tables (table1 and table2).

![MySQL CROSS JOIN](img_cross_join.png)

### CROSS JOIN Syntax

SELECT *column\_name(s)*  
FROM *table1*  
CROSS JOIN *table2*;

**Note:** `CROSS JOIN` can potentially return very large
result-sets!

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

And a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

---

---

## MySQL CROSS JOIN Example

The following SQL statement selects all customers, and all orders:

### Example

SELECT Customers.CustomerName, Orders.OrderID  
FROM Customers  
CROSS JOIN Orders;

**Note:** The `CROSS JOIN` keyword returns all matching
records from both tables whether the other table matches or not. So, if
there are rows in "Customers" that do not have matches in "Orders", or if there
are rows in "Orders" that do not have matches in "Customers", those rows will be
listed as well.

If you add a `WHERE` clause (if table1 and
table2 has a relationship), the `CROSS JOIN` will
produce the same result as the `INNER JOIN` clause:

### Example

SELECT Customers.CustomerName, Orders.OrderID  
FROM Customers  
CROSS JOIN Orders  
WHERE Customers.CustomerID=Orders.CustomerID;



---

# MySQL Self Join

---

## MySQL Self Join

A self join is a regular join, but the table is joined with itself.

### Self Join Syntax

SELECT *column\_name(s)*  
FROM *table1 T1, table1 T2*  
WHERE *condition*;

*T1* and *T2* are different table aliases for the same table.

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

---

## MySQL Self Join Example

The following SQL statement matches customers that are from the same city:

### Example

SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2,
A.City  
FROM Customers A, Customers B  
WHERE A.CustomerID <> B.CustomerID  
AND A.City = B.City   
ORDER BY 

---

# MySQL UNION Operator

---

## The MySQL UNION Operator

The `UNION` operator is used to combine the result-set of two or more
`SELECT`
statements.

* Every `SELECT` statement within
  `UNION` must have the same number
  of columns
* The columns must also have similar data types
* The columns in
  every `SELECT` statement must also be in the same order

### UNION Syntax

SELECT *column\_name(s)* FROM *table1*  
UNION  
SELECT *column\_name(s)* FROM *table2*;

### UNION ALL Syntax

The `UNION` operator selects only distinct values by default. To allow
duplicate values, use `UNION ALL`:

SELECT *column\_name(s)* FROM *table1*  
UNION ALL  
SELECT *column\_name(s)* FROM *table2*;

**Note:** The column names in the result-set are usually equal to
the column names in the first `SELECT` statement.

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

And a selection from the "Suppliers" table:

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd. | Ann Arbor | 48104 | USA |

---

---

## SQL UNION Example

The following SQL statement returns the cities
(only distinct values) from both the "Customers" and the "Suppliers" table:

### Example

SELECT City FROM Customers  
UNION  
SELECT City FROM Suppliers  
ORDER BY City;

**Note:** If some customers or suppliers have the same city, each city will only be
listed once, because `UNION` selects only distinct values. Use
`UNION ALL` to also select
duplicate values!

---

## SQL UNION ALL Example

The following SQL statement returns the cities
(duplicate values also) from both the "Customers" and the "Suppliers" table:

### Example

SELECT City FROM Customers  
UNION ALL  
SELECT City FROM Suppliers  
ORDER BY City;

---

## SQL UNION With WHERE

The following SQL statement returns the German cities
(only distinct values) from both the "Customers" and the "Suppliers" table:

### Example

SELECT City, Country FROM Customers  
WHERE Country='Germany'  
UNION  
SELECT City, Country FROM Suppliers  
WHERE Country='Germany'  
ORDER BY City;

---

## SQL UNION ALL With WHERE

The following SQL statement returns the German cities (duplicate values also) from
both the "Customers" and the "Suppliers" table:

### Example

SELECT City, Country FROM Customers  
WHERE Country='Germany'  
UNION ALL  
SELECT City, Country FROM Suppliers  
WHERE Country='Germany'  
ORDER BY City;

---

## Another UNION Example

The following SQL statement lists all customers and suppliers:

### Example

SELECT 'Customer' AS Type, ContactName, City, Country  
FROM Customers  
UNION  
SELECT 'Supplier', ContactName, City, Country  
FROM Suppliers;

Notice the "AS Type" above - it is an alias. [SQL
Aliases](mysql_alias.asp) are used to give a table or a column a temporary name.
An alias only exists for the duration of the query. So, here we have created a
temporary column named "Type", that list whether the contact person is a
"Customer" or a "Supplier".



---

# MySQL GROUP BY Statement

---

## The MySQL GROUP BY Statement

The `GROUP BY` statement groups rows that have the same values into summary
rows, like "find the number of customers in each country".

The `GROUP BY` statement is often used with aggregate functions (`COUNT()`,
`MAX()`,
`MIN()`, `SUM()`,
`AVG()`) to group the result-set by one or more columns.

### GROUP BY Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE *condition*  
GROUP BY *column\_name(s)*ORDER BY *column\_name(s);*

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample
database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

---

## MySQL GROUP BY Examples

The following SQL statement lists the number of customers in each country:

### Example

SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country;

The following SQL statement lists the number of customers in each country,
sorted high to low:

### Example

SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country  
ORDER BY COUNT(CustomerID) DESC;

---

## Demo Database

Below is a selection from the "Orders" table in the Northwind sample database:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10248 | 90 | 5 | 1996-07-04 | 3 |
| 10249 | 81 | 6 | 1996-07-05 | 1 |
| 10250 | 34 | 4 | 1996-07-08 | 2 |

And a selection from the "Shippers" table:

| ShipperID | ShipperName |
| --- | --- |
| 1 | Speedy Express |
| 2 | United Package |
| 3 | Federal Shipping |

---

## GROUP BY With JOIN Example

The following SQL statement lists the number of orders sent by each shipper:

### Example

SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders FROM
Orders  
LEFT JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID  
GROUP BY ShipperName;



---

# MySQL HAVING Clause

---

## The MySQL HAVING Clause

The `HAVING` clause was added to SQL because the
`WHERE` keyword cannot be
used with aggregate functions.

### HAVING Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE *condition*  
GROUP BY *column\_name(s)*HAVING *condition*ORDER BY *column\_name(s);*

---

## Demo Database

Below is a selection from the "Customers" table in the Northwind sample
database:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |
| 4 | Around the Horn | Thomas Hardy | 120 Hanover Sq. | London | WA1 1DP | UK |
| 5 | Berglunds snabbkÃ¶p | Christina Berglund | BerguvsvÃ¤gen 8 | LuleÃ¥ | S-958 22 | Sweden |

---

## MySQL HAVING Examples

The following SQL statement lists the number of customers in each country.
Only include countries with more than 5 customers:

### Example

SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country  
HAVING COUNT(CustomerID) > 5;

The following SQL statement lists the number of customers in each country,
sorted high to low (Only include countries with more than 5 customers):

### Example

SELECT COUNT(CustomerID), Country  
FROM Customers  
GROUP BY Country  
HAVING COUNT(CustomerID)
> 5  
ORDER BY COUNT(CustomerID) DESC;

---

---

## Demo Database

Below is a selection from the "Orders" table in the Northwind sample database:

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| --- | --- | --- | --- | --- |
| 10248 | 90 | 5 | 1996-07-04 | 3 |
| 10249 | 81 | 6 | 1996-07-05 | 1 |
| 10250 | 34 | 4 | 1996-07-08 | 2 |

And a selection from the "Employees" table:

| EmployeeID | LastName | FirstName | BirthDate | Photo | Notes |
| --- | --- | --- | --- | --- | --- |
| 1 | Davolio | Nancy | 1968-12-08 | EmpID1.pic | Education includes a BA.... |
| 2 | Fuller | Andrew | 1952-02-19 | EmpID2.pic | Andrew received his BTS.... |
| 3 | Leverling | Janet | 1963-08-30 | EmpID3.pic | Janet has a BS degree.... |

---

## More HAVING Examples

The following SQL statement lists the employees that have registered more
than 10 orders:

### Example

SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders  
FROM
(Orders  
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)  
GROUP BY LastName  
HAVING COUNT(Orders.OrderID) > 10;

The following SQL statement lists if the employees "Davolio" or "Fuller" have registered
more than 25 orders:

### Example

SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders  
FROM Orders  
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID  
WHERE LastName = 'Davolio' OR LastName = 'Fuller'  
GROUP BY LastName  
HAVING
COUNT(Orders.OrderID) > 25;



---

# MySQL EXISTS Operator

---

## The MySQL EXISTS Operator

The `EXISTS` operator is used to test for the existence of any record in a subquery.

The `EXISTS` operator returns TRUE if the subquery returns one or more records.

### EXISTS Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE
EXISTS  
(SELECT *column\_name* FROM *table\_name* WHERE
*condition*);

---

## Demo Database

Below is a selection from the "Products" table in the Northwind sample database:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| --- | --- | --- | --- | --- | --- |
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 2 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 2 | 2 | 36 boxes | 21.35 |

And a selection from the "Suppliers" table:

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd. | Ann Arbor | 48104 | USA |
| 4 | Tokyo Traders | Yoshi Nagase | 9-8 Sekimai Musashino-shi | Tokyo | 100 | Japan |

---

---

## MySQL EXISTS Examples

The following SQL statement returns TRUE and lists the suppliers with a product price less than 20:

### Example

SELECT SupplierName  
FROM Suppliers  
WHERE EXISTS (SELECT ProductName FROM
Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);

The following SQL statement returns TRUE and lists the suppliers with a product price
equal to 22:

### Example

SELECT SupplierName  
FROM Suppliers  
WHERE EXISTS (SELECT ProductName FROM
Products WHERE Products.SupplierID = Suppliers.supplierID AND Price = 22);



---

# MySQL ANY and ALL Operators

---

## The MySQL ANY and ALL Operators

The `ANY` and `ALL` operators allow you to perform a comparison between a single
column value and a range of other values.

---

## The ANY Operator

The `ANY` operator:

* returns a boolean value as a result
* returns TRUE if ANY of the subquery values meet the condition

`ANY` means that the condition will be true if the operation is true for
any of the values in the range.

### ANY Syntax

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE
*column\_name operator* ANY  
  (SELECT *column\_name* FROM *table\_name* WHERE
*condition*);

**Note:** The *operator* must be a standard comparison
operator (=, <>, !=, >, >=, <, or <=).

---

## The ALL Operator

The `ALL` operator:

* returns a boolean value as a result
* returns TRUE if ALL of the subquery values meet the condition
* is used with `SELECT`,
  `WHERE` and `HAVING` statements

`ALL` means that the condition will be true only if the operation is true
for all values in the range.

### ALL Syntax With SELECT

SELECT ALL *column\_name(s)*  
FROM *table\_name*  
WHERE
*condition*;

### ALL Syntax With WHERE or HAVING

SELECT *column\_name(s)*  
FROM *table\_name*  
WHERE
*column\_name operator* ALL  
  (SELECT *column\_name* FROM *table\_name* WHERE *condition*);

**Note:** The *operator* must be a standard comparison
operator (=, <>, !=, >, >=, <, or <=).

---

## Demo Database

Below is a selection from the **"Products"** table in the Northwind sample database:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| --- | --- | --- | --- | --- | --- |
| 1 | Chais | 1 | 1 | 10 boxes x 20 bags | 18 |
| 2 | Chang | 1 | 1 | 24 - 12 oz bottles | 19 |
| 3 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 4 | Chef Anton's Cajun Seasoning | 2 | 2 | 48 - 6 oz jars | 22 |
| 5 | Chef Anton's Gumbo Mix | 2 | 2 | 36 boxes | 21.35 |
| 6 | Grandma's Boysenberry Spread | 3 | 2 | 12 - 8 oz jars | 25 |
| 7 | Uncle Bob's Organic Dried Pears | 3 | 7 | 12 - 1 lb pkgs. | 30 |
| 8 | Northwoods Cranberry Sauce | 3 | 2 | 12 - 12 oz jars | 40 |
| 9 | Mishi Kobe Niku | 4 | 6 | 18 - 500 g pkgs. | 97 |

And a selection from the **"OrderDetails"** table:

| OrderDetailID | OrderID | ProductID | Quantity |
| --- | --- | --- | --- |
| 1 | 10248 | 11 | 12 |
| 2 | 10248 | 42 | 10 |
| 3 | 10248 | 72 | 5 |
| 4 | 10249 | 14 | 9 |
| 5 | 10249 | 51 | 40 |
| 6 | 10250 | 41 | 10 |
| 7 | 10250 | 51 | 35 |
| 8 | 10250 | 65 | 15 |
| 9 | 10251 | 22 | 6 |
| 10 | 10251 | 57 | 15 |

---

---

## SQL ANY Examples

The following SQL statement lists the ProductName if it
finds ANY records in the OrderDetails table has Quantity equal to 10 (this will
return TRUE because the Quantity column has some values of 10):

### Example

SELECT ProductName  
FROM Products  
WHERE ProductID = ANY  
  (SELECT ProductID  
  FROM OrderDetails  
  WHERE Quantity = 10);

The following SQL statement lists the ProductName if it
finds ANY records in the OrderDetails table has Quantity larger than 99 (this
will return TRUE because the Quantity column has some values larger than 99):

### Example

SELECT ProductName  
FROM Products  
WHERE ProductID = ANY  
  (SELECT ProductID  
 
FROM OrderDetails  
  WHERE Quantity > 99);

The following SQL statement lists the ProductName if it
finds ANY records in the OrderDetails table has Quantity larger than 1000 (this
will return FALSE because the Quantity column has no values larger than 1000):

### Example

SELECT ProductName  
FROM Products  
WHERE ProductID = ANY  
  (SELECT ProductID  
 
FROM OrderDetails  
  WHERE Quantity > 1000);

---

## SQL ALL Examples

The following SQL statement lists ALL the product names:

### Example

SELECT ALL ProductName  
FROM Products  
WHERE TRUE;

The following SQL statement lists the ProductName if ALL the records in the
OrderDetails table has Quantity equal to 10. This will of course return FALSE
because the Quantity column has many different values (not only the value of 10):

### Example

SELECT ProductName  
FROM Products  
WHERE ProductID = ALL  
  (SELECT ProductID  
  FROM OrderDetails  
  WHERE Quantity = 10);



---

# MySQL INSERT INTO SELECT Statement

---

## The MySQL INSERT INTO SELECT Statement

The `INSERT INTO SELECT` statement copies data from one table and
inserts it into another table.

The `INSERT INTO SELECT` statement requires that
the data types in source and target tables matches.

**Note:** The existing records in the target table are unaffected.

### INSERT INTO SELECT Syntax

Copy all columns from one table to another table:

INSERT INTO *table2*  
SELECT \* FROM *table1*WHERE *condition*;

Copy only some columns from one table into another table:

INSERT INTO *table2* (*column1*, *column2*, *column3*, ...)  
SELECT *column1*, *column2*, *column3*, ...  
 FROM *table1*  
WHERE *condition*;

---

## Demo Database

In this tutorial we will use the well-known Northwind sample database.

Below is a selection from the "Customers" table:

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la ConstituciÃ³n 2222 | MÃ©xico D.F. | 05021 | Mexico |
| 3 | Antonio Moreno TaquerÃ­a | Antonio Moreno | Mataderos 2312 | MÃ©xico D.F. | 05023 | Mexico |

And a selection from the "Suppliers" table:

| SupplierID | SupplierName | ContactName | Address | City | Postal Code | Country |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | Londona | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd. | Ann Arbor | 48104 | USA |

---

---

## MySQL INSERT INTO SELECT Examples

The following SQL statement copies "Suppliers" into "Customers" (the columns
that are not filled with data, will contain NULL):

### Example

INSERT INTO Customers (CustomerName,
City, Country)  
SELECT SupplierName, City, Country FROM Suppliers;

The following SQL statement copies "Suppliers" into "Customers" (fill all
columns):

### Example

INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode,
Country)  
SELECT SupplierName, ContactName, Address, City, PostalCode,
Country FROM Suppliers;

The following SQL statement copies only the German suppliers into "Customers":

### Example

INSERT INTO Customers (CustomerName,
City, Country)  
SELECT SupplierName, City, Country FROM Suppliers  
WHERE Country='Germany';



---

# MySQL CASE Statement

---

## The MySQL CASE Statement

The `CASE` statement goes through conditions and returns a value when the first condition is
met (like an if-then-else statement). So, once a condition is true, it will stop
reading and return the result. If no conditions are true, it returns
the value in the `ELSE` clause.

If there is no `ELSE` part and no conditions are true, it returns NULL.

## CASE Syntax

CASE  
    WHEN *condition1* THEN *result1*  
   
WHEN *condition2* THEN *result2*  
    WHEN
*conditionN* THEN *resultN*  
    ELSE *result*  
END;

---

## Demo Database

Below is a selection from the "OrderDetails" table in the Northwind sample database:

| OrderDetailID | OrderID | ProductID | Quantity |
| --- | --- | --- | --- |
| 1 | 10248 | 11 | 12 |
| 2 | 10248 | 42 | 10 |
| 3 | 10248 | 72 | 5 |
| 4 | 10249 | 14 | 9 |
| 5 | 10249 | 51 | 40 |

---

---

## MySQL CASE Examples

The following SQL goes through conditions and returns a value when the first condition is met:

### Example

SELECT OrderID, Quantity,  
CASE  
    WHEN Quantity > 30
THEN 'The quantity is greater than 30'  
    WHEN Quantity = 30 THEN 'The
quantity is 30'  
    ELSE 'The quantity is under 30'  
END AS QuantityText  
FROM OrderDetails;

The following SQL will order the customers by City. However, if City is NULL, then order by Country:

### Example

SELECT CustomerName, City, Country  
FROM Customers  
ORDER BY  
(CASE  
   
WHEN City IS NULL THEN Country  
    ELSE City  
END);



---

# MySQL NULL Functions

---

## MySQL IFNULL() and COALESCE() Functions

Look at the following "Products" table:

| P\_Id | ProductName | UnitPrice | UnitsInStock | UnitsOnOrder |
| --- | --- | --- | --- | --- |
| 1 | Jarlsberg | 10.45 | 16 | 15 |
| 2 | Mascarpone | 32.56 | 23 |  |
| 3 | Gorgonzola | 15.67 | 9 | 20 |

Suppose that the "UnitsOnOrder" column is optional, and may contain NULL values.

Look at the following SELECT statement:

SELECT ProductName, UnitPrice \* (UnitsInStock + UnitsOnOrder)  
FROM Products;

In the example above, if any of the "UnitsOnOrder" values are NULL, the result
will be NULL.

---

## MySQL IFNULL() Function

The MySQL `IFNULL()` function lets you
return an alternative value if an expression is NULL.

The example below returns 0 if the value is NULL:

SELECT ProductName, UnitPrice \* (UnitsInStock + IFNULL(UnitsOnOrder, 0))  
FROM Products;

---

## MySQL COALESCE() Function

Or we can use the `COALESCE()` function, like this:

SELECT ProductName, UnitPrice \* (UnitsInStock + COALESCE(UnitsOnOrder, 0))  
FROM Products;



---

# MySQL Comments

---

## MySQL Comments

Comments are used to explain sections of SQL statements, or to prevent execution
of SQL statements.

---

## Single Line Comments

Single line comments start with `--`.

Any text between -- and the end of the line will be ignored (will not be executed).

The following example uses a single-line comment as an explanation:

### Example

-- Select all:  
SELECT \* FROM Customers;

The following example uses a single-line comment to ignore the end of a line:

### Example

SELECT \* FROM Customers -- WHERE City='Berlin';

The following example uses a single-line comment to ignore a statement:

### Example

-- SELECT \* FROM Customers;  
SELECT \* FROM Products;

---

---

## Multi-line Comments

Multi-line comments start with `/*` and end with
`*/`.

Any text between /\* and \*/ will be ignored.

The following example uses a multi-line comment as an explanation:

### Example

/\*Select all the columns  
of all the records  
in the Customers table:\*/  
SELECT \* FROM Customers;

The following example uses a multi-line comment to ignore many statements:

### Example

/\*SELECT \* FROM Customers;  
SELECT \* FROM Products;  
SELECT \* FROM Orders;  
SELECT \* FROM Categories;\*/  
SELECT \* FROM Suppliers;

To ignore just a part of a statement, also use the /\* \*/ comment.

The following example uses a comment to ignore part of a line:

### Example

SELECT CustomerName, /\*City,\*/ Country FROM Customers;

The following example uses a comment to ignore part of a statement:

### Example

SELECT \* FROM Customers WHERE (CustomerName LIKE 'L%'  
OR CustomerName LIKE 'R%' /\*OR CustomerName LIKE 'S%'  
OR CustomerName LIKE 'T%'\*/ OR CustomerName LIKE 'W%')  
AND Country='USA'  
ORDER BY CustomerName;



---

# MySQL Operators

---

## MySQL Arithmetic Operators

| Operator | Description | Example |
| --- | --- | --- |
| + | Add | [Try it](trymysql.asp?filename=trysql_op_add) |
| - | Subtract | [Try it](trymysql.asp?filename=trysql_op_subtract) |
| \* | Multiply | [Try it](trymysql.asp?filename=trysql_op_multiply) |
| / | Divide | [Try it](trymysql.asp?filename=trysql_op_divide) |
| % | Modulo | [Try it](trymysql.asp?filename=trysql_op_modulo) |

---

## MySQL Bitwise Operators

| Operator | Description |
| --- | --- |
| & | Bitwise AND |
| | | Bitwise OR |
| ^ | Bitwise exclusive OR |

---

## MySQL Comparison Operators

| Operator | Description | Example |
| --- | --- | --- |
| = | Equal to | [Try it](trymysql.asp?filename=trysql_op_equal_to) |
| > | Greater than | [Try it](trymysql.asp?filename=trysql_op_greater_than) |
| < | Less than | [Try it](trymysql.asp?filename=trysql_op_less_than) |
| >= | Greater than or equal to | [Try it](trymysql.asp?filename=trysql_op_greater_than2) |
| <= | Less than or equal to | [Try it](trymysql.asp?filename=trysql_op_less_than2) |
| <> | Not equal to | [Try it](trymysql.asp?filename=trysql_op_not_equal_to) |

---

---

## MySQL Compound Operators

| Operator | Description |
| --- | --- |
| += | Add equals |
| -= | Subtract equals |
| \*= | Multiply equals |
| /= | Divide equals |
| %= | Modulo equals |
| &= | Bitwise AND equals |
| ^-= | Bitwise exclusive equals |
| |\*= | Bitwise OR equals |

---

## MySQL Logical Operators

| Operator | Description | Example |
| --- | --- | --- |
| ALL | TRUE if all of the subquery values meet the condition | [Try it](trymysql.asp?filename=trysql_op_all) |
| AND | TRUE if all the conditions separated by AND is TRUE | [Try it](trymysql.asp?filename=trysql_op_and) |
| ANY | TRUE if any of the subquery values meet the condition | [Try it](trymysql.asp?filename=trysql_op_any) |
| BETWEEN | TRUE if the operand is within the range of comparisons | [Try it](trymysql.asp?filename=trysql_op_between) |
| EXISTS | TRUE if the subquery returns one or more records | [Try it](trymysql.asp?filename=trysql_op_exists) |
| IN | TRUE if the operand is equal to one of a list of expressions | [Try it](trymysql.asp?filename=trysql_op_in) |
| LIKE | TRUE if the operand matches a pattern | [Try it](trymysql.asp?filename=trysql_op_like) |
| NOT | Displays a record if the condition(s) is NOT TRUE | [Try it](trymysql.asp?filename=trysql_op_not) |
| OR | TRUE if any of the conditions separated by OR is TRUE | [Try it](trymysql.asp?filename=trysql_op_or) |
| SOME | TRUE if any of the subquery values meet the condition | [Try it](trymysql.asp?filename=trysql_op_some) |



---

# MySQL CREATE DATABASE Statement

---

## The MySQL CREATE DATABASE Statement

The `CREATE DATABASE` statement is used to create a new SQL database.

### Syntax

CREATE DATABASE *databasename*;

---

## CREATE DATABASE Example

The following SQL statement creates a database called "testDB":

### Example

CREATE DATABASE testDB;

**Tip:** Make sure you have admin privilege before creating any database. Once a
database is created, you can check it in the list of databases with the
following SQL command: `SHOW DATABASES`;



---

# MySQL DROP DATABASE Statement

---

## The MySQL DROP DATABASE Statement

The `DROP DATABASE` statement is used to drop an existing SQL database.

### Syntax

DROP DATABASE *databasename*;

**Note:** Be careful before dropping a database. Deleting
a database will result in loss of complete information stored in the database!

---

## DROP DATABASE Example

The following SQL statement drops the existing database "testDB":

### Example

DROP DATABASE testDB;

**Tip:** Make sure you have admin privilege before dropping any database. Once a
database is dropped, you can check it in the list of databases with the
following SQL command: `SHOW DATABASES`;



---

# MySQL CREATE TABLE Statement

---

## The MySQL CREATE TABLE Statement

The `CREATE TABLE` statement is used to create a new table in a database.

### Syntax

CREATE TABLE *table\_name* (  
*column1 datatype*,  
*column2 datatype*,  
*column3 datatype*,  
  
....  
);

The column parameters specify the names of the columns of the table.

The datatype parameter specifies the type of data the column can hold (e.g. varchar, integer, date, etc.).

**Tip:** For an overview of the available data types, go to our complete [Data Types Reference](mysql_datatypes.asp).

---

## MySQL CREATE TABLE Example

The following example creates a table called "Persons" that contains five columns: PersonID, LastName, FirstName,
Address, and City:

### Example

CREATE TABLE Persons
(  
   
PersonID int,  
   
LastName varchar(255),  
   
FirstName varchar(255),  
   
Address varchar(255),  
   
City varchar(255)   
);

The PersonID column is of type int and will hold an integer.

The LastName, FirstName, Address, and City columns are of type varchar and will hold characters, and the maximum length for these fields
is 255 characters.

The empty "Persons" table will now look like this:

| PersonID | LastName | FirstName | Address | City |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

**Tip:** The empty "Persons" table can now be filled with data with the
SQL [INSERT INTO](mysql_insert.asp) statement.

---

---

## Create Table Using Another Table

A copy of an existing table can also be created using `CREATE TABLE`.

The new table gets the same column definitions. All columns or specific columns can be selected.

If you create a new table using an existing table, the new table will be filled with the existing values from the old table.

### Syntax

CREATE TABLE *new\_table\_name* AS  
   
SELECT *column1, column2,...*  
    FROM *existing\_table\_name*  
    WHERE ....;

The following SQL creates a new table called "TestTables" (which is
a copy of the "Customers" table):

### Example

CREATE TABLE TestTable AS  
SELECT customername, contactname  
FROM
customers;



---

# MySQL DROP TABLE Statement

---

## The MySQL DROP TABLE Statement

The `DROP TABLE` statement is used to drop an existing table in a database.

### Syntax

DROP TABLE *table\_name*;

**Note****:** Be careful before dropping a table. Deleting a
table will result in loss of complete information stored in the table!

---

## MySQL DROP TABLE Example

The following SQL statement drops the existing table "Shippers":

### Example

DROP TABLE Shippers;

---

## MySQL TRUNCATE TABLE

The `TRUNCATE TABLE` statement is used to delete the data inside a table, but
not the table itself.

### Syntax

TRUNCATE TABLE *table\_name*;



---

# MySQL ALTER TABLE Statement

---

## MySQL ALTER TABLE Statement

The `ALTER TABLE` statement is used to add, delete, or modify columns in an existing table.

The `ALTER TABLE` statement is also used to add and drop various constraints on
an existing table.

---

## ALTER TABLE - ADD Column

To add a column in a table, use the following syntax:

ALTER TABLE *table\_name*  
ADD *column\_name datatype*;

The following SQL adds an "Email" column to the "Customers" table:

### Example

ALTER TABLE Customers  
ADD Email varchar(255);

---

## ALTER TABLE - DROP COLUMN

To delete a column in a table, use the following syntax (notice that some
database systems don't allow deleting a column):

ALTER TABLE *table\_name*  
DROP COLUMN *column\_name*;

The following SQL deletes the "Email" column from the "Customers" table:

### Example

ALTER TABLE Customers  
DROP COLUMN Email;

---

## ALTER TABLE - MODIFY COLUMN

To change the data type of a column in a table, use the following syntax:

ALTER TABLE *table\_name*  
MODIFY COLUMN *column\_name datatype*;

---

---

## MySQL ALTER TABLE Example

Look at the "Persons" table:

| ID | LastName | FirstName | Address | City |
| --- | --- | --- | --- | --- |
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |

Now we want to add a column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

### Example

ALTER TABLE Persons  
ADD DateOfBirth date;

Notice that the new column, "DateOfBirth", is of type date and is going to hold a
date. The data type specifies what type of data the column can hold. For a complete
reference of all the data types available in MySQL,
go to our complete [Data Types reference](mysql_datatypes.asp).

The "Persons" table will now look like this:

| ID | LastName | FirstName | Address | City | DateOfBirth |
| --- | --- | --- | --- | --- | --- |
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |  |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |  |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |  |

---

## Change Data Type Example

Now we want to change the data type of the column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

### Example

ALTER TABLE Persons  
MODIFY COLUMN DateOfBirth year;

Notice that the "DateOfBirth" column is now of type year and is going to hold a year in a two- or four-digit format.

---

## DROP COLUMN Example

Next, we want to delete the column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

### Example

ALTER TABLE Persons  
DROP COLUMN DateOfBirth;

The "Persons" table will now look like this:

| ID | LastName | FirstName | Address | City |
| --- | --- | --- | --- | --- |
| 1 | Hansen | Ola | Timoteivn 10 | Sandnes |
| 2 | Svendson | Tove | Borgvn 23 | Sandnes |
| 3 | Pettersen | Kari | Storgt 20 | Stavanger |



---

# MySQL Constraints

---

SQL constraints are used to specify rules for data in a table.

---

## Create Constraints

Constraints can be specified when the table is created with the
`CREATE TABLE` statement, or after the table is created
with the `ALTER TABLE` statement.

### Syntax

CREATE TABLE *table\_name* (  
*column1 datatype* *constraint*,  
*column2 datatype* *constraint*,  
*column3 datatype* *constraint*,  
   
....  
);

---

## MySQL Constraints

SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This
ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action,
the action is aborted.

Constraints can be column level or table level. Column level constraints
apply to a column, and table level constraints apply to the whole table.

The following constraints are commonly used in SQL:

* `NOT NULL` - Ensures that a column cannot have a NULL value
* `UNIQUE` - Ensures that all values in a column are
  different
* `PRIMARY KEY` - A combination of a
  `NOT NULL` and `UNIQUE`.
  Uniquely identifies each row in a table
* `FOREIGN KEY`
  - Prevents actions that would destroy links between tables
* `CHECK` - Ensures that
  the values in a column satisfies a specific condition
* `DEFAULT` - Sets a default value for a column
  if no value
  is specified
* `CREATE INDEX` - Used to create and retrieve data from the database
  very quickly



---

# MySQL NOT NULL Constraint

---

## MySQL NOT NULL Constraint

By default, a column can hold NULL values.

The `NOT NULL` constraint enforces a column to NOT accept NULL values.

This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.

---

## NOT NULL on CREATE TABLE

The following SQL ensures that the "ID", "LastName", and
"FirstName" columns
will NOT accept NULL values when the "Persons" table is created:

### Example

CREATE TABLE Persons (  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
    FirstName varchar(255)
NOT NULL,  
    Age int  
);

---

## NOT NULL on ALTER TABLE

To create a `NOT NULL` constraint on the "Age" column when the "Persons" table is already created, use the following SQL:

### Example

ALTER TABLE Persons  
MODIFY Age int NOT NULL;



---

# MySQL UNIQUE Constraint

---

## MySQL UNIQUE Constraint

The `UNIQUE` constraint ensures that all values in a column are different.

Both the `UNIQUE` and
`PRIMARY KEY` constraints provide a guarantee for uniqueness for a column or set of columns.

A `PRIMARY KEY` constraint automatically has a
`UNIQUE` constraint.

However, you can have many `UNIQUE` constraints per table, but only one
`PRIMARY KEY` constraint per table.

---

## UNIQUE Constraint on CREATE TABLE

The following SQL creates a `UNIQUE` constraint on the "ID" column when the "Persons" table is created:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
UNIQUE (ID)  
);

To name a `UNIQUE` constraint, and to define a
`UNIQUE` constraint on multiple columns, use the following SQL syntax:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
CONSTRAINT UC\_Person UNIQUE (ID,LastName)  
);

---

---

## UNIQUE Constraint on ALTER TABLE

To create a `UNIQUE` constraint on the "ID" column when the table is already created, use the following SQL:

ALTER TABLE Persons  
ADD UNIQUE (ID);

To name a `UNIQUE` constraint, and to define a
`UNIQUE` constraint on multiple columns, use the following SQL syntax:

ALTER TABLE Persons  
ADD CONSTRAINT UC\_Person UNIQUE (ID,LastName);

---

## DROP a UNIQUE Constraint

To drop a `UNIQUE` constraint, use the following SQL:

ALTER TABLE Persons  
DROP INDEX UC\_Person;



---

# MySQL PRIMARY KEY Constraint

---

## MySQL PRIMARY KEY Constraint

The `PRIMARY KEY` constraint uniquely identifies each record in a table.

Primary keys must contain UNIQUE values, and cannot contain NULL values.

A table can have only ONE primary key; and in the table, this primary key can
consist of single or multiple columns (fields).

---

## PRIMARY KEY on CREATE TABLE

The following SQL creates a `PRIMARY KEY` on the "ID" column when the "Persons" table is created:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
PRIMARY KEY (ID)  
);

To allow naming of a `PRIMARY KEY` constraint, and for defining a
`PRIMARY KEY` constraint on multiple columns, use the following SQL syntax:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
CONSTRAINT PK\_Person PRIMARY KEY (ID,LastName)  
);

**Note:** In the example above there is only ONE `PRIMARY KEY` (PK\_Person).
However, the VALUE of the primary key is made up of TWO COLUMNS (ID + LastName).

---

---

## PRIMARY KEY on ALTER TABLE

To create a `PRIMARY KEY` constraint on the "ID" column when the table is already created, use the following SQL:

ALTER TABLE Persons  
ADD PRIMARY KEY (ID);

To allow naming of a `PRIMARY KEY` constraint, and for defining a
`PRIMARY KEY` constraint on multiple columns, use the following SQL syntax:

ALTER TABLE Persons  
ADD CONSTRAINT PK\_Person PRIMARY KEY (ID,LastName);

**Note:** If you use `ALTER TABLE` to add a primary key, the primary key column(s) must
have been declared to not contain NULL values (when the table was first created).

---

## DROP a PRIMARY KEY Constraint

To drop a `PRIMARY KEY` constraint, use the following SQL:

ALTER TABLE Persons  
DROP PRIMARY KEY;



---

# MySQL FOREIGN KEY Constraint

---

## MySQL FOREIGN KEY Constraint

The `FOREIGN KEY` constraint is used to prevent actions that would destroy links between tables.

A `FOREIGN KEY` is a field (or collection of fields) in one table, that refers to
the `PRIMARY KEY` in another table.

The table with the foreign key is called the child table, and the table
with the primary key is called the referenced or parent table.

Look at the following two tables:

### Persons Table

| PersonID | LastName | FirstName | Age |
| --- | --- | --- | --- |
| 1 | Hansen | Ola | 30 |
| 2 | Svendson | Tove | 23 |
| 3 | Pettersen | Kari | 20 |

### Orders Table

| OrderID | OrderNumber | PersonID |
| --- | --- | --- |
| 1 | 77895 | 3 |
| 2 | 44678 | 3 |
| 3 | 22456 | 2 |
| 4 | 24562 | 1 |

Notice that the "PersonID" column in the "Orders" table points to the "PersonID" column in the "Persons" table.

The "PersonID" column in the "Persons" table is the `PRIMARY KEY` in the "Persons" table.

The "PersonID" column in the "Orders" table is a `FOREIGN KEY` in the "Orders" table.

The `FOREIGN KEY` constraint prevents invalid data from being inserted into the foreign key column,
because it has to be one of the values contained in the parent table.

---

---

## FOREIGN KEY on CREATE TABLE

The following SQL creates a `FOREIGN KEY` on the "PersonID" column when the "Orders" table is created:

CREATE TABLE Orders
(  
   
OrderID int NOT NULL,  
   
OrderNumber int NOT NULL,  
   
PersonID int,  
   
PRIMARY KEY (OrderID),  
   
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)  
);

To allow naming of a `FOREIGN KEY` constraint, and for defining a `FOREIGN KEY` constraint on multiple columns, use the following SQL syntax:

CREATE TABLE Orders
(  
   
OrderID int NOT NULL,  
   
OrderNumber int NOT NULL,  
   
PersonID int,  
   
PRIMARY KEY (OrderID),  
   
CONSTRAINT FK\_PersonOrder FOREIGN KEY (PersonID)  
   
REFERENCES Persons(PersonID)  
);

---

## FOREIGN KEY on ALTER TABLE

To create a `FOREIGN KEY` constraint on the "PersonID" column when the "Orders" table is already created, use the following SQL:

ALTER TABLE Orders  
ADD FOREIGN KEY (PersonID)
REFERENCES Persons(PersonID);

To allow naming of a `FOREIGN KEY` constraint, and for defining a `FOREIGN KEY` constraint on multiple columns, use the following SQL syntax:

ALTER TABLE Orders  
ADD CONSTRAINT FK\_PersonOrder  
FOREIGN KEY (PersonID)
REFERENCES Persons(PersonID);

---

## DROP a FOREIGN KEY Constraint

To drop a `FOREIGN KEY` constraint, use the following SQL:

ALTER TABLE Orders  
DROP FOREIGN KEY FK\_PersonOrder;



---

# MySQL CHECK Constraint

---

## MySQL CHECK Constraint

The `CHECK` constraint is used to limit the value range that can be placed in a column.

If you define a `CHECK` constraint on a column it
will allow only certain values for this column.

If you define a `CHECK` constraint on a table it can limit the values in certain columns based on values in other columns in the row.

---

## CHECK on CREATE TABLE

The following SQL creates a `CHECK` constraint on the "Age" column when the "Persons" table is created.
The `CHECK` constraint ensures that the age of a person must be 18, or older:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
CHECK (Age>=18)  
);

To allow naming of a `CHECK` constraint, and for defining a `CHECK` constraint on multiple columns, use the following SQL syntax:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
City varchar(255),  
   
CONSTRAINT CHK\_Person CHECK (Age>=18 AND City='Sandnes')  
);

---

---

## CHECK on ALTER TABLE

To create a `CHECK` constraint on the "Age" column when the table is already created, use the following SQL:

ALTER TABLE Persons  
ADD CHECK (Age>=18);

To allow naming of a `CHECK` constraint, and for defining a `CHECK` constraint on multiple columns, use the following SQL syntax:

ALTER TABLE Persons  
ADD CONSTRAINT CHK\_PersonAge CHECK (Age>=18 AND City='Sandnes');

---

## DROP a CHECK Constraint

To drop a `CHECK` constraint, use the following SQL:

ALTER TABLE Persons  
DROP CHECK CHK\_PersonAge;



---

# MySQL DEFAULT Constraint

---

## MySQL DEFAULT Constraint

The `DEFAULT` constraint is used to set a default value for a column.

The default value will be added to all new records, if no other value is specified.

---

## DEFAULT on CREATE TABLE

The following SQL sets a `DEFAULT` value for the "City" column when the "Persons" table is created:

CREATE TABLE Persons
(  
    ID int NOT NULL,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
   
Age int,  
   
City varchar(255) DEFAULT 'Sandnes'  
);

The `DEFAULT` constraint can also be used to insert system values, by using functions like `CURRENT_DATE()`:

CREATE TABLE Orders
(  
    ID int NOT NULL,  
   
OrderNumber int NOT NULL,  
   
OrderDate date DEFAULT CURRENT\_DATE()  
);

---

## DEFAULT on ALTER TABLE

To create a `DEFAULT` constraint on the "City" column when the table is already created, use the following SQL:

ALTER TABLE Persons  
ALTER City SET DEFAULT 'Sandnes';

---

## DROP a DEFAULT Constraint

To drop a `DEFAULT` constraint, use the following SQL:

ALTER TABLE Persons  
ALTER City DROP DEFAULT;



---

# MySQL CREATE INDEX Statement

---

## MySQL CREATE INDEX Statement

The `CREATE INDEX` statement is used to create indexes in tables.

Indexes are used to retrieve data from the database more quickly than
otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

**Note:** Updating a table with indexes takes more time than updating a table without (because the indexes also need an update).
So, only create indexes on columns that will be frequently searched against.

### CREATE INDEX Syntax

Creates an index on a table. Duplicate values are allowed:

CREATE INDEX *index\_name*  
ON *table\_name* (*column1*, *column2*, ...);

### CREATE UNIQUE INDEX Syntax

Creates a unique index on a table. Duplicate values are not allowed:

CREATE UNIQUE INDEX *index\_name*  
ON *table\_name* (*column1*, *column2*, ...);

---

## MySQL CREATE INDEX Example

The SQL statement below creates an index named "idx\_lastname" on the "LastName" column in the "Persons" table:

CREATE INDEX idx\_lastname  
ON Persons (LastName);

If you want to create an index on a combination of columns, you can list the column names within the parentheses, separated by commas:

CREATE INDEX idx\_pname  
ON Persons (LastName, FirstName);

---

## DROP INDEX Statement

The `DROP INDEX` statement is used to delete an index in a table.

ALTER TABLE *table\_name*DROP INDEX *index\_name*;



---

# MySQL AUTO INCREMENT Field

---

## What is an AUTO INCREMENT Field?

Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

Often this is the primary key field that we would like to be created automatically every time a new record is inserted.

---

## MySQL AUTO\_INCREMENT Keyword

MySQL uses the `AUTO_INCREMENT` keyword to perform an auto-increment feature.

By default, the starting value for `AUTO_INCREMENT` is 1, and it will increment by 1 for each new record.

The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

CREATE TABLE Persons
(  
   
Personid int NOT NULL AUTO\_INCREMENT,  
   
LastName varchar(255) NOT NULL,  
   
FirstName varchar(255),  
    Age int,  
   
PRIMARY KEY (Personid)  
);

To let the `AUTO_INCREMENT` sequence start with another value, use the following SQL statement:

ALTER TABLE Persons AUTO\_INCREMENT=100;

When we insert a new record into the "Persons" table, we do NOT have to specify a value for the "Personid"
column (a unique value will be added automatically):

INSERT INTO Persons (FirstName,LastName)  
VALUES ('Lars','Monsen');

The SQL statement above would insert a new record into the "Persons" table. The
"Personid" column would be assigned a unique value automatically. The "FirstName" column would be set to
"Lars" and the "LastName" column would be set to "Monsen".



---

# MySQL Working With Dates

---

## MySQL Dates

The most difficult part when working with dates is to be sure that the format of the date you are trying to insert,
matches the format of the date column in the database.

As long as your data contains only the date portion, your queries will work as expected. However, if a time portion is involved, it gets
more complicated.

---

## MySQL Date Data Types

MySQL comes with the following data types for storing a date or a date/time value in the database:

* `DATE` - format YYYY-MM-DD
* `DATETIME` - format: YYYY-MM-DD HH:MI:SS
* `TIMESTAMP` - format: YYYY-MM-DD HH:MI:SS
* `YEAR` - format YYYY or YY

**Note:** The date data type are set for a column when you create a new table in your database!

---

## Working with Dates

Look at the following table:

### Orders Table

| OrderId | ProductName | OrderDate |
| --- | --- | --- |
| 1 | Geitost | 2008-11-11 |
| 2 | Camembert Pierrot | 2008-11-09 |
| 3 | Mozzarella di Giovanni | 2008-11-11 |
| 4 | Mascarpone Fabioli | 2008-10-29 |

Now we want to select the records with an OrderDate of "2008-11-11" from the table above.

We use the following `SELECT` statement:

SELECT \* FROM Orders WHERE OrderDate='2008-11-11'

The result-set will look like this:

| OrderId | ProductName | OrderDate |
| --- | --- | --- |
| 1 | Geitost | 2008-11-11 |
| 3 | Mozzarella di Giovanni | 2008-11-11 |

**Note:** Two dates can easily be compared if there is no time component involved!

Now, assume that the "Orders" table looks like this (notice the
added time-component in the "OrderDate" column):

| OrderId | ProductName | OrderDate |
| --- | --- | --- |
| 1 | Geitost | 2008-11-11 13:23:44 |
| 2 | Camembert Pierrot | 2008-11-09 15:45:21 |
| 3 | Mozzarella di Giovanni | 2008-11-11 11:12:01 |
| 4 | Mascarpone Fabioli | 2008-10-29 14:56:59 |

If we use the same `SELECT` statement as above:

SELECT \* FROM Orders WHERE OrderDate='2008-11-11'

we will get no result! This is because the query is looking only for dates with no time portion.

**Tip:** To keep your queries simple and easy to maintain, do not use time-components in your dates, unless you have to!



---



---



---



---



---



---



---



---



---

# MySQL Functions

---

MySQL has many built-in functions.

This reference contains string, numeric, date, and some advanced functions
in MySQL.

---

## MySQL String Functions

| Function | Description |
| --- | --- |
| [ASCII](func_mysql_ascii.asp) | Returns the ASCII value for the specific character |
| [CHAR\_LENGTH](func_mysql_char_length.asp) | Returns the length of a string (in characters) |
| [CHARACTER\_LENGTH](func_mysql_character_length.asp) | Returns the length of a string (in characters) |
| [CONCAT](func_mysql_concat.asp) | Adds two or more expressions together |
| [CONCAT\_WS](func_mysql_concat_ws.asp) | Adds two or more expressions together with a separator |
| [FIELD](func_mysql_field.asp) | Returns the index position of a value in a list of values |
| [FIND\_IN\_SET](func_mysql_find_in_set.asp) | Returns the position of a string within a list of strings |
| [FORMAT](func_mysql_format.asp) | Formats a number to a format like "#,###,###.##", rounded to a specified number of decimal places |
| [INSERT](func_mysql_insert.asp) | Inserts a string within a string at the specified position and for a certain number of characters |
| [INSTR](func_mysql_instr.asp) | Returns the position of the first occurrence of a string in another string |
| [LCASE](func_mysql_lcase.asp) | Converts a string to lower-case |
| [LEFT](func_mysql_left.asp) | Extracts a number of characters from a string (starting from left) |
| [LENGTH](func_mysql_length.asp) | Returns the length of a string (in bytes) |
| [LOCATE](func_mysql_locate.asp) | Returns the position of the first occurrence of a substring in a string |
| [LOWER](func_mysql_lower.asp) | Converts a string to lower-case |
| [LPAD](func_mysql_lpad.asp) | Left-pads a string with another string, to a certain length |
| [LTRIM](func_mysql_ltrim.asp) | Removes leading spaces from a string |
| [MID](func_mysql_mid.asp) | Extracts a substring from a string (starting at any position) |
| [POSITION](func_mysql_position.asp) | Returns the position of the first occurrence of a substring in a string |
| [REPEAT](func_mysql_repeat.asp) | Repeats a string as many times as specified |
| [REPLACE](func_mysql_replace.asp) | Replaces all occurrences of a substring within a string, with a new substring |
| [REVERSE](func_mysql_reverse.asp) | Reverses a string and returns the result |
| [RIGHT](func_mysql_right.asp) | Extracts a number of characters from a string (starting from right) |
| [RPAD](func_mysql_rpad.asp) | Right-pads a string with another string, to a certain length |
| [RTRIM](func_mysql_rtrim.asp) | Removes trailing spaces from a string |
| [SPACE](func_mysql_space.asp) | Returns a string of the specified number of space characters |
| [STRCMP](func_mysql_strcmp.asp) | Compares two strings |
| [SUBSTR](func_mysql_substr.asp) | Extracts a substring from a string (starting at any position) |
| [SUBSTRING](func_mysql_substring.asp) | Extracts a substring from a string (starting at any position) |
| [SUBSTRING\_INDEX](func_mysql_substring_index.asp) | Returns a substring of a string before a specified number of delimiter occurs |
| [TRIM](func_mysql_trim.asp) | Removes leading and trailing spaces from a string |
| [UCASE](func_mysql_ucase.asp) | Converts a string to upper-case |
| [UPPER](func_mysql_upper.asp) | Converts a string to upper-case |

---

---

## MySQL Numeric Functions

| Function | Description |
| --- | --- |
| [ABS](func_mysql_abs.asp) | Returns the absolute value of a number |
| [ACOS](func_mysql_acos.asp) | Returns the arc cosine of a number |
| [ASIN](func_mysql_asin.asp) | Returns the arc sine of a number |
| [ATAN](func_mysql_atan.asp) | Returns the arc tangent of one or two numbers |
| [ATAN2](func_mysql_atan2.asp) | Returns the arc tangent of two numbers |
| [AVG](func_mysql_avg.asp) | Returns the average value of an expression |
| [CEIL](func_mysql_ceil.asp) | Returns the smallest integer value that is >= to a number |
| [CEILING](func_mysql_ceiling.asp) | Returns the smallest integer value that is >= to a number |
| [COS](func_mysql_cos.asp) | Returns the cosine of a number |
| [COT](func_mysql_cot.asp) | Returns the cotangent of a number |
| [COUNT](func_mysql_count.asp) | Returns the number of records returned by a select query |
| [DEGREES](func_mysql_degrees.asp) | Converts a value in radians to degrees |
| [DIV](func_mysql_div.asp) | Used for integer division |
| [EXP](func_mysql_exp.asp) | Returns e raised to the power of a specified number |
| [FLOOR](func_mysql_floor.asp) | Returns the largest integer value that is <= to a number |
| [GREATEST](func_mysql_greatest.asp) | Returns the greatest value of the list of arguments |
| [LEAST](func_mysql_least.asp) | Returns the smallest value of the list of arguments |
| [LN](func_mysql_ln.asp) | Returns the natural logarithm of a number |
| [LOG](func_mysql_log.asp) | Returns the natural logarithm of a number, or the logarithm of a number to a specified base |
| [LOG10](func_mysql_log10.asp) | Returns the natural logarithm of a number to base 10 |
| [LOG2](func_mysql_log2.asp) | Returns the natural logarithm of a number to base 2 |
| [MAX](func_mysql_max.asp) | Returns the maximum value in a set of values |
| [MIN](func_mysql_min.asp) | Returns the minimum value in a set of values |
| [MOD](func_mysql_mod.asp) | Returns the remainder of a number divided by another number |
| [PI](func_mysql_pi.asp) | Returns the value of PI |
| [POW](func_mysql_pow.asp) | Returns the value of a number raised to the power of another number |
| [POWER](func_mysql_power.asp) | Returns the value of a number raised to the power of another number |
| [RADIANS](func_mysql_radians.asp) | Converts a degree value into radians |
| [RAND](func_mysql_rand.asp) | Returns a random number |
| [ROUND](func_mysql_round.asp) | Rounds a number to a specified number of decimal places |
| [SIGN](func_mysql_sign.asp) | Returns the sign of a number |
| [SIN](func_mysql_sin.asp) | Returns the sine of a number |
| [SQRT](func_mysql_sqrt.asp) | Returns the square root of a number |
| [SUM](func_mysql_sum.asp) | Calculates the sum of a set of values |
| [TAN](func_mysql_tan.asp) | Returns the tangent of a number |
| [TRUNCATE](func_mysql_truncate.asp) | Truncates a number to the specified number of decimal places |

---

## MySQL Date Functions

| Function | Description |
| --- | --- |
| [ADDDATE](func_mysql_adddate.asp) | Adds a time/date interval to a date and then returns the date |
| [ADDTIME](func_mysql_addtime.asp) | Adds a time interval to a time/datetime and then returns the time/datetime |
| [CURDATE](func_mysql_curdate.asp) | Returns the current date |
| [CURRENT\_DATE](func_mysql_current_date.asp) | Returns the current date |
| [CURRENT\_TIME](func_mysql_current_time.asp) | Returns the current time |
| [CURRENT\_TIMESTAMP](func_mysql_current_timestamp.asp) | Returns the current date and time |
| [CURTIME](func_mysql_curtime.asp) | Returns the current time |
| [DATE](func_mysql_date.asp) | Extracts the date part from a datetime expression |
| [DATEDIFF](func_mysql_datediff.asp) | Returns the number of days between two date values |
| [DATE\_ADD](func_mysql_date_add.asp) | Adds a time/date interval to a date and then returns the date |
| [DATE\_FORMAT](func_mysql_date_format.asp) | Formats a date |
| [DATE\_SUB](func_mysql_date_sub.asp) | Subtracts a time/date interval from a date and then returns the date |
| [DAY](func_mysql_day.asp) | Returns the day of the month for a given date |
| [DAYNAME](func_mysql_dayname.asp) | Returns the weekday name for a given date |
| [DAYOFMONTH](func_mysql_dayofmonth.asp) | Returns the day of the month for a given date |
| [DAYOFWEEK](func_mysql_dayofweek.asp) | Returns the weekday index for a given date |
| [DAYOFYEAR](func_mysql_dayofyear.asp) | Returns the day of the year for a given date |
| [EXTRACT](func_mysql_extract.asp) | Extracts a part from a given date |
| [FROM\_DAYS](func_mysql_from_days.asp) | Returns a date from a numeric datevalue |
| [HOUR](func_mysql_hour.asp) | Returns the hour part for a given date |
| [LAST\_DAY](func_mysql_last_day.asp) | Extracts the last day of the month for a given date |
| [LOCALTIME](func_mysql_localtime.asp) | Returns the current date and time |
| [LOCALTIMESTAMP](func_mysql_localtimestamp.asp) | Returns the current date and time |
| [MAKEDATE](func_mysql_makedate.asp) | Creates and returns a date based on a year and a number of days value |
| [MAKETIME](func_mysql_maketime.asp) | Creates and returns a time based on an hour, minute, and second value |
| [MICROSECOND](func_mysql_microsecond.asp) | Returns the microsecond part of a time/datetime |
| [MINUTE](func_mysql_minute.asp) | Returns the minute part of a time/datetime |
| [MONTH](func_mysql_month.asp) | Returns the month part for a given date |
| [MONTHNAME](func_mysql_monthname.asp) | Returns the name of the month for a given date |
| [NOW](func_mysql_now.asp) | Returns the current date and time |
| [PERIOD\_ADD](func_mysql_period_add.asp) | Adds a specified number of months to a period |
| [PERIOD\_DIFF](func_mysql_period_diff.asp) | Returns the difference between two periods |
| [QUARTER](func_mysql_quarter.asp) | Returns the quarter of the year for a given date value |
| [SECOND](func_mysql_second.asp) | Returns the seconds part of a time/datetime |
| [SEC\_TO\_TIME](func_mysql_sec_to_time.asp) | Returns a time value based on the specified seconds |
| [STR\_TO\_DATE](func_mysql_str_to_date.asp) | Returns a date based on a string and a format |
| [SUBDATE](func_mysql_subdate.asp) | Subtracts a time/date interval from a date and then returns the date |
| [SUBTIME](func_mysql_subtime.asp) | Subtracts a time interval from a datetime and then returns the time/datetime |
| [SYSDATE](func_mysql_sysdate.asp) | Returns the current date and time |
| [TIME](func_mysql_time.asp) | Extracts the time part from a given time/datetime |
| [TIME\_FORMAT](func_mysql_time_format.asp) | Formats a time by a specified format |
| [TIME\_TO\_SEC](func_mysql_time_to_sec.asp) | Converts a time value into seconds |
| [TIMEDIFF](func_mysql_timediff.asp) | Returns the difference between two time/datetime expressions |
| [TIMESTAMP](func_mysql_timestamp.asp) | Returns a datetime value based on a date or datetime value |
| [TO\_DAYS](func_mysql_to_days.asp) | Returns the number of days between a date and date "0000-00-00" |
| [WEEK](func_mysql_week.asp) | Returns the week number for a given date |
| [WEEKDAY](func_mysql_weekday.asp) | Returns the weekday number for a given date |
| [WEEKOFYEAR](func_mysql_weekofyear.asp) | Returns the week number for a given date |
| [YEAR](func_mysql_year.asp) | Returns the year part for a given date |
| [YEARWEEK](func_mysql_yearweek.asp) | Returns the year and week number for a given date |

---

## MySQL Advanced Functions

| Function | Description |
| --- | --- |
| [BIN](func_mysql_bin.asp) | Returns a binary representation of a number |
| [BINARY](func_mysql_binary.asp) | Converts a value to a binary string |
| [CASE](func_mysql_case.asp) | Goes through conditions and return a value when the first condition is met |
| [CAST](func_mysql_cast.asp) | Converts a value (of any type) into a specified datatype |
| [COALESCE](func_mysql_coalesce.asp) | Returns the first non-null value in a list |
| [CONNECTION\_ID](func_mysql_connection_id.asp) | Returns the unique connection ID for the current connection |
| [CONV](func_mysql_conv.asp) | Converts a number from one numeric base system to another |
| [CONVERT](func_mysql_convert.asp) | Converts a value into the specified datatype or character set |
| [CURRENT\_USER](func_mysql_current_user.asp) | Returns the user name and host name for the MySQL account that the server used to authenticate the current client |
| [DATABASE](func_mysql_database.asp) | Returns the name of the current database |
| [IF](func_mysql_if.asp) | Returns a value if a condition is TRUE, or another value if a condition is FALSE |
| [IFNULL](func_mysql_ifnull.asp) | Return a specified value if the expression is NULL, otherwise return the expression |
| [ISNULL](func_mysql_isnull.asp) | Returns 1 or 0 depending on whether an expression is NULL |
| [LAST\_INSERT\_ID](func_mysql_last_insert_id.asp) | Returns the AUTO\_INCREMENT id of the last row that has been inserted or updated in a table |
| [NULLIF](func_mysql_nullif.asp) | Compares two expressions and returns NULL if they are equal. Otherwise, the first expression is returned |
| [SESSION\_USER](func_mysql_session_user.asp) | Returns the current MySQL user name and host name |
| [SYSTEM\_USER](func_mysql_system_user.asp) | Returns the current MySQL user name and host name |
| [USER](func_mysql_user.asp) | Returns the current MySQL user name and host name |
| [VERSION](func_mysql_version.asp) | Returns the current version of the MySQL dat

---

# MySQL Data Types

---

The data type of a column defines what value the column can hold:
integer, character, money, date and time, binary,
and so on.

---

## MySQL Data Types (Version 8.0)

Each column in a database table is required to have a name and a data type.

An SQL developer must decide what type of data that will be stored inside each
column when creating a table. The data type is a
guideline for SQL to understand what type of data is expected inside of each
column, and it also identifies how SQL will interact with the stored data.

In MySQL there are three main data types: string, numeric, and date and time.

### String Data Types

| Data type | Description |
| --- | --- |
| CHAR(size) | A FIXED length string (can contain letters, numbers, and special characters). The *size* parameter specifies the column length in characters - can be from 0 to 255. Default is 1 |
| VARCHAR(size) | A VARIABLE length string (can contain letters, numbers, and special characters). The *size* parameter specifies the maximum column length in characters - can be from 0 to 65535 |
| BINARY(size) | Equal to CHAR(), but stores binary byte strings. The *size* parameter specifies the column length in bytes. Default is 1 |
| VARBINARY(size) | Equal to VARCHAR(), but stores binary byte strings. The *size* parameter specifies the maximum column length in bytes. |
| TINYBLOB | For BLOBs (Binary Large OBjects). Max length: 255 bytes |
| TINYTEXT | Holds a string with a maximum length of 255 characters |
| TEXT(size) | Holds a string with a maximum length of 65,535 bytes |
| BLOB(size) | For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data |
| MEDIUMTEXT | Holds a string with a maximum length of 16,777,215 characters |
| MEDIUMBLOB | For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data |
| LONGTEXT | Holds a string with a maximum length of 4,294,967,295 characters |
| LONGBLOB | For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of data |
| ENUM(val1, val2, val3, ...) | A string object that can have only one value, chosen from a list of possible values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted. The values are sorted in the order you enter them |
| SET(val1, val2, val3, ...) | A string object that can have 0 or more values, chosen from a list of possible values. You can list up to 64 values in a SET list |

---

---

### Numeric Data Types

| Data type | Description |
| --- | --- |
| BIT(*size*) | A bit-value type. The number of bits per value is specified in *size*. The *size* parameter can hold a value from 1 to 64. The default value for *size* is 1. |
| TINYINT(*size*) | A very small integer. Signed range is from -128 to 127. Unsigned range is from 0 to 255. The *size* parameter specifies the maximum display width (which is 255) |
| BOOL | Zero is considered as false, nonzero values are considered as true. |
| BOOLEAN | Equal to BOOL |
| SMALLINT(*size*) | A small integer. Signed range is from -32768 to 32767. Unsigned range is from 0 to 65535. The *size* parameter specifies the maximum display width (which is 255) |
| MEDIUMINT(*size*) | A medium integer. Signed range is from -8388608 to 8388607. Unsigned range is from 0 to 16777215. The *size* parameter specifies the maximum display width (which is 255) |
| INT(*size*) | A medium integer. Signed range is from -2147483648 to 2147483647. Unsigned range is from 0 to 4294967295. The *size* parameter specifies the maximum display width (which is 255) |
| INTEGER(*size*) | Equal to INT(size) |
| BIGINT(*size*) | A large integer. Signed range is from -9223372036854775808 to 9223372036854775807. Unsigned range is from 0 to 18446744073709551615. The *size* parameter specifies the maximum display width (which is 255) |
| FLOAT(*size*, *d*) | A floating point number. The total number of digits is specified in *size*. The number of digits after the decimal point is specified in the *d* parameter. This syntax is deprecated in MySQL 8.0.17, and it will be removed in future MySQL versions |
| FLOAT(*p*) | A floating point number. MySQL uses the *p* value to determine whether to use FLOAT or DOUBLE for the resulting data type. If *p* is from 0 to 24, the data type becomes FLOAT(). If *p* is from 25 to 53, the data type becomes DOUBLE() |
| DOUBLE(*size*, *d*) | A normal-size floating point number. The total number of digits is specified in *size*. The number of digits after the decimal point is specified in the *d* parameter |
| DOUBLE PRECISION(*size*, *d*) |  |
| DECIMAL(*size*, *d*) | An exact fixed-point number. The total number of digits is specified in *size*. The number of digits after the decimal point is specified in the *d* parameter. The maximum number for *size* is 65. The maximum number for *d* is 30. The default value for *size* is 10. The default value for *d* is 0. |
| DEC(*size*, *d*) | Equal to DECIMAL(size,d) |

**Note:** All the numeric data types may have an extra option: UNSIGNED
or ZEROFILL. If you add the UNSIGNED option, MySQL disallows negative values for
the column. If you add the ZEROFILL option, MySQL automatically also adds the
UNSIGNED attribute to the column.

### Date and Time Data Types

| Data type | Description |
| --- | --- |
| DATE | A date. Format: YYYY-MM-DD. The supported range is from '1000-01-01' to '9999-12-31' |
| DATETIME(*fsp*) | A date and time combination. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'. Adding DEFAULT and ON UPDATE in the column definition to get automatic initialization and updating to the current date and time |
| TIMESTAMP(*fsp*) | A timestamp. TIMESTAMP values are stored as the number of seconds since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC. Automatic initialization and updating to the current date and time can be specified using DEFAULT CURRENT\_TIMESTAMP and ON UPDATE CURRENT\_TIMESTAMP in the column definition |
| TIME(*fsp*) | A time. Format: hh:mm:ss. The supported range is from '-838:59:59' to '838:59:59' |
| YEAR | A year in four-digit format. Values allowed in four-digit format: 1901 to 2155, and 0000. MySQL 8.0 does not support year in two-digit fo

---



---

