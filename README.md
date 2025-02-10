# Totient multiplicativity proof for integers

## Totient for powers of primes

<p>
  
  Up to this point we know that $\phi(p) = p - 1$, if $p$ is prime, and that the multiplicative property holds between primes. Now we want to extend the property to non-primes. We know that every non-prime is a product of powers of primes, then the first thing to do is know how the Totient function behaves for powers of primes.
  
Let's take $p^{k}$. We need to calc. the number of coprimes. To solve this in the easiest way possible we can make a slight abstraction and consider $\phi(p)$ as the number of elements of the set $\\{1, 2, \dots, p \\}$ minus the set of multiples of $p$, which for $\phi(p^{1})$ reduces to have 

$\phi(p^{1}) = \phi(p) = |\\{ 1, 2, \dots, p \\} \setminus \\{ p \\}| =  p - 1$

Let's now take for example $\phi(2p)$ into consideration, following our reasoning we have

$\phi(2p) = |\\{ 1, 2, \dots, 2p \\} \setminus \\{ p, 2p \\}| = 2p - 2$

and for $\phi(3p)$

$\phi(3p) = |\\{ 1, 2, \dots, 3p \\} \setminus \\{ p, 2p, 3p \\}| = 3p - 3$

thus, we will have that

$\phi(pp) = \phi(p^{2}) = |\\{ 1, 2, \dots, p^{2} \\} \setminus \\{ p, 2p, 3p, \dots, p^{2} \\}| = p^{2} - p$

Now, let's restart from $p^{2}$, we can see that

$\phi(2p^{2}) = |\\{ 1, 2, \dots, 2p^{2} \\} \setminus \\{ p, 2p, 3p, \dots, p^{2}, p^{2} + p, p^{2} + 2p, p^{2} + 3p, \dots, 2p^{2} \\}| = 2p^{2} - 2p$

then

$\phi(pp^{2}) = \phi(p^{3}) = p^{3} - p^{2}$

and we can formalyze this as

$\phi(p^{k}) = p^{k} - p^{k - 1} = p^{k - 1}(p - 1)$

This is quite hard to figure out and so I'll show another example before going over.

$\phi(2p^{3}) = |\\{ 1, 2, \dots, 2p^{3} \\} \setminus \\{ p, 2p, 3p, \dots, p^{2}, p^{2} + p, p^{2} + 2p, p^{2} + 3p \dots, 2p^{2}, 2p^{2} + p, 2p^{2} + 2p, 2p^{2} + 3p, \dots, 3p^{2}, \dots, p^{3}, p^{3} + p, p^{3} + 2p, p^{3} + 3p, \dots, p^{3} + p^{2}, p^{3} + p^{2} + p, p^{3} + p^{2} + 2p, p^{3} + p^{2} + 3p, \dots, p^{3} + 2p^{2}, \dots, 2p^{3} \\}| = 2p^{3} - 2p^{2}$

To get this last one, just notice how the reasoning up to $p^{3}$ is almost straightforward (it's doable to figure out we have $p^{2}$ elements to remove), then we basically restart from the beginning at $p^{3} + p$, and so we get $2p^{2}$ elements to remove. Then for $pp^{3}$ we will have $pp^{2}$ elements to remove and so on towards infinity.

</p>

## Multiplicativity extends Totient to integers

<p>
  
  We know that multiplicativity holds for primes, but here we have $\phi(p^{k}) = p^{k} - p^{k - 1}$ where $p^{k}$ is not a prime.<br>
If we manage to prove that multiplicativity holds for powers of primes we can multiply $\phi(p^{k})$ for every $p_{i}, k_{i}$ and derive the property for integers.
  
</p>

### Example: $\phi(2^{20}5^{15})$

<p>
  
 ![Scheme](Scheme_fixed.png) 

It's quite clear that removing co-factors will be harder. Now we will have to remove all the columns and lines which are mults of $2$ and $5$, and for every line and column removed we will need to remove intersections. Looking at this scheme it's easy to see that $2^{19} × 5^{15}$ columns are removable. It's not the same for $5^{14} × 2^{20}$. To remove the latter we will need swaps. Of course this time it won't be possible to show the complete picture and the reasoning will need to abstract the image representation. <br>
We already know that there are $5^{14}$ elements among lines to be removed. The multiplication by $2^{20}$ is not really trivial too: all these cofactors are mutiplied by all numbers from $1$ to $2^{20}$ and the products are obviously elements which share $5$ co-factor and then they all need to be removed. Then we can imagine swaps between lines which preserve the formalization. $5^{14} × 2^{19}$ is the last term we need to match the formalization and is a consequence of this whole reasoning (intersections).

We know that we will have to remove $2^{20} / 2$ columns $+$ $5^{15} / 5$ lines in total, this means

$(2^{20} / 2) * 5^{15} + (5^{15} / 5) * 2^{20}$ 

and since we will need to sub $1$ for every intersection, we will need to sub $5^{15} / 5 * 2^{20} / 2$, hence obtaining

$\phi(2^{20}5^{15}) = 5^{15} × 2^{20} − ((2^{19} × 5^{15}) + (5^{14} × 2^{20}) − 5^{14} × 2^{19})$

</p>

## Formalization

<p>
  
  $\phi(x^{k}y^{z}) = x^{k}y^{z} - x^{k-1}y^{z} - x^{k}y^{z-1} + x^{k-1}y^{z-1}$<br>
  $x^{k}y^{z} - x^{k-1}y^{z} - x^{k}y^{z-1} + x^{k-1}y^{z-1} = (x^{k} - x^{k-1})(y^{z} - y^{z-1})$<br>
  
  where
  
  $\phi(x^{k}) = x^{k} - x^{k-1}$<br>
  $\phi(y^{z}) = y^{z} - y^{z-1}$</p>

</p>


