
# Postgres and Json


Indexes
An General Inverted Index (GIN)  is an index used for tree/text and other type docuements for efficient indexing.  Postgres supports a GIN index. It is same index that is used behind search engines like Solr and Elastic Search

Gin index's are good at querying columns with lots of duplicates 

Creating an index 

    CREATE INDEX my_gin_index ON api USING gin (jdoc);
or 

    CREATE INDEX my_gin_index  ON api USING gin (jdoc jsonb_path_ops);


 Two GIN  "operator classes"  are provided, offering different performance and flexibility trade-offs.

The first (jdoc) index supports a range of postgres operators 

| Operators |  Note|  
|--|--|
| @> |  |
|  ?&  | | 
| ? | | 

While the second (faster) index only supports the `@>` operator 


## Links and Reference
 * https://www.postgresql.org/docs/9.4/datatype-json.html
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY5NjgxNTEyOCwtMTM4MTc2MzgzMiwxMj
g4NzYxNzM3LDE0MjQ1OTQwNDIsLTk2NjkyMTU4N119
-->