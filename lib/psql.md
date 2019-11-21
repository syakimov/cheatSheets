Use this line to connect
psql -U {USER} -d {DATABASE} -h {HOST} -W

Enter password

--------------------------------------------------------------------------------
install pgadmin
open pgtunnel
start pgadmin

--------------------------------------------------------------------------------
Commands

sudo -u postgres psql -> start psql
\q quit

Copy database from location
pg_dump -U {USER} -h {HOST} -W -d {DB} > {NEW_NAME}.sql

start psql
CREATE DATABASE {DBNAME};

import in db
psql -U user -W -d db < dump.sql 

show table
\d {table_name}

list all enum types
\dT+ transaction_type_char
                                             List of data types
 Schema |         Name          |     Internal name     | Size | Elements | Access privileges | Description 
--------+-----------------------+-----------------------+------+----------+-------------------+-------------
 public | transaction_type_char | transaction_type_char | 4    | buy     +|                   | 
        |                       |                       |      | sell    +|                   | 
        |                       |                       |      | balance +|                   | 
        |                       |                       |      | credit   |                   | 
(1 row)
