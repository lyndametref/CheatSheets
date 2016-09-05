* Dont forgete the `;` at the end of each call for multiple calls
* Commands are case insensitive

    CREATE TABLE TableName (id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE,
        attr1Name VARCHAR(128), 
        attr2Name VARCHAR(128),
        attrForeignKey INTEGER)
    
    INSERT INTO TableName (attr1Name, attr2Name,attrForeignKey) VALUES ('attr1Value', 'attr2Value', 333)
    
    DELETE FROM TableName WHERE attr2Name='attr2Value'
    
    UPDATE TableName SET attr1Name='attr1NewValue' WHERE attr2Name='attr2Value' # works also if WHERE is on attr1
    
    SELECT * FROM TableName
        WHERE attr2Name='attr2Value'
        ORDER BY attr1Name
  
# Definition
* Primary key: id of a tuple (entry)
* Foreign key: refere to the primary key of another table
* Logical key: can be used in a WHERE clause  