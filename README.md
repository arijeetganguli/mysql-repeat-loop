# mysql-repeat-loop

How to use Repeat in MySQL.

## Procedure
```sql
CREATE PROCEDURE `Repeat_Loop`(_start int, _end int )
BEGIN

	DECLARE _a INT;

	DROP TEMPORARY TABLE IF EXISTS __table_list;
	CREATE TEMPORARY TABLE IF NOT EXISTS __table_list 
	(
		num INT
	);

	SET _a = _start;

	REPEAT -- Start repeat
  
		INSERT INTO __table_list VALUE (_a);
    
		SET _a = _a + 1; -- Counter
		
		UNTIL _a > _end -- Condition to continue
    
	END REPEAT;

	SELECT * FROM __table_list;
END
```
