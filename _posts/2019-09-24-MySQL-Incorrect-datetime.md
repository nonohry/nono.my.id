---
title:  "MySQL Incorrect datetime value: '0000-00-00 00:00:00'"
categories: [MySQL]
comments: true
---

MySQL Incorrect datetime value: '0000-00-00 00:00:00'

```mysql
-- save current setting of sql_mode
SET @old_sql_mode := @@sql_mode ;

-- derive a new value by removing NO_ZERO_DATE and NO_ZERO_IN_DATE
SET @new_sql_mode := @old_sql_mode ;
SET @new_sql_mode := TRIM(BOTH ',' FROM REPLACE(CONCAT(',',@new_sql_mode,','),',NO_ZERO_DATE,'  ,','));
SET @new_sql_mode := TRIM(BOTH ',' FROM REPLACE(CONCAT(',',@new_sql_mode,','),',NO_ZERO_IN_DATE,',','));
SET @@sql_mode := @new_sql_mode ;

-- perform the operation that errors due to "zero dates"

-- when we are done with required operations, we can revert back
-- to the original sql_mode setting, from the value we saved
SET @@sql_mode := @old_sql_mode ;

set global sql_mode="NO_ENGINE_SUBSTITUTION";
```
