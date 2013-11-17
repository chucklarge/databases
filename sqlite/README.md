load the db

    sqlite users.sqlite < users.sql
    sqlite users.sqlite
    select * from users;

sqlite> select * from users;

    1|chuck|close|cc@email.com|1276473600|1276473600
    2|george|jones|gj@email.com|1295827200|1295827200
    3|alex|smith|as@email.com|1309564800|1309564800
    4|john|benotto|jb@email.com|1315008000|1315008000
    5|peter|ryan|pr@email.com|1323734400|1323734400

sqlite> SELECT datetime(create_date, 'unixepoch') from users;

    2010-06-14 00:00:00
    2011-01-24 00:00:00
    2011-07-02 00:00:00
    2011-09-03 00:00:00
    2011-12-13 00:00:00

commands

    .databases
    .tables
    .quit
