# horners_algorithm


Horner's algorithm is an efficient method for evaluating polynomials. It reduces the computational complexity by minimizing the number of multiplications and additions required. This algorithm is particularly useful when dealing with polynomials of high degree.


A polynomial of degree n can be represented as:
P(x) = a_n * x^n + a_(n-1) * x^(n-1) + ... + a_1 * x + a_0
Where:
a_n, a_(n-1), ..., a_1, a_0 are the coefficients of the polynomial.
x is the variable.

The key idea of Horner's method is to rewrite the polynomial in a nested form, which allows the polynomial to be evaluated with fewer operations:
P(x) = (...((a_n * x + a_(n-1)) * x + a_(n-2)) * x + ...) * x + a_0
This form reduces the number of multiplications required to evaluate the polynomial from n(n+1)/2 (using the naive method) to n.


Given the polynomial:
P(x) = a_n * x^n + a_(n-1) * x^(n-1) + ... + a_1 * x + a_0

We start by setting:
result = a_n
Then, for each coefficient from a_(n-1) down to a_0, we update the result by:
result = result * x + a_(n-1)
result = result * x + a_(n-2)
...
result = result * x + a_0

After the final step, result will contain the value of P(x).


Mathematically, Horner's method allows us to evaluate the polynomial as follows:
P(x) = a_n * x^n + a_(n-1) * x^(n-1) + ... + a_1 * x + a_0
     = a_n * (x^n + a_(n-1)/a_n * x^(n-1) + ... + a_1/a_n * x + a_0/a_n)
     = (((a_n * x + a_(n-1)) * x + a_(n-2)) * x + ... + a_1) * x + a_0
The transformation from the general polynomial form to the nested form reduces the computational complexity.

Complexity:
The time complexity of Horner's method is O(n) for a polynomial of degree n, because it requires n multiplications and n additions.
