# Notes

## Menu

- intro to RDBMS
- SQL
- Knex ++
- CRUD operation persisting data

R = relational
DB = database
M = management
S = system

A relation is similar to spreadsheet, it has rowws with columns.
Another name for a relations is **Table**.

The data on a Relational Databaase is stored in **Tables**.

[Client] <=HTTP (methods/endpoints/JSON data)=> [API running on a Web Server] <> [Database Management System]

Some popular DBMS
- Oracle
- MySQL
- PostgreSQL
- MS SQL Server
- SQLite3 (file-based RDBMS)
- MongoDB (No [Not Only] SQL database)

HTTP is a network protocol. A protocol is a set of rules for communication over the network.

Each database vendor can (and probably will) have it's own protocol.

SQL = Structured **Query** Language. SQL is a Standart.

Each DBMS will imolement part of the SQL standart and add extra features on top.

some sql commands:

https://www.w3schools.com/Sql/tryit.asp?filename=trysql_select_top

SELECT CategoryName, Description as Details FROM categories

SELECT * FROM [Products List]


```sql
SELECT * FROM Products
where price > 45
order by price desc
```

-- list customers that live in Germany
SELECT * FROM [Customers]
where Country = 'Germany'

-- list customers that live in Germany
SELECT country, city, * FROM [Customers]
where Country = 'Germany'
order by country, city

```sql
-- list customers that live in Germany
SELECT country, city, * FROM [Customers]
where Country = 'Germany' or country = 'Argentina'
order by country, city
```

```sql
-- list customers that live in Germany
SELECT country, city, * FROM [Customers]
where Country in ('Germany', 'Argentina', 'Austria')
order by country, city
```

```sql
SELECT * FROM [Products]
order by price desc
limit 5
```

```sql
insert into categories (description, categoryName)
values ('Ololo', 'Ololo pewpew')
```

```sql
update Categories set description = 'Lambda Ololo'
--select * from categories
where categoryId = 9
```
```sql
update Categories set description = 'Lambda Ololo', CategoryName = 'pewpew'
--select * from categories
where categoryId = 9
```

```sql
delete from Categories 
--select * from categories
where categoryId = 9
```

## Connect to a DBMS from our API

[API] <= JS => [knex] <- SQL -> [DB Driver] <= DBMS Protocol => [DBMS] 