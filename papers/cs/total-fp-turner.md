# Total Functional Programming

- Paper - D. A. Turner - [Total Functional Programming](http://www.jucs.org/jucs_10_7/total_functional_programming/jucs_10_07_0751_0768_turner.pdf) 

## Notes

- Total functional programming _excludes_ the possibility of non-termination.
- `fib` function will *not* compile in Haskell 2010 due to later standard not supporting `n + k` patterns. 
- Haskell 2010 version can be writen as follows,
    ```haskell
    fib n
    | n == 0    = 0
    | n == 1    = 1
    | otherwise = fib (n-1) + fib (n - 2)
    ```
