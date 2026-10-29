# Number Theory Explorer

A menu-driven Python program for exploring classic number theory algorithms. Each tool prints its work step by step, so you can see *how* the answer is reached, not only what it is.

Course: Programming with Python

## Tools

| # | Tool | Algorithm |
|---|------|-----------|
| 1 | Primes up to n | Sieve of Eratosthenes (optionally shown round by round) |
| 2 | Prime factorization | Trial division, plus divisor count, divisor sum and Euler's totient |
| 3 | GCD, LCM, Bezout coefficients | Euclid's algorithm and the extended Euclidean algorithm |
| 4 | Modular power `a^b mod m` | Square-and-multiply (fast exponentiation) |
| 5 | Modular inverse | Extended Euclid |
| 6 | Collatz sequence | Iteration of n/2 or 3n+1 |
| 7 | Toy RSA | Key generation, encryption and decryption with small primes (not secure) |

## Requirements

Python 3.9 or newer. No third-party packages.

## Run it

Interactive menu:

```
python main.py
```

Or run one tool directly:

```
python main.py primes 100 --steps
python main.py factor 360
python main.py gcd 252 198
python main.py powmod 7 129 13
python main.py inverse 3 11
python main.py collatz 27
python main.py rsa 61 53 --message 65
```

## Run the tests

```
python -m unittest -v
```

## Files

| File | Purpose |
|------|---------|
| `number_theory.py` | All the algorithms, as pure functions (no printing, no input) |
| `main.py` | Menu and command-line interface, input validation, output formatting |
| `test_number_theory.py` | Unit tests for the algorithms |
| `test_main.py` | Tests for the command-line interface and the menu |

## Design notes

- Algorithms are kept separate from the interface so they can be tested on their own and reused.
- Invalid input never crashes the program: the menu asks again, and direct commands print a one-line error and exit with status 1.
- Results are cross-checked in the tests against Python's own `math.gcd`, `math.lcm` and `pow()`, and against brute-force counting.
"# legendary-sniffle" 
