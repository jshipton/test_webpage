.. _numerical_analysis:

Numerical analysis
==================

What is numerical analysis?
---------------------------

We will see throughout this module that we can solve the same problem
using different numerical methods. Given that we can write down a
variety of numerical methods, it is important to understand what
*errors* are made when applying each one.  Since none of these methods
will generally give exact answers, if we have two numerical methods
for solving the same problem, we need to understand the size of the
errors to know which method is superior.

The analysis of numerical methods, their errors and other properties, forms the
subject of *numerical analysis*, which is an important and vigorous topic in
mathematics and computation.

Taylor–Maclaurin series
-----------------------

Suppose we have a function :math:`f(x)` with derivative :math:`f'(x)`. Given a
point :math:`x = a` and we wish to approximate :math:`f(a + h)` for nearby
points :math:`x = a + h` (with :math:`h` small), then we can approximate:

**Linear approximation:** :math:`f(a + h) \simeq f(a) + h f'(a)`

**Quadratic approximation:**
:math:`f(a + h) \simeq f(a) + h f'(a) + \frac{h^2}{2} f''(a)`

For better approximations, we use the **Taylor-Maclaurin series**:

.. math::

   f(a + h) = f(a) + h f'(a) + \frac{h^2}{2!}f''(a)
   + \frac{h^3}{3!}f'''(a) + \ldots + \frac{h^n}{n!} f^{(n)}(a) + \ldots

Taylor's theorem
----------------

If the function :math:`f(x)` is differentiable at least :math:`n+1` times at a
point :math:`x = a`, then values of :math:`f` near to :math:`a` are given by:

.. math::

   f(a + h) = f(a) + h f'(a) + \frac{h^2}{2}f''(a) + \ldots
   + \frac{h^n}{n!} f^{(n)}(a) + O(h^{n+1})

The notation :math:`O(h^{n+1})` means a quantity that tends to zero like a
constant times :math:`h^{n+1}` when :math:`h` tends to zero. It is a convenient
way to give the key information needed about the 'error term'.

**Rule of thumb:** If the error term is :math:`\varepsilon = O(h^2)`, then if
we halve :math:`h` the error :math:`\varepsilon` is multiplied by a quarter. A
scheme with :math:`O(h^2)` error is superior to one with :math:`O(h)` error,
when halving :math:`h` only halves the error.
