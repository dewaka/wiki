# TIL January, 2020

- 2020-01-15
  - Establish invariants for a unit test in the setup. 
    
    In concrete terms, in JUnit for example, use `@Before` methods to make sure
    that the state of the world fits the assumptions made in the tests. In the
    same manner, use `@After` to ensure that post conditions are also "as
    expected".

- 2020-01-16
  - [Cross Datacenter Replication (XDR) | Aerospike](https://www.aerospike.com/docs/operations/configure/cross-datacenter/)
    
    ```
    Provides inter-cluster replication at teh namespace or optionally set
    granularity level.
    ```
    
    This is an Aerospike Enterprise Edition feature.
