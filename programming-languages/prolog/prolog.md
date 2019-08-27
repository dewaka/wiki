# Prolog

## Resources

- [Awesome Prolog](https://github.com/klaussinani/awesome-prolog)
- [Simply Logical: Intelligent Reasoning by Example](https://book.simply-logical.space/)
- [The Power of Prolog](https://www.metalevel.at/prolog) and the video
  tutorials at [The Power of Prolog - YouTube](https://www.youtube.com/channel/UCFFeNyzCEQDS4KCecugmotg).

## Snippets

- Classic factorial function,

  ```prolog
  factorial(0, 1).
  factorial(N, N_Fact) :-
      N > 0,
      M is N-1,
      factorial(M, M_Fact),
      N_Fact is M_Fact*N.

  ```

- Fibonacci functions

  ```prolog
  ;; Non tail recursive version - is going to stack overflow quickly
  fib(0, 0).
  fib(1, 1).
  fib(N, N_Fib) :-
      N > 1,
      M is N-1,
      T is N-2,
      fib(M, M_Fib),
      fib(T, T_Fib),
      N_Fib is M_Fib + T_Fib.

  ;; Tail recursive version
  fibonacci(N, N_Fib) :- tfib(N, 0, 1, N_Fib).
  tfib(0, A, _, A).
  tfib(N, A, B, N_Fib) :-
      N > 0,
      Next_N is N-1,
      Next_A is B,
      Next_B is A + B,
      tfib(Next_N, Next_A, Next_B, N_Fib).
  ```
