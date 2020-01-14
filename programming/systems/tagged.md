# Tagged Pointers

- Tagged pointers - <https://en.wikipedia.org/wiki/Tagged_pointer> 
- [mikeash.com: Friday Q&A 2012-07-27: Let's Build Tagged Pointers](https://www.mikeash.com/pyblog/friday-qa-2012-07-27-lets-build-tagged-pointers.html)

- What is pointer alignment?
  Most computer architectures have a concept of _pointer alignment_ where a pointer to a data type should be a multiple of some power of two. This fact is what enables pointer tagging which makes use of "unused" bits in pointer values.
