# Valgrind

Valgrind is super useful for debugging native programs. Valgrind can be used to
uncover memory leaks, concurrency issues and a lot more.

## How valgrind works

- [The design and implementation of Valgrind](https://courses.cs.washington.edu/courses/cse326/05wi/valgrind-doc/mc_techdocs.html)

## Usage

- Checking for memory leaks of a program (`hello`),

  ```sh
  valgrind --leak-check=full ./hello
  ```

  If you see a message like, _All heap blocks were freed -- no leaks are
  possible_, then your program is probably leak free!
