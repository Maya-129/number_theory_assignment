# number_theory_assignment
Name: Mst. Maya Khatun
ID: IT23026

colab-link: https://colab.research.google.com/drive/1iSrzhgeag_EOovoaR-iGOLLmvoirtRJf?usp=sharing

1.Extended Euclidean Algorithm:

The implementation of the Extended Euclidean Algorithm to calculate the Greatest Common Divisor (GCD) of two integers and find two integers x and y such that ax+by= gcd(a,b). The algorithm is implemented using recursion in Python.

First, it checks the base condition:
if b=0, the function returns (a,1,0), because the GCD of a and 0 is a. Otherwise, the function recursively calls itself with b and a and b mod a to calculate the GCD and the corresponding coefficients. After that, it calculates the new coefficients using the formulas x=y1 and y=x1-(a//b). y1. Finally, it returns three values: the GCD, x, and y.

Example:
For the input a=30 and b=18, the function returns (6, -1, 2). To verify the result, we substitute the values into the equation:
 30(-1)+18(2)= -30+36=6 
Therefore, the GCD is 6, x=-1, and y=2. The result satisfies Bézout's identity, confirming that the Extended Euclidean Algorithm has been implemented correctly


2. The relationship between GCD and LCM
   
a connection between LCM and GCD, write an efficient algorithm for finding the least common multiple of two positive integers. 
The relationship between GCD and LCM is:
LCM(a,b)= (a. b)/GCD(a,b)
The function calculates the Least Common Multiple (LCM) of two positive integers using the relationship between GCD and LCM. First, it calculates the GCD using the Euclidean Algorithm with a while loop. The loop repeatedly replaces the two numbers with the second number and the remainder until the remainder becomes zero. Then, it calculates the LCM by multiplying the original two numbers and dividing the result by their GCD. Finally, the function returns the LCM as an integer.

3. Diophantine Equation Using Extended Euclidean Algorithm
   
To find two integers x and y satisfying the linear Diophantine equation:
ax+by=c 
Since a solution is guaranteed to exist, we first calculate the GCD of a and b using the Extended Euclidean Algorithm. Then we multiply the coefficients obtained from the algorithm by c/gcd(a,b) to get the required solution


4. Modular Inverse Using Extended Euclidean Algorithm

To calculate the modular inverse of an integer a modulo n and use it to perform modular division. The modular inverse exists when gcd(a,n)=1.
Explanation:
The function calculates the modular inverse of a modulo n using the Extended Euclidean Algorithm. First, it calls extended_gcd() with the larger number as the first argument because the function requires the first argument to be greater than or equal to the second argument. It then selects the coefficient corresponding to a, which represents the modular inverse. The inverse is converted into a non-negative integer using the modulo operator. In the divide() function, the modular inverse is calculated and multiplied by b, and the result is taken modulo n. Finally, the function returns an integer x satisfying the modular division condition.


5. Fast Modular Exponentiation
   
The Fast Modular Exponentiation algorithm calculates b^e mod m efficiently using the square-and-multiply method. 
First, it initializes the result to 1 and reduces the base modulo m. Then, it repeatedly checks whether the exponent is odd or even. If the exponent is odd, the current base is multiplied by the result, and the remainder is stored. After that, the base is squared modulo m, and the exponent is divided by 2 using integer division. This process continues until the exponent becomes zero. Finally, the function returns the calculated result. The algorithm requires approximately 2log2 e modular multiplications, making it much faster than repeated multiplication.


6. Chinese Remainder Theorem (CRT):
    
the Chinese Remainder Theorem used to find a number r that satisfies two modular equations: r r = r1 (mod n1)
 r= r2 (mod n2)
We use the Extended Euclidean Algorithm to calculate the required coefficients.
Explanation:
The Chinese Remainder Theorem is used to find a number that satisfies two modular equations simultaneously. First, the function calls the extended_gcd() function to calculate the GCD of n1 and n2, along with two coefficients x and y satisfying n1.x+n2.y=1. Since the two numbers are distinct coprime integers, their GCD must be 1. Then, the function uses these coefficients and the given remainders to calculate the required number using the Chinese Remainder Theorem formula. Finally, it takes the result modulo n1.n2 to ensure that the returned number satisfies
 0 <= r <n1.n2 .

7.Fermat's Little Theorem:
Statement:
Let p be a prime and let a be an integer with p∤ a (equivalently gcd (a, p)=1). Then
A^p−1 ≡ 1(mod p).
Corollary (multiply by a). For every integer a(including multiples of p),
a^ p ≡a (mod p).

Proof (group-theoretic / permutation argument)
Consider the p−1nonzero residues mod p: 1,2,… p−1. Since gcd (a ,p)=1, multiplication by a permutes this set:
a⋅1,  a⋅2,  …,  a⋅(p−1)(mod p)
is again exactly the set {1,…,p−1} (if ai ≡ aj then a(i−j)≡0 and since a is invertible mod p, i≡j). Therefore the products of the two lists are congruent:
a^p−1(p−1) !≡ (p−1)!    (mod p)
Since (p−1)! is coprime to p, we may cancel it, giving 
a^p−1 ≡1  (mod p)

import random
def fermat_check(n, a):
    return pow(a, n - 1, n) == 1

def fermat_test(n, trials=20):
    if n < 2: return False
    if n in (2, 3): return True
    if n % 2 == 0: return False
    for _ in range(trials):
        a = random.randint(2, n - 2)
        if not fermat_check(n, a):
            return False        # witness to compositeness
    return True                 # probable prime


8.Euler's Totient Function:
 Definition
For a positive integer n, Euler's totient function φ(n) is defined as the number of integers k in the range 1≤k≤n such that gcd (k, n)= 1. In other words, φ(n) counts how many numbers up to n are coprime to n .
Since Day 1 established that gcd (a,b) is well-defined and computable via Euclid's algorithm, φ(n) can be computed naively by counting:

def phi_naive(n):
    assert n >= 1
    count = 0
    for k in range(1, n + 1):
        if gcd(k, n) == 1:      # gcd from Day 1 (Euclid's algorithm)
            count += 1
    return count

9.Euler's Theorem
Statement
Let n≥1 and let a be an integer with gcd (a,n)=1  Then
aφ(n) ≡ 1 (mod n).
Fermat's Little Theorem is the special case n=p  prime, since φ(p)=p−1




Problem 1: Repunit Numbers and Prime Numbers

Find the set Ap, where p is prime and p| a(n).
Recall:
 a(n)=( 10^n -1) /9


Problem 2: Even Perfect Numbers

Generate even perfect numbers using the formula:
k=2^(n-1).(2^n -1) 
where 2^n -1 is prime.


Problem 3: Infinitely Many Fermat Pseudoprimes

Construct composite numbers n satisfying:
a^(n-1)= 1 (mod n )
For a fixed integer a>=2, choose odd primes p such that p|(a^2 -1), and construct:
n=( a^(2p)-1)/(a^2 -1)


