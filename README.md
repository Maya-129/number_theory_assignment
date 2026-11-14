# number_theory_assignment
Name: Mst. Maya Khatun
ID: IT23026

colab-link: https://colab.research.google.com/drive/1iSrzhgeag_EOovoaR-iGOLLmvoirtRJf#scrollTo=1f_BFpRXj-ua

Extended Euclidean Algorithm:
The implementation of the Extended Euclidean Algorithm to calculate the Greatest Common Divisor (GCD) of two integers and find two integers x and y such that ax+by= gcd(a,b). The algorithm is implemented using recursion in Python. 
First, it checks the base condition: if b=0, the function returns (a,1,0), because the GCD of a and 0 is a. Otherwise, the function recursively calls itself with b and a and b mod a to calculate the GCD and the corresponding coefficients. After that, it calculates the new coefficients using the formulas x=y1 and y=x1-(a//b). y1. Finally, it returns three values: the GCD, x, and y.

Example: For the input a=30 and b=18, the function returns (6, -1, 2). To verify the result, we substitute the values into the equation:
 30(-1)+18(2)= -30+36=6 
Therefore, the GCD is 6, x=-1, and y=2. The result satisfies Bézout's identity, confirming that the Extended Euclidean Algorithm has been implemented correctly


2. The relationship between GCD and LCM
   
a connection between LCM and GCD, write an efficient algorithm for finding the least common multiple of two positive integers. 
The relationship between GCD and LCM is:
LCM(a,b)= (a. b)/GCD(a,b)
The function calculates the Least Common Multiple (LCM) of two positive integers using the relationship between GCD and LCM. First, it calculates the GCD using the Euclidean Algorithm with a while loop. The loop repeatedly replaces the two numbers with the second number and the remainder until the remainder becomes zero. Then, it calculates the LCM by multiplying the original two numbers and dividing the result by their GCD. Finally, the function returns the LCM as an integer.

4. Diophantine Equation Using Extended Euclidean Algorithm
   
To find two integers x and y satisfying the linear Diophantine equation:
ax+by=c 
Since a solution is guaranteed to exist, we first calculate the GCD of a and b using the Extended Euclidean Algorithm. Then we multiply the coefficients obtained from the algorithm by c/gcd(a,b) to get the required solution


6. Modular Inverse Using Extended Euclidean Algorithm

To calculate the modular inverse of an integer a modulo n and use it to perform modular division. The modular inverse exists when gcd(a,n)=1.
Explanation:
The function calculates the modular inverse of a modulo n using the Extended Euclidean Algorithm. First, it calls extended_gcd() with the larger number as the first argument because the function requires the first argument to be greater than or equal to the second argument. It then selects the coefficient corresponding to a, which represents the modular inverse. The inverse is converted into a non-negative integer using the modulo operator. In the divide() function, the modular inverse is calculated and multiplied by b, and the result is taken modulo n. Finally, the function returns an integer x satisfying the modular division condition.


8. Fast Modular Exponentiation
   
The Fast Modular Exponentiation algorithm calculates b^e mod m efficiently using the square-and-multiply method. First, it initializes the result to 1 and reduces the base modulo m. Then, it repeatedly checks whether the exponent is odd or even. If the exponent is odd, the current base is multiplied by the result, and the remainder is stored. After that, the base is squared modulo m, and the exponent is divided by 2 using integer division. This process continues until the exponent becomes zero. Finally, the function returns the calculated result. The algorithm requires approximately 2log2 e modular multiplications, making it much faster than repeated multiplication.


10. Chinese Remainder Theorem (CRT):
    
the Chinese Remainder Theorem used to find a number r that satisfies two modular equations: r r = r1 (mod n1)
 r= r2 (mod n2)
We use the Extended Euclidean Algorithm to calculate the required coefficients.
Explanation:
The Chinese Remainder Theorem is used to find a number that satisfies two modular equations simultaneously. First, the function calls the extended_gcd() function to calculate the GCD of n1 and n2, along with two coefficients x and y satisfying n1.x+n2.y=1. Since the two numbers are distinct coprime integers, their GCD must be 1. Then, the function uses these coefficients and the given remainders to calculate the required number using the Chinese Remainder Theorem formula. Finally, it takes the result modulo n1.n2 to ensure that the returned number satisfies
 0 <= r <n1.n2 .


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


