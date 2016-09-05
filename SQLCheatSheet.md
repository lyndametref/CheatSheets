* Dont forgete the `;` at the end of each call
* Commands are case insensitive

  CREATE TABLE TableName (attr1Name VARCHAR(128), attr2Name VARCHAR(128))
  INSERT INTO TableName (attr1Name, attr2Name) VALUES ('attr1Value', 'attr2Value')
  DELETE FROM TableName WHERE attr2Name='attr2Value'
  UPDATE TableName SET attr1Name='attr1NewValue' WHERE attr2Name='attr2Value' # works also if WHERE is on attr1
  SELECT * FROM TableName
    WHERE attr2Name='attr2Value'
    ORDER BY attr1Name
  
# Definition
* Primary key: id of a tuple (entry)
* Foreign key: refere to the primary key of another table
* Logical key: can be used in a WHERE clause  