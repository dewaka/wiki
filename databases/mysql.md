# MySQL 

- DELETE QUICK - <https://dev.mysql.com/doc/refman/8.0/en/delete.html>

  ```
  The QUICK modifier affects whether index leaves are merged for delete operations. DELETE QUICK is most useful for applications where index values for deleted rows are replaced by similar index values from rows inserted later. In this case, the holes left by deleted values are reused.
  ```
