
# Postgres and Json


Indexes
An inverted index is used for tree/text and other type docuements for efficient indexing 

GIN indexes can be used to efficiently search for keys or key/value pairs occurring within a large number of  jsonb  documents (datums). Two GIN  "operator classes"  are provided, offering different performance and flexibility trade-offs.

The default GIN operator class for  jsonb  supports queries with the  @>,  ?,  ?&  and  ?|  operators. (For details of the semantics that these operators implement, see  [Table 9-41](https://www.postgresql.org/docs/9.4/functions-json.html#FUNCTIONS-JSONB-OP-TABLE).) An example of creating an index with this operator class is:

CREATE INDEX idxgin ON api USING gin (jdoc);

The non-default GIN operator class  jsonb_path_ops  supports indexing the  @>  operator only. An example of creating an index with this operator class is:

CREATE INDEX idxginp ON api USING gin (jdoc jsonb_path_ops);
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQwNzUzMTA5LC05NjY5MjE1ODddfQ==
-->