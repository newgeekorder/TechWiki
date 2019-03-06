
# Postgres and Json


Indexes
An General Inverted Index (GIN)  is an index used for tree/text and other type docuements for efficient indexing.  Postgres supports a GIN index. It is same index that is used behind search engines like Solr and Elastic Search

Creating an index 

    CREATE INDEX my_gin_index ON api USING gin (jdoc);
or 

    CREATE INDEX my_gin_index  ON api USING gin (jdoc jsonb_path_ops);


 Two GIN  "operator classes"  are provided, offering different performance and flexibility trade-offs.

The first (jdoc) index supports a range of postgres operators 
| @>,  ?,  ?&  and  ?|  operators|  |
|--|--|
| @> |  |
| ? | | 
| ? | | 
v



The default GIN operator class for  jsonb  supports queries with the  @>,  ?,  ?&  and  ?|  operators. (For details of the semantics that these operators implement, see  [Table 9-41](https://www.postgresql.org/docs/9.4/functions-json.html#FUNCTIONS-JSONB-OP-TABLE).) An example of creating an index with this operator class is:


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2ODE0MDgyNjIsLTk2NjkyMTU4N119
-->