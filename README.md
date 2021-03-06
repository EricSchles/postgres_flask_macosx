#How to postgres

* Listing all the users: `psql -l`
* Create user: `createuser -P -s -e -d username`
* Create DB: `createdb [database_name]`
* running postgresql: `psql [database_name]`
* delete DB: `dropdb [database_name]`
Connecting to postgres:

```
from sqlalchemy import create_engine
engine = create_engine("postgresql://iamauser:thatpasswordyouentered@localhost/test")
con = engine.connect()
con.execute()
print engine.table_names() # list all the table names
```

Using Postgresql from the command line:

create table:

```
CREATE TABLE table_name(
   column1 datatype,
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
   PRIMARY KEY( one or more columns )
);
```

insert table:

```
INSERT INTO films (code, title, did, date_prod, kind)
    VALUES ('T_601', 'Yojimbo', 106, '1961-06-16', 'Drama');
```

select table:

```
SELECT * FROM table;
```

Listing current dbs: `\list`

Listing all current db tables: `\dt`

[Making a user a super user](http://stackoverflow.com/questions/15791406/logged-in-as-postgres-but-getting-the-error-createuser-creation-of-new-role-fai)

`psql -U [existing user] -d template1`

`alter user postgres superuser;`
