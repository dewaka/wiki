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

- 2020-01-19
  - syscall perturbation
    - [System call perturbation using Strace](https://github.com/KTH/royal-chaos/blob/master/chaosorca/sysc/README.md)
    - [Observability and Chaos Engineering on System Calls for Containerized Applications in Docker](https://arxiv.org/pdf/1907.13039.pdf)

- 2020-01-20
  - [CompletionStage](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletionStage.html)
    - Examples of usage - <https://dzone.com/articles/20-examples-of-using-javas-completablefuture>
  - GNU grep `-o` option for `--only-matching` entries in a search - pretty useful in practice.

- 2020-01-21
  - Julia DataFrame Cheat Sheet - <https://jcharistech.wordpress.com/julia-dataframes-cheat-sheets/>
  - [Blue Green deployment](https://docs.cloudfoundry.org/devguide/deploy-apps/blue-green.html).
  - Ansible forks with `-f` option.
    - More on Ansible performance tuning - <https://www.ansible.com/blog/ansible-performance-tuning>.

- 2020-01-22
  - [Semantic Patches for Java Program Transformation](https://doi.org/10.4230/LIPIcs.ECOOP.2019.22) - this is a port of [Coccinelle](http://coccinelle.lip6.fr/) for Java.

- 2020-01-23
  - [Lua named arguments](https://www.lua.org/pil/5.3.html)

- 2020-01-24
  - Screen window splitting - <https://tomlee.co/2011/10/gnu-screen-splitting/>
    - Unlike on `tmux` a shell has to be spawned explicitly after splitting.
    - To do a vertical split - `Ctrl+a |` then `Ctrl+TAB` to go to the other
      split. Then as usual, use `Ctrl+a c` to create a window.
    - For a horizontal split use `Ctrl+a S`.

- 2020-01-25
  - [enchive - Encrypted personal archives](https://github.com/skeeto/enchive) - this is a tool from [Chris Wellons](https://nullprogram.com/).
