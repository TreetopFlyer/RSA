# RSA

### Euler's Theorem:

*given P and Q are primes:*  
**N = PQ**  
**Phi(N) = (P-1)(Q-1)**  

*given some integer A < N:*  
**A^( Phi(N)+1 ) % N = A**  

### RSA application:
*We would like to have the following:*  
**Message^Encrypter % N = Cypher**  
**Cypher^Decrypter % N = Message**  
*where*  
**Message^(Encrypter*Decrypter) % N = Message**  
*which is Euler's Theorem*  

Create **N** as a semiprime and choose **Encrypter** as a coprime of **Phi(N)**.  
Therefore **Decrypter** is (**Phi(N)**+1)/**Encrypter** 

### Explanation
Given that **N** and **Encrypter** are made public, as well as any **Cypher**s produced,
the all-important **Decrypter** can be created by *anyone* that can calculate **Phi(N)**.  

However, given a value of **N** that is sufficiently large (excess of 100 digits), **Phi(N)** would take decades to calculate.  

The exception is if you know the **P** and **Q** values used to generate **N** in the first place. Recall Euler's Theorem where, **Phi(N)** is the trivial arithmetic (**P**-1)(**Q**-1). This is why **P**, **Q**, and **Decrypter** *must* be kept secret.

#### Explanation cont.

What is Phi(N) and why is it so hard to calculate?  

Phi is Euler's Totient function: it returns the *number* of integers, greater than 0 and less-than-or-equal-to N, that are coprime with N. There's an easy way to solve it, and a nearly impossible way to solve it.  

The easy way is, *if* you know that N is a product of P and Q, then Phi(N) = (P-1)(Q-1).  

The hard way is to get a computer to do *googles* of greatest-common-denominator calculations in a brute-force trial-and-error method to count all the coprimes buried in a value of N that is hundreds of digits long. And, given a decade or two, it can and will do it :)
