Add User

    GRANT ALL ON [database_name].* TO '[username]'@'[hostname]' IDENTIFIED BY '[password]';
    FLUSH PRIVILEGES;

Load CSV to table (make sure csv file is in /tmp, otherwise mysql won't have access to it)

    LOAD DATA INFILE "/tmp/majordecenstudents.csv" INTO TABLE `eligible_student`
    FIELDS TERMINATED BY ',' ENCLOSED BY '"' LINES TERMINATED BY '\n'
    --IGNORE 1 LINES
    (person_id_number,last_name,first_name,uni,entering_year,advisor_lastname)
    SET school_code = 'EN';


Write query to csv file

    SELECT User_ID, Affiliation, Privilege_Level, Name INTO OUTFILE 'security.csv'
    FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"'
    LINES TERMINATED BY '\n'
    FROM Security;

Debug info

    SHOW FULL PROCESSLIST;

Find/Replace Update

    UPDATE [table_name] SET [field_name] = REPLACE([field_name],'[string_to_find]','[string_to_replace]');

Export Query to File

    echo "SHOW FULL PROCESSLIST" | mysql -p drupal_admissions > file.csv
    echo "SELECT * FROM <table_name> WHERE <condition>" | mysql -h $IP_ADDR -u $USER_NAME -p$PASSWD $TABLE_NAME > file.txt
    echo "SHOW FULL PROCESSLIST" | mysql -h $IP_ADDR -u $USER_NAME -p$PASSWD $TABLE_NAME > file.csv

PHP search for multiple words

    $q = mysql_escape_string($q);
    $q_fix = str_replace(" ","%",$q); // Space replacing with %
    $sql = mysql_query("SELECT title FROM articles WHERE title LIKE N'%$q_fix%'");

Other stuff

    show create table [table_name];
    show indexes in [table_name];
    
    
Alters

    ALTER TABLE `table` ADD INDEX `product_id_idx` (`product_id`)
