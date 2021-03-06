
 ## Partitioning
Partitioning refers to splitting what is logically one large table into smaller physical pieces. This is usually to speed up query performance where we partition data into the commonly used data 

 * Range Partitioning - The table is partitioned into  “ranges”  defined by a key column or set of columns, with no overlap between the ranges of values assigned to different partitions. For example, one might partition by date ranges, or by ranges of identifiers for particular business objects.

 * List Partitioning - The table is partitioned by explicitly listing which key values appear in each partition.


 Postgres 10 introduce "declarative Partitioning" 
 https://www.postgresql.org/docs/10/ddl-partitioning.html

## Postgres and Security 
* Authentication 
	* the default md5 salted password mechanism  
	* pg10 scram -  

> set password_encrption = 'scram';

* Restrict IP ranges
open file called /var/lib/pgsql/data/pg_hba.conf. Login as postgres user using su command:

    > $ su - postgres 
    > $ vi /var/lib/pgsql/data/pg_hba.conf

to give access to 192.168.1.0/24 network:  
`host all all 192.168.1.0 255.255.255.0 trust`

To reload configuration without restarting the database 
    select pg_reload_conf();

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk4MTkwMzk0NywxNjIzNjE2NTM4LDQzMj
I3NzM5OSwtMjEyMjExNDk1M119
-->