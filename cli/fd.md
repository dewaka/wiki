# fd

[fd](https://github.com/sharkdp/fd) is a user friendly replacement for
[find](http://man7.org/linux/man-pages/man1/find.1.html).

- How to include hidden files and directories for searches?

  ```sh
  fd 'ipa.*.crt' ~/ -H
  ```
  
- Uses smartcase by default, which means if the search term is in lowercase,
  the search is done in case-insensitive manner. But if the search term contains
  Capital letters the search is done in a case-sensitive manner.


- Find files with a specific extension:

  ```sh
  fd --extension txt
  ```

- Open a file found via `fd`,

  ```sh
  fd 'Math.*.pdf' -x open
  ```
  
  Use `-x` flag for executing a command.
