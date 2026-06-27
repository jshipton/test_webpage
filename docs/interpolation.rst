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

Convergence of linear interpolation
-----------------------------------

Let us apply the ideas from :ref:`numerical_analysis` by looking at the
error we make when we apply linear interpolation to a smooth function
:math:`f(x)`. If we have data points at :math:`x = x_1` and :math:`x =
x_2` with :math:`h = x_2 - x_1`, then clearly the error goes down as
we reduce :math:`h`, but we need some theory to establish the order of
this numerical method.

Suppose :math:`f(x)` is at least twice differentiable in the interval
:math:`[x_1, x_2]`. The interpolation error is the difference between the
interpolated value :math:`\hat{f}(\hat{x})` and the true value
:math:`f(\hat{x})`. We wish to know how the interpolation error behaves as
:math:`h \rightarrow 0`. We say that the interpolation *converges* if
:math:`\hat{f}(\hat{x}) - f(\hat{x}) \rightarrow 0` as
:math:`h \rightarrow 0`.
