# Python Performance

- [Loop optimisation](https://www.python.org/doc/essays/list2str/)
- Avoid manual looping - use generators or list comprehensions and high level
  functions like map where possible.
- Generators are lazy and if it fits the use case generally prefer them over
  list comprehensions. This choice might depend on Python version as well.
