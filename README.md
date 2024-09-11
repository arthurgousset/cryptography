# Cryptography (Cheat Sheet)

> [!NOTE]  
> This is a cheat sheet on cryptography (mostly notes-to-self). It is incomplete by default.

## FAQ

### What does it mean for a prime number to be 2048-bit in size?

Source: ChatGPT

When we say that a prime number is **2048-bit in size**, it means that the prime number can be
represented using up to 2048 binary digits (bits). In other words, the prime number has a value that
fits within the range of numbers representable by 2048 bits.

#### Understanding Bit Length

The bit length of a number is the number of binary digits required to represent that number. Each
bit can either be a 0 or a 1, so a 2048-bit number can represent any integer from $0$ to
$2^{2048} - 1$. In decimal terms, this is a very large number: approximately $3.23 \times
10^{616}$.

#### Prime Number Context

Prime numbers are numbers greater than 1 that have no divisors other than 1 and themselves. A
**2048-bit prime number** would be a prime that lies in the range of numbers that can be represented
with 2048 bits. This means its decimal value would be somewhere between: $2^{2047} \quad \text{(the
smallest 2048-bit number)} \quad \text{and} \quad 2^{2048} - 1 $ This range includes large prime
numbers used in cryptographic algorithms, such as RSA, where prime numbers of such large size are
needed to ensure the security of encryption.

#### Practical Use in Cryptography

In cryptographic systems like RSA, very large primes (such as 2048-bit primes) are used because the
difficulty of factoring the product of two large primes underpins the security of the encryption
algorithm. Finding two 2048-bit prime numbers and multiplying them together yields a number that is
extremely difficult to factor, thus providing strong encryption.

To give an idea of the size:

- The smallest 2048-bit number is $2^{2047}$, approximately equal to $1.7 \times 10^{616}$.
- A random 2048-bit prime would likely have a value somewhere in this range.

#### Example

In binary, a 2048-bit prime might look something like:

```
110100110101... (2048 total bits)
```

In decimal, this would correspond to a very large number, on the order of $10^{616}$.

Thus, a **2048-bit prime number** refers to a prime number that requires 2048 binary digits to
represent, making it extremely large and useful in fields like cryptography, where computational
difficulty is leveraged for security.

### Approximately how many 2048-bit prime numbers are there?

Source: ChatGPT

To estimate how many prime numbers exist in the range of 2048-bit numbers, we can use the **Prime
Number Theorem**. This theorem gives us an approximation of the number of primes less than or equal
to a given number $n$. Specifically, the Prime Number Theorem states that the number of primes less
than or equal to $n$, denoted as $\pi(n)$, is approximately:

$\pi(n) \approx \frac{n}{\ln(n)}$

#### Step-by-step estimation:

1. **Range of 2048-bit numbers**:

   - The smallest 2048-bit number is $2^{2047}$.
   - The largest 2048-bit number is $2^{2048} - 1$.

   So, we want to estimate the number of primes in the range $[2^{2047}, 2^{2048}]$.

2. **Approximate number of primes less than $2^{2048}$**: To estimate $\pi(2^{2048})$, we use the
   Prime Number Theorem:

   $\pi(2^{2048}) \approx \frac{2^{2048}}{\ln(2^{2048})}$

   Since $\ln(2^{2048}) = 2048 \ln(2)$, and $\ln(2) \approx 0.693$, we have:

   $\ln(2^{2048}) \approx 2048 \times 0.693 \approx 1419.6$

   Thus, the number of primes less than $2^{2048}$ is approximately:

   $\pi(2^{2048}) \approx \frac{2^{2048}}{1419.6}$

   This is approximately:

   $\pi(2^{2048}) \approx \frac{2^{2048}}{1419.6} \approx 1.18 \times 10^{615}$

3. **Approximate number of primes less than $2^{2047}$**: Similarly, we can estimate $\pi(2^{2047})$
   as:

   $\pi(2^{2047}) \approx \frac{2^{2047}}{\ln(2^{2047})}$

   Using $\ln(2^{2047}) \approx 2047 \times 0.693 = 1418.9$:

   $\pi(2^{2047}) \approx \frac{2^{2047}}{1418.9} \approx 5.9 \times 10^{614}$

4. **Number of primes between $2^{2047}$ and $2^{2048}$**: To estimate the number of primes in the
   range $[2^{2047}, 2^{2048}]$, we subtract $\pi(2^{2047})$ from $\pi(2^{2048})$:

   $\text{Number of primes} \approx \pi(2^{2048}) - \pi(2^{2047}) \approx (1.18 \times 10^{615}) -
   (5.9 \times 10^{614}) $

   As a reminder, to subtract numbers in scientific notation, you first need to express both numbers
   with the same exponent. Since these numbers have different exponents (one is $10^{615}$ and the
   other is $10^{614}$), we need to convert one of the numbers to have the same exponent as the
   other before performing the subtraction.

5. **Equalizing the exponents**:  
   To equalize the exponents, we can rewrite $5.9 \times 10^{614}$ as $0.59 \times 10^{615}$. This
   way, both numbers are expressed with the exponent $10^{615}$.

   Now we have:

   $1.18 \times 10^{615} \quad \text{and} \quad 0.59 \times 10^{615}$

6. **Subtracting the coefficients**:  
   With the exponents equal, you can simply subtract the coefficients (the numbers in front of the
   powers of 10):

   $1.18 - 0.59 = 0.59$

7. **Combine with the shared exponent**:  
   After subtracting the coefficients, you reapply the shared exponent to the result:

   $0.59 \times 10^{615}$

8. This gives approximately:

   $\text{Number of primes} \approx 5.9 \times 10^{614}$

#### Conclusion:

There are approximately $5.9 \times 10^{614}$ (or about 590 quinquagintillion) prime numbers between
$2^{2047}$ and $2^{2048}$. As a reminder, a quinquagintillion is a 1 followed by 615 zeros. This is
an enormous quantity, which is why finding large prime numbers suitable for cryptography is feasible
even though they are very large.
