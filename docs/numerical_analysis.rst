Interpolation
=============

Suppose we are given some tabulated data, for example temperatures at certain
heights in the atmosphere, and we wish to estimate the temperature at an
intermediate height that is not tabulated. In effect we need to construct a
*mathematical model* for the dependence of temperature on height between the
tabulated values.

**Linear interpolation** is the simplest type of interpolation, which fits a
straight line between each neighbouring pair of data points.

Linear interpolation formula
----------------------------

Given two neighbouring data points :math:`(x_1, y_1)` and :math:`(x_2, y_2)`,
the equation of the straight line passing through these points is:

.. math::

   y = \frac{(x - x_1)y_2 + (x_2 - x)y_1}{x_2 - x_1}

Thus, an estimate :math:`\hat{y}` for the value of :math:`y` at
:math:`x = \hat{x}` is given by:

.. math::

   \hat{y} = \frac{(\hat{x} - x_1)y_2 + (x_2 - \hat{x})y_1}{x_2 - x_1}

The closer our given data points are to each other, the more accurate we might
expect our interpolated value to be.

Numerical analysis
==================

What is numerical analysis?
---------------------------

We have met the numerical process of *linear interpolation* for estimating
values of a function given some dataset. Although we can write down a variety
of numerical methods, one key aspect is to understand what *errors* are made.
Since none of these methods will generally give exact answers, if we have two
numerical methods for solving the same problem, we need to understand the size
of the errors to know which method is superior.

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

Convergence of linear interpolation
-----------------------------------

Let us illustrate these ideas by looking at the error we make when we apply
linear interpolation to a smooth function :math:`f(x)`. If we have data points
at :math:`x = x_1` and :math:`x = x_2` with :math:`h = x_2 - x_1`, then clearly
the error goes down as we reduce :math:`h`, but we need some theory to
establish the order of this numerical method.

Suppose :math:`f(x)` is at least twice differentiable in the interval
:math:`[x_1, x_2]`. The interpolation error is the difference between the
interpolated value :math:`\hat{f}(\hat{x})` and the true value
:math:`f(\hat{x})`. We wish to know how the interpolation error behaves as
:math:`h \rightarrow 0`. We say that the interpolation *converges* if
:math:`\hat{f}(\hat{x}) - f(\hat{x}) \rightarrow 0` as
:math:`h \rightarrow 0`.
