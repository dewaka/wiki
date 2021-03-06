# Prolog Cookbook 

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
- Aggregate counting in SWI-Prolog,
  
  ```prolog
  likes(jimmy, anna).
  likes(paul, anna).
  likes(jimmy, paul).

  popular(X) :- aggregate(count, Y^likes(Y,X), N), N > 1.
  ```
  
  Here, `popular` function checks whether given person is liked by more than one
  person. In the definition `Y` is existentionally qualified.
  
  References - <https://stackoverflow.com/questions/5930340/aggregate-3-in-swi-prolog/5930420>
- Higher order functions,

  ```prolog
  double(X, Y) :- Y is X + X.
  pow2(X, Y) :- Y is X * X.
  
  map([], _, []).
  map([X|Xs], P, [Y|Ys]) :-
    call(P, X, Y),
    map(Xs, P, Ys).
    
  ;; Examples
  map([1,  2, 3], double, Xs). ;; Xs = [1, 4, 6]
  map([1, -2, 3],   pow2, Xs). ;; Xs = [1, 4, 9]
  ```
- Checking whether a predicate exists -
  https://stackoverflow.com/questions/12886179/prolog-how-to-check-if-a-predicate-exists.
  
  ```prolog
  current_predicate(map/3). ;; checks whether map which takes 3 parameters exists
  ```
- Define contains based on append function,
  ```prolog
  append([], Ys, Ys).
  append([X|Xs], Ys, [X|Zs]) :- append(Xs, Ys, Zs).

  prefix(P, L) :- append(P, _, L).
  suffix(S, L) :- append(_, S, L).

  contains(SubL, L) :- suffix(S, L), prefix(SubL, S), !.
  ```
- Palindrome check in Prolog is quite nice,
  ```prolog
  palindrome(Xs) :- reverse(Xs, Xs).
  ```

  In a restricted set, we can even use this declarative definition to generate
  palindromes, as in the following example!
  
  ```prolog
  member(X, [1, 2, 3]),
  member(Y, [10, 11, 12]),
  member(Z, [1, 2]),
  palindrome([X, Y, Z]).
  ```
- Fizz buzz in Prolog,

  ```prolog
  print_fizz_buzz(N) :- (
      0 is mod(N, 15) -> write("fizzbuzz"),nl
      ;
      0 is mod(N, 3) -> write("fizz"), nl
      ;
      0 is mod(N, 5) -> write("buzz"), nl
      ;
      write(N), nl
      ).
  
  
  fizz_buzz(N) :- aux_fizz_buzz(0, N).
  aux_fizz_buzz(M, N) :- M < N, print_fizz_buzz(M), M1 is (M + 1), aux_fizz_buzz(M1, N).
  aux_fizz_buzz(M, N) :- M >= N, !, nl.
  ```

- `current_op` can be used to find out precedence and type of an operator.
  Example, to find out these information about `mod`,

  ```prolog
  current_op(Precedence, Type, mod).
  ```
  
  In true Prolog fashion, one can find out all the operators which are curently
  definied using something like follows,
  
  ```prolog
  current_op(Precedence, Type, Op).
  ```
  
  which will list all the opeartors with their respective precedence and type.
- Permutations,

  ```prolog
  take([H|T], H, T).
  take([H|T], R, [H|S]) :- take(T, R, S).

  perm([], []).
  perm(List, [H|T]) :- take(List, H, R), perm(R, T).
  ```
