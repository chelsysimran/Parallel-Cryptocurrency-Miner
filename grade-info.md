# Grade Information

## Test 1: Compilation

No dead/leftover/unnecessary code should be highlighted here. [1 pts]

```
+ gcc -Wall -g -pthread -std=c99 mine.c -o mine
+ test_end
+ return=0
+ [Output Lines: 0]
+ [Time elapsed: 0.0943699]
```

## Test 2: Invalid number of threads

```
+ timeout 5 ./mine 0 1 'this is a test'
Difficulty Mask: 01111111111111111111111111111111
+ test_end
+ return=1
+ [Output Lines: 1]
+ [Time elapsed: 0.0192001]
```

## Test 3: Invalid difficulty I

```
+ timeout 5 ./mine 1 -5 'this is a test'
Difficulty Mask: 11111111111111111111111111111111
Number of threads: 1
..
Solution found by thread 0:
Nonce: 0
Hash: F72EFCE3D41ED1615327D9FAE17E99C3AC866B62
0 hashes in 0.02s (0.00 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 0.0438499]
```

## Test 4: Invalid difficulty II

```
+ timeout 5 ./mine 1 50 'this is a test'
Difficulty Mask: 00000000000000000000000000000000
Number of threads: 1
.......+ test_end
+ return=124
+ [Output Lines: 3]
+ [Time elapsed: 5.02083]
```

## Test 5: Difficulty Calculation

```
+ timeout 5 ./mine 1 1 'this is a test'
Difficulty Mask: 01111111111111111111111111111111
Number of threads: 1
..
Solution found by thread 0:
Nonce: 1
Hash: 6DE0956F29E6A2412F4CCA4C2CDDA38F640688BE
0 hashes in 0.02s (0.00 hashes/sec)
+ timeout 5 ./mine 1 2 'this is a test'
Difficulty Mask: 00111111111111111111111111111111
Number of threads: 1
..
Solution found by thread 0:
Nonce: 9
Hash: 05041C0563085614A00F3E3BE2FD8E8DFC53FFE2
0 hashes in 0.02s (0.00 hashes/sec)
+ timeout 5 ./mine 1 4 'this is a test'
Difficulty Mask: 00001111111111111111111111111111
Number of threads: 1
..
Solution found by thread 0:
Nonce: 9
Hash: 05041C0563085614A00F3E3BE2FD8E8DFC53FFE2
0 hashes in 0.02s (0.00 hashes/sec)
+ timeout 5 ./mine 1 10 'this is a test'
Difficulty Mask: 00000000001111111111111111111111
Number of threads: 1
..
Solution found by thread 0:
Nonce: 365
Hash: 00232C20F5C1515D9941C6D064F6113AFC257B8A
0 hashes in 0.02s (0.00 hashes/sec)
+ timeout 5 ./mine 1 17 'this is a test'
Difficulty Mask: 00000000000000000111111111111111
Number of threads: 1
...
Solution found by thread 0:
Nonce: 94812
Hash: 000064550882C04EAB59A44C84E7B9D3861E8C92
0 hashes in 0.11s (0.00 hashes/sec)
+ timeout 5 ./mine 1 32 'this is a test'
Difficulty Mask: 00000000000000000000000000000000
Number of threads: 1
.......+ test_end
+ return=124
+ [Output Lines: 38]
+ [Time elapsed: 5.25763]
```

## Test 6: Single thread run

With one thread, the number of hashes should (roughly) equal the nonce.

```
+ timeout 10 ./mine 1 21 'testing testing 1 2 3'
Difficulty Mask: 00000000000000000000011111111111
Number of threads: 1
....
Solution found by thread 0:
Nonce: 1702342
Hash: 000000B9810F2B8F5D0A34CBCD29574093B3E3F7
1000000 hashes in 1.83s (545291.96 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 1.85653]
```

## Test 7: Input String: testing testing 1 2 3

```
+ timeout 60 ./mine 8 24 'testing testing 1 2 3'
Difficulty Mask: 00000000000000000000000011111111
Number of threads: 8
..........
Solution found by thread 6:
Nonce: 1702342
Hash: 000000B9810F2B8F5D0A34CBCD29574093B3E3F7
1000000 hashes in 1.41s (707510.85 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 2.06565]
```

## Test 8: Input String: iewoijeoiwfjwiojpqwjj

```
+ timeout 5 ./mine 1 22 iewoijeoiwfjwiojpqwjj
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 1
......
Solution found by thread 0:
Nonce: 3168785
Hash: 0000016372746C5082E89AE5928F2240E6510B64
3000000 hashes in 3.39s (883730.76 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 3.41716]
```

## Test 9: Input String: what what what what what what what

```
+ timeout 5 ./mine 4 10 'what what what what what what what'
Difficulty Mask: 00000000001111111111111111111111
Number of threads: 4
..
Solution found by thread 0:
Nonce: 36
Hash: 001ACDB3672251A8B9DFB362969ECB0F9BCF2407
0 hashes in 0.02s (0.00 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 0.0438099]
```

## Test 10: Input String: hellooooooooooo world!

```
+ timeout 5 ./mine 8 3 'hellooooooooooo world!'
Difficulty Mask: 00011111111111111111111111111111
Number of threads: 8
..
Solution found by thread 1:
Nonce: 1
Hash: 07BDF4385CFCE9372851FD051CE9777C4C02E6F2
0 hashes in 0.02s (0.00 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 0.0439701]
```

## Test 11: Input String: long computation

```
+ timeout 5 ./mine 8 22 'long computation'
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 8
..........
Solution found by thread 1:
Nonce: 3074929
Hash: 00000225B93963B335FA91EF5F339A2ECA04AA53
1000000 hashes in 0.19s (5256599.73 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 7]
+ [Time elapsed: 1.90688]
```

## Test 12: Baseline (single thread) vs four threads

```
+ timeout 10 ./mine 1 22 'Hello CS220!'
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 1
....
Solution found by thread 0:
Nonce: 1079495
Hash: 000002FEE38B31856A2F75732B0297F98AC6FE6B
1000000 hashes in 1.14s (876604.04 hashes/sec)
+ timeout 10 ./mine 4 22 'Hello CS220!'
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 4
......
Solution found by thread 3:
Nonce: 1079495
Hash: 000002FEE38B31856A2F75732B0297F98AC6FE6B
1000000 hashes in 0.12s (8651260.26 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 14]
+ [Time elapsed: 2.34651]
```


## Deductions

* (Test 4): Ran anyway [-1]
* (Test 6): Incorrect hash count [-1]

