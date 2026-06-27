Python
======

Lists, tuples and arrays
------------------------

It is often convenient to refer to several (or many) pieces of data via single
variable name, e.g., a list of atmospheric temperatures ``T`` at corresponding
heights ``z``. We can do this in Python using *lists*, *tuples* or *arrays*.
Lists and tuples are data structures available in Python whereas arrays are
handled using the ``numpy`` module.

We can create a (small) list by enclosing the entries in square brackets and
separating them by commas.

.. code-block:: pycon

   >>> R = [3, 6, -2]

If we want to access an individual element of a list, either to compute with it
or to assign to it, we can do so using *indices* (also called *subscripts*) in
square brackets after the list name. In Python, indices start at 0 (in some
languages they start at 1). We can use negative indices to access the list (or
tuple, or array) from the end.

.. code-block:: pycon

   >>> R[0] = 37

Note that square brackets are used here because round brackets are used for
calling functions (you have seen this with built-in functions e.g. ``sin(pi)``
and will meet it again later when you write your own functions).

**Example:** What error message do you get if you try using round brackets to
access the first entry in ``R``? How about if you try to change the value of
the first entry using round brackets?

A list can be extended by adding a new value at the end using the ``append``
method. Here round brackets are used because we are calling a function (a
method is a function defined on an object).

.. code-block:: pycon

   >>> R.append(119)

A Python tuple is very similar to a Python list, but is created using round
brackets.

.. code-block:: pycon

   >>> R = (3, 6, -2)

Again we can access the individual elements using indices in square brackets.

.. code-block:: pycon

   >>> print(R[0])

However, when we try to append to the tuple, or change one of the values, we
find that we cannot. This is because tuples are *immutable*, meaning that once
defined, they cannot be changed.

**Example:** Try appending to a tuple, or changing one of the values as we did
with the list above. What error messages do you get?

The tuples and lists we have just seen look like 1D vectors. However, if we try
to treat them in this way, we will see that they do not behave as we require.
For example, we expect that multiplying a vector by a scalar will result in a
new vector with the same number of components where each component has been
multiplied by the scalar:

.. math::

   a\begin{pmatrix}
   1 \\
   4 \\
   3
   \end{pmatrix}
   =
   \begin{pmatrix}
   a \\
   4a \\
   3a
   \end{pmatrix}

If we try to do this with a Python list (or tuple) the result is a new list (or
tuple) that contains :math:`a` copies of the original list (or tuple).
[Exercise: try it!] We need a different type of object for performing these
mathematical operations... arrays!

The Python module for handling arrays is ``numpy``. The most common way to
import it is to give it the shortened name ``np``.

.. code-block:: pycon

   >>> import numpy as np

We can now convert a list to an array

.. code-block:: pycon

   >>> C = np.array([3, 6, -2])

Multiplying this array by a scalar now works as we require for mathematical
operations [Exercise: try it!].

We can create a (small) 2D array, or matrix, in a similar way, with a new list
for each row.

.. code-block:: pycon

   >>> M = np.array([[0, 1], [-1, 0]])

What's the difference between a list, a tuple, a vector, a matrix, and an
array? We usually refer to objects as 'vectors' or 'matrices' when we envisage
performing matrix-vector arithmetic operations on them (see below), and as
'arrays' when they are just tables of numbers. A row vector is a
:math:`1 \times n` array with :math:`n` columns, a column vector is an
:math:`m \times 1` array with :math:`m` rows. Python does not distinguish
between the two - they are both represented as 1D arrays. A matrix is an
:math:`m \times n` array. Higher dimensional arrays are also possible. But note
all arrays must be 'rectangular', i.e. have the same number of columns in every
row and vice versa. Note that for 2D arrays the first index is the row index
and the second is the column index.

.. code-block:: pycon

   >>> C[1] = 12

**Warning:** Try setting ``C[1] = sqrt(3)``. If you print out the value of
``C[1]`` you will see that it is ``1``, rather than ``1.73205081...``. This is
because ``C`` was created with integer entries and Python has assumed that you
would like the entries to remain integers. You can check the type of array
entries by looking at the value of ``C.dtype``, and you can set the type of
entry when you create the array. Try setting ``C = np.array([3, 6, 2],
dtype=float)`` and then setting ``C[1] = sqrt(3)``.

We can create larger arrays in various ways. To create an array containing
entries from 1 to 100 with an increment of 1 we can use ``np.arange``.

.. code-block:: pycon

   >>> z = np.arange(1, 100, 1)

The first two numbers passed to ``np.arange`` are the start and the end of the
sequence. The final number is the increment, and this defaults to 1 if left
unspecified.

.. code-block:: pycon

   >>> z = np.arange(1, 100)

Negative and non-integer increments can also be used. If the increment means
that the final value will be missed, then the array terminates before the
number specified by the ending value. For example, ``np.arange(1, 10, 2)``
generates the array ``[1, 3, 5, 7, 9]``.

A common requirement is for an array to contain a guaranteed start and end point
with evenly spaced elements in between. For this we can use
``np.linspace(start, end, n)``, where ``n`` is the number of entries.

.. code-block:: pycon

   >>> z = np.linspace(1, 5, 10)

We can create arrays of zeros or ones using built-in ``numpy`` functions.

.. code-block:: pycon

   >>> X0 = np.zeros((100,100))

We can perform standard arithmetic operations on arrays provided their shapes
**conform**, including ...

.. code-block:: pycon

   >>> A = np.array([[1, 2], [3, 4]])
   >>> B = np.array([[5, 6], [7, 8]])
   >>> S = A + B
   >>> P = A @ B
   >>> Q = A * B
   >>> Q = A**2
   >>> T = A.T

Note that by 'conform' we mean that the matrix dimensions must be compatible,
so for example we can add two :math:`2\times 3` matrices, and we can multiply a
:math:`2\times 3` matrix by a :math:`3\times 4` matrix, but not a
:math:`2\times 3` by a :math:`4\times 2` matrix. Python will flag an error if
the dimensions make the operation impossible. We can check the shape of a
matrix by printing its ``shape`` attribute.

.. code-block:: pycon

   >>> print(M.shape)

**Warning:** Because ``numpy`` arrays are not strictly matrices, some operations
are allowed that you might not expect. When operating on arrays, ``numpy``
compares their shapes to decide if they are *compatible*. The dimensions are
compatible if they are equal or if one of them is 1. This is best illustrated
with an example.

.. code-block:: pycon

   >>> X = np.array([[4, 2, 3], [1, 1, 0]])
   >>> Y = np.array([[2], [1]])
   >>> X + Y

``X`` has shape ``(2, 3)`` and ``Y`` has shape ``(2, 1)`` so both dimensions
are compatible. In this case, ``Y`` will act like a ``(2, 3)`` array and Python
will *broadcast* ``Y[:,0]`` to the other columns. The operation ``X+Y`` will
add ``Y`` to each column of ``X``. You can read more about this
`here <https://numpy.org/doc/stable/user/basics.broadcasting.html>`__, although
it is outside the scope of this module.

For complex matrices, that is matrices with complex entries, the transpose
operation ``A.T`` becomes a 'transpose and take the complex conjugate of all
the entries' operation, or a so-called **Hermitian transpose**. This is the
'natural' way to transpose a complex matrix, as you will find in later courses
on algebra.

Many additional linear algebra functions are provided by the ``numpy.linalg``
library. For square matrices ``A``, the ``linalg.matrix_power(A, n)`` function
will raise the matrix ``A`` to the power of ``n``.

.. code-block:: pycon

   >>> Y = np.linalg.matrix_power(A, 2)

**Example:** Given the arrays ``a``, ``b``, and ``c``::

   >>> a = np.array([[1, 0, 1], [0, 1, 0]])
   >>> b = np.array([[6, 5, 4], [3, 2, 1]])
   >>> c = np.array([-1, 1])

which of the following commands are allowed?

+-------------+-------------+-------------+
| ``a + b``   | ``a + c``   | ``a + b.T`` |
+-------------+-------------+-------------+
| ``a @ b``   | ``b @ a``   | ``b @ c``   |
+-------------+-------------+-------------+
| ``b @ a.T`` | ``c @ b``   | ``a * b``   |
+-------------+-------------+-------------+

Try to work it out before checking using Python.

Many built-in functions such as ``cos``, ``exp``, etc., can be applied to
arrays. They act element-by-element.

We can perform calculations on sub-arrays using the colon notation to refer to
a range of subscripts. These are often referred to as **slices** of an array,
with analogies to serving cake.

.. code-block:: pycon

   >>> A = np.array([[1, 2, 3], [4, 5, 6]])
   >>> A[0, :2] = 0
   >>> A[:, 0] = -1

Note that the notation ``[:2]`` refers to all entries up to but *not including*
the entry with index 2.


Reading and saving data
-----------------------

We can save ``numpy`` arrays to text files using the ``np.savetxt`` command

.. code-block:: pycon

   >>> X = np.array([[4, 2, 3], [6, 7, 8]])
   >>> np.savetxt('my_array.txt', X)

Python can read this data back in using the ``np.loadtxt`` command.

.. code-block:: pycon

   >>> Y = np.loadtxt('my_array.txt')

The ``savetxt`` and ``loadtxt`` commands have many options; use ``help`` if you
want to find out more.


Plotting
--------

Python has extensive graphics capability via the module ``matplotlib``. Here we
will just use a couple of examples to introduce some of the basics.

First we need to import the functions we need from the module. The standard way
to do this is with the command

.. code-block:: pycon

   >>> import matplotlib.pyplot as plt

**Example:** A particle's position :math:`x` is given as a function of time
:math:`t` as :math:`x = 2.5 \cos(t)`. Plot its position vs time for
:math:`t \in [0,10]`.

First create a uniformly spaced list of times between 0 and 10: this command
line specifies 101 points from 0 to 10 going [0, 0.1, 0.2, …, 9.9, 10]:

.. code-block:: pycon

   >>> t = np.linspace(0, 10, 101)

Compute the corresponding positions; note that we need to use the ``cos``
function defined in ``numpy`` to apply the ``cos`` function element-by-element
to compute a whole array of :math:`x`'s; the ``cos`` function defined in the
``math`` module does not know about arrays.

.. code-block:: pycon

   >>> x = 2.5*np.cos(t)

Plot the data.

.. code-block:: pycon

   >>> plt.plot(t, x)

The plot has been created but before we display it, let us add axis labels and
a title.

.. code-block:: pycon

   >>> plt.xlabel('t')
   >>> plt.ylabel('x')
   >>> plt.title('Position vs time')

Now display the plot.

.. code-block:: pycon

   >>> plt.show()

**Example:** Download the file ``USSA.txt`` from the ELE page to the current
folder. Let us read the data set::

   >>> data = np.loadtxt('USSA.txt')

and unpack the data; first column of the array contains heights, second column
contains temperatures. Convert the heights from m to km.

.. code-block:: pycon

   >>> z = data[:, 0]/1000
   >>> T = data[:, 1]

Plot the data. Indicate data points by black circles; join with black dotted
lines. Make the line a bit thicker for clarity.

.. code-block:: pycon

   >>> plt.plot(T, z, 'ko:', linewidth=1.5)

Add axis labels and a title.

.. code-block:: pycon

   >>> plt.xlabel('T (K)')
   >>> plt.ylabel('z (km)')
   >>> plt.title('US Standard Atmosphere')

Now display the plot.

.. code-block:: pycon

   >>> plt.show()

Now let us linearly interpolate to a uniformly spaced set of points between the
fourth and fifth data points in the set. Note that here (contrast section 9)
``zhat`` and ``That`` are arrays.

.. code-block:: pycon

   >>> zhat = np.linspace(z[4], z[5], 11)
   >>> That = ((zhat - z[4])*T[5] + (z[5] - zhat)*T[4])/(z[5] - z[4])
