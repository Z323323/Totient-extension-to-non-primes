# Extending the power of Totient function

<p>Up to this point we know that $\phi(p)$ for $p$ prime is $\phi(p) = p - 1$, and that the multiplicative property holds between primes.<br>
Now we want to extend this to non-primes. We know that every non-prime is a product of powers of primes, then the first thing to do is know how the Totient function behaves for powers of primes. <br>
Let's take $p^{k}$. We need to calc. n. of coprimes. <br>
To solve this in the easiest way possible we can remove those we are sure are not coprimes.
Every number multiplied by $p$ which produces $p^{k}$ is not coprime to $p^{k}$, while every other number from 1 to $p^{k}$ is coprime instead, because $p$ is prime and is only mult. by itself.<br>
Then: $n * p = p^{k}$   ->   $n = p^{k} / p$   ->   $n = p^{k - 1}$ <br>
Then: $p^{k-1}$ are not coprimes -> $p^{k} - p^{k-1}$ are coprimes -> $\phi(p^{k}) = p^{k} - p^{k-1}$ <br> </p>

## Now the ¿hard? stuff

<p>We know that multiplicativity holds for primes, but here we have $\phi(p^{k}) = p^{k} - p^{k-1}$ where $p^{k}$ is not a prime. <br>
If we manage to demonstrate that multiplicativity holds for non-primes (powers of primes actually) we can multiply $\phi(p^{k})$ for every $p_{i}, k_{i}$ and derive the property for non-primes. This will mean being able to calculate Totient for every integer and being sure the calculation is correct. <br>
</p>

## Example: $\phi(2^{20}5^{15})$
<p>Let's look at the new scheme for this example. Making this has helped me a lot in the process. <br>

![Scheme](Scheme4.png)

Here becomes clear that removing co-factors will be harder. The previous reasoning scheme holds but now we will have to remove all the columns and lines which are mults of $2$ and $5$, and for every line and column removed we will need to remove $1$ element considered twice and so intersections will be a huge? problem. So we will need to remove for ex: $5^{15}(2)$ column, which is composed of $5^{15}$ elements which share the $2$ factor, the same goes for $2^{20}(5)$ line, here there will be $2^{20}$ elements to remove because they share the $5$ factor. <br>
We know that we will have to remove $2^{20} / 2$ columns + $5^{15} / 5$ lines in total, this means: $(2^{20} / 2) * 5^{15} + (5^{15} / 5) * 2^{20}$ and since we will need to sub $1$ for every intersection, we will need to sub $5^{15} / 5 * 2^{20} / 2$. Let's write this whole formula:

$\phi(2^{20}5^{15}) = 5^{15} × 2^{20} − ((2^{19} × 5^{15}) + (5^{14} × 2^{20}) − 5^{14} × 2^{19})$ <br></p>

## Formalization

<p>
  $\phi(x^{k}y^{z}) = x^{k}y^{z} - x^{k-1}y^{z} - x^{k}y^{z-1} + x^{k-1}y^{z-1}$<br>
  $x^{k}y^{z} - x^{k-1}y^{z} - x^{k}y^{z-1} + x^{k-1}y^{z-1} = (x^{k} - x^{k-1})(y^{z} - y^{z-1})$<br>
  
  where
  
  $\phi(x^{k}) = x^{k} - x^{k-1}$<br>
  $\phi(y^{z}) = y^{z} - y^{z-1}$</p>

## Refinition of the scheme ensuring formalization is unbreakable
<p>The scheme above is a little bit messy, and looks like it's not following a structured reasoning, this time is going to be harder to make it structured and perform swaps and preserve formalization.
Structured scheme: <br>

![Scheme](Scheme_fixed.png)

Looking at this scheme it's easy to see that $2^{19} × 5^{15}$ columns are removable. It's not the same for $5^{14} × 2^{20}$. To remove the latter we will need swaps. Of course this time it won't be possible to show the complete picture and the reasoning will need to abstract the image representation. <br>
We already know that there are $5^{14}$ elements among lines to be removed. The multiplication by $2^{20}$ is not really trivial too: all these cofactors are mutiplied by all numbers from $1$ to $2^{20}$ and the products are obviously elements which share $5$ co-factor and then they all need to be removed. Then we can easily imagine swaps between lines which preserve the formalization. $5^{14} × 2^{19}$ is the last term we need to match the formalization and is a consequence of this whole reasoning (intersections).



