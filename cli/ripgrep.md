# ripgrep

## Tips

- To list only file paths matching a given query, use `--file-with-matches--`
  option. Example,
  
  ```
  rg --files-with-matches EnableEureka
  ```
  - For case insensitive searches, use `-i` flag.
- Search in specific files. 
  Examples,
  - Search in only gradle files,
    ```
    rg grpc -g '*.gradle'
    ```  
  - Search in non-gradle files,
    ```
    rg grpc -g '!*.gradle'
    ```
