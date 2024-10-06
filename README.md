# Extending the power of Totient function
<p>Up to this point we know that $\phi(x)$ where x is prime is = x - 1, and that the multiplicative property holds between primes.<br>
Now we want to extend this to non-primes. We know that every non-prime is a product of powers of primes, then the first thing to do is know how the Totient function behaves for powers of primes. <br>
Let's take $p^{k}$. We need to calc. n. of coprimes. <br>
To solve this in the easiest way possible we can remove those we are sure are not coprimes (divisors).
Every number multiplied by 'p' which produces $p^{k}$ is not coprime to $p^{k}$, while every other number from 1 to $p^{k}$ is coprime instead, because 'p' is prime and is only mult. by itself.<br>
Then: $n * p = p^{k}$ -> $n = p^{k} / p$ -> $n = p^{k - 1}$
Then: $p^{k-1} are not coprimes -> $p^{k} - p^{k-1} are coprimes.
