# TIL June, 2020

- 2020-06-12
  - [tai64nlocal](https://cr.yp.to/daemontools/tai64nlocal.html) is pretty useful when viewing logs through tail command to get readable timestamps on log lines.
    Example usage,
    ```
    tail -F /var/program/log | tai64nlocal
    ```
