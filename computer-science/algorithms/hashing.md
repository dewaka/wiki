# Hashing

## Open address hashing

- [Hashing | Set 3 (Open Addressing) - GeeksforGeeks](https://www.geeksforgeeks.org/hashing-set-3-open-addressing/)

## Cryptographically secure hashing

- [Cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)

## Hash functions

### [FNV Hash](http://www.isthe.com/chongo/tech/comp/fnv/index.html)

The core of the FVN-1 hash algorithm is,

```
hash = offset_basis
for each octet_of_data to be hashed
 hash = hash * FNV_prime
 hash = hash xor octet_of_data
return hash
```

