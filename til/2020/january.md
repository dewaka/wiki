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
  - [Namespace Retention Configuration | Aerospike](https://www.aerospike.com/docs/operations/configure/namespace/retention)
    - Aerospike can be configured to `expire` or `evict` least recently updated data.
    - Expiration and eviction algorithms use records `TTL` (Time To Live) value to determine eligibility for removal.
    - `default-ttl` can be set at a `namespace` level. See the documentation
      above for examples.
  - Checking docker exposed ports can be done by `docker port` command - <https://docs.docker.com/engine/reference/commandline/port/>
  - AssertJ test for equality ignoring fields can be done via `isEqualToComparingOnlyGivenFields`, as in the following example,
    
    ```java
    assertThat(testVersion)
        .isEqualToComparingOnlyGivenFields(sourceVersion, "supplySourceList", "name", "defaultSeatId");
    ```

- 2020-01-17
  - Java `EnumMap` and `EnumSet` optimisations - <https://stackoverflow.com/questions/16637288/optimization-done-by-an-enummap-enumset>
  - [dig](https://mediatemple.net/community/products/dv/204644130/understanding-the-dig-command)
