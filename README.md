#How to postgres

* Listing all the users: `psql -l`
* Create user: `createuser -P -s -e -d username`
* Create DB: `createdb tester`

test
Connecting to postgres:

```
from sqlalchemy import create_engine
engine = create_engine("postgresql://iamauser:thatpasswordyouentered@localhost/test")
con = engine.connect()
con.execute()
print engine.table_names() # list all the table names
```