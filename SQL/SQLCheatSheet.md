# SQL: Structured Query language
![](https://en.wikipedia.org/wiki/Relational_database#/media/File:Relational_database_terms.svg)

* Dont forgete the `;` at the end of each call for multiple calls
* Commands are case insensitive

# Schema Commands
```sql
    CREATE TABLE TableName (id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE,
        attr1Name VARCHAR(128),
        attr2Name VARCHAR(128),
        OtherTableName_id INTEGER) # Foreign Key

    DROP TABLE TableName
```

# Data Commands
```sql
    INSERT INTO TableName (attr1Name, attr2Name,attrForeignKey)
        VALUES ('attr1Value', 'attr2Value', 333)

    INSERT OR IGNORE # clause ignored if INSERT make an error, f.ex unique statuement is infringed
    INSERT OR REPLACE # replace an entry if the unique constrain would be infringed with the insertion

    DELETE FROM TableName WHERE attr2Name='attr2Value'

    UPDATE TableName SET attr1Name='attr1NewValue'
        WHERE attr2Name='attr2Value' # works also if WHERE is on attr1

    SELECT * FROM TableName
        WHERE attr2Name='attr2Value'
        ORDER BY attr1Name
        ORDER BY attr2Name DESC
        JOIN OtherTableName ON TableName.OtherTableName_id = OtherTableName.id  
        # if no ON clause, all combinations are computed
```

# Data types (MySQL)
###Binary :
    * BIT (array of bits, specify lenght)
    * BOOL (=`TINYINT(1)`)

###Integer :
    * `TINYINT` (-128 to 127)
    * `SMALLINT` (-32768 to 32767)
    * `INT` (-2147483648 to 2147483647)
    * `BIGINT` (-9223372036854775808 to 9223372036854775807)

###Decimal numbers:
    *`DECIMAL`: fixed-point number
    *`FLOAT`: floating point value
    *`DOUBLE`: double precision floating point value

# Definition
* Primary key: id of a tuple (entry)
* Foreign key: refere to the primary key of another table
* Logical key: can be used in a WHERE clause  
* Junction table: table with several foreign keys and no primary key, may contain other metadata on the relation. Combination of the foreign keys is defined as the primary key. Used for many-to-may relationship.

# References
* https://www.cheatography.com/davechild/cheat-sheets/mysql/
