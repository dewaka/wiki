# args4j - Java command line arguments parsing

## Usage examples

- Required single argument,

  ```java
  @Option(name="-name",usage="Sets a name")
  public String name;
  ```

- Comma seperated arguments,

  ```java
  @Option(name = "--files", required = true, handler = CSVStringOptionHandler.class)
  private List<String> files;
  ```

- Boolean or flag arguments,

  ```java
  @Option(name = "--dryrun", handler = ExplicitBooleanOptionHandler.class)
  private boolean dryRun;
  ```
