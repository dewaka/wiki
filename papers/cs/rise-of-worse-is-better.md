# The Rise of Worse is Better

- [The Rise of Worse is Better - Richard P. Gabriel](https://web.mit.edu/6.033/www/papers/Worse_is_Better.pdf)

## Notes

- MIT/Standford approach vs the New Jersey approach.

### MIT Approach to Software Development

Common Lisp and CLOS had influence from MIT approach which put emphasis on following principles,

- Simplicity - both interface and implementation must be simple. It is more important that the interface is simple than the implemntation.
- Correctness - the design must be correct in all observable aspects. Incorrectness is simply not allowed.
- Consistency - the design must not be inconsistent. The design is allowed to be slightly less simple and less complete to avoid inconsistency. Consistency is as important as correctness.
- Completeness - the design must cover as many important situations as is practical. All reasonably expected cases must be covered. Simplicity is not allowed to overly reduce completeness.
    
### New Jersey approach to Software Develpment

This is characterised by the _UNIX_ and _C_ programming innovations. This is
called the _worse-is-better_ appraoch by the author.

- Simplicity - both interface and implementation must be simple. It is more important that the implementation is to be simple than the interface.
- Correctness - the design must be correct in all observable aspects. It is slightly better to be simple than correct.
- Consistency - the design must not be overly inconsistent.  Consistency can be sacrificed for simplicity in some cases, but it is better to drop those parts of the design that deal with less common circumstances than to introduce either implementational complexity or inconsistency.
- Completeness - the design must cover as many important situations as is practical. Completeness can be sacrificed in favor of any other quality. In fact, completeness must sacrificed whenever implementation simplicity is jeopardized. Consistency can be sacrificed to achieve completeness if simplicity is retained; especially worthless is consistency of interface.

UNIX and C are descendents of the _worse-is-better_ approach.
- They are easy to port because implementation is _simple_.
- Since they cater to the common use case, they are optimised to run from smallest computers to the largest ones.
- Author compares the spread of UNIX and C programming to a spread of a virus.
- Author also compares Common Lisp as an example of a big complex systems scenario with a monolith (static) design and the design of Scheme to a diamond-lie jewel.
- Author contends that even though C is _worse-is-better_ type of language it is not the right tool for AI software.
