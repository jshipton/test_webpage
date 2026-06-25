.. container::

   .. rubric:: Mathematical Modelling Module - Lecture Notes Chapter 1
      (Part 2)
      :name: mathematical-modelling-module---lecture-notes-chapter-1-part-2

   Back to sections 1-4: :doc:`index`
   .. container:: section
      :name: sec-python-arithmetic

      .. rubric:: Python: Arithmetic on the command line
         :name: python-arithmetic-on-the-command-line

      You can use Python in 'interactive' mode by following these
      instructions:

      .. rubric:: Starting iPython
         :name: starting-ipython

      #. First start Anaconda Navigator - you can find this by typing in
         the search box.
      #. **Wait patiently** for it to finish setting up (observe the
         progress bar at the bottom of the window) otherwise you may
         have some unpleasant errors!
      #. Scroll down to find 'Jupyter Lab' and click the 'Launch'
         button. Note, you do *not* want 'Jupyter Notebook'.
      #. When asked what type of file to open, choose 'Terminal'. This
         will open a Powershell terminal where you can interact with the
         filesystem using commands.
      #. Start an Interactive Python (iPython) session by typing
         ``ipython`` in the Terminal and hitting enter.
      #. Note that to exit iPython you press ``Ctrl+D`` and hit enter.

      .. rubric:: Basic Arithmetic Operations
         :name: basic-arithmetic-operations

      You can type instructions at the command line prompt to tell
      Python to carry out basic arithmetic operations: addition (``+``),
      subtraction (``-``), multiplication (``*``), division (``/``), and
      exponentiation (``**``).

      .. container:: example

         **Example:** Compute the volume of a pyramid of height 150 m
         and base area 50,000 m²
         >>> 150*50000/3

      .. rubric:: Important Notes
         :name: important-notes

      - All multiplications need to be written out explicitly: ``2x``
        will give an error, whereas ``2*x`` is correct.
      - Parentheses (``()``) are used to group terms together. Every
        opening bracket must have a matching closing bracket.
      - Exponentiation has higher precedence than multiplication and
        division, which have higher precedence than addition and
        subtraction.
      - Python has a variable called ``pi``, which can be imported from
        the ``math`` module.

   .. container:: section
      :name: sec-python-modules

      .. rubric:: Python: The math and cmath modules; variables
         :name: python-the-math-and-cmath-modules-variables

      Python keeps things tidy by collecting objects such as functions
      together in modules. For example, the ``math`` module contains the
      definitions of a lot of mathematical functions and useful
      constants such as $\\pi$. To access these definitions, we need to
      import them from the module:

      ::

         >>> from math import pi

      The `math <https://docs.python.org/3/library/math.html>`__ and
      `cmath <https://docs.python.org/3/library/cmath.html>`__ modules
      contain functions to compute many standard mathematical functions.
      The ``math`` functions are only defined for real input and output,
      whereas the ``cmath`` functions will accept real and complex input
      and will *always* return a complex number.

      .. rubric:: Commonly Used Mathematical Functions
         :name: commonly-used-mathematical-functions

      ============ ======================== ================ =================
      Function     Description              Function         Description
      ============ ======================== ================ =================
      ``sin(x)``   Sine                     ``sqrt(x)``      Square root
      ``cos(x)``   Cosine                   ``exp(x)``       $e^x$
      ``tan(x)``   Tangent                  ``log(x)``       Natural logarithm
      ``asin(x)``  Inverse sine             ``log10(x)``     Base 10 logarithm
      ``abs(x)``   Absolute value           ``factorial(x)`` $x!$
      ``round(x)`` Round to nearest integer ``floor(x)``     Round down
      ============ ======================== ================ =================

      .. rubric:: Variables
         :name: variables

      You can store numbers, including the results of calculations, in
      named locations in the computer memory, called **variables**, to
      use them later. Variable names must start with a letter, followed
      by any number of letters, digits, or underscore characters.
      Variable names are case sensitive: ``Temp`` is different from
      ``temp``.

   .. container:: section
      :name: sec-python-assignment

      .. rubric:: Python: assignment, sequences of commands
         :name: python-assignment-sequences-of-commands

      There is a crucial conceptual difference between the use of '=' in
      pencil-and-paper mathematics and the use of '=' in a programming
      language such as Python. In pencil-and-paper mathematics, $y = x^2
      + 4x + 5$ is an *equation*. In Python, ``y = x**2 + 4*x + 5`` is
      an *instruction*; it means evaluate the expression on the right
      hand side and *assign* the result to the variable whose name
      appears on the left hand side.

      Python executes the commands we give one at a time, in the order
      we give them. The values of the variables change as each command
      is executed. While in pencil-and-paper mathematics it would be
      nonsensical to write $p = 6$, $p = 7$, $p = p + 1$, the following
      is perfectly valid in Python:

      ::

         >>> p = 6
         >>> p = 7
         >>> p = p + 1

   .. container:: section
      :name: sec-python-precision

      .. rubric:: Python: Precision
         :name: python-precision

      Computers have finite memory, and this means they cannot store
      real numbers such as $\\pi$ or $\\sqrt{2}$ exactly; such numbers
      can only be stored to some finite *precision*. By default Python
      stores real numbers to a precision of about 15 decimal digits.

      This is more than enough for most practical purposes. However,
      there are certain calculations in which the effects of tiny
      precision errors (also called *roundoff errors*) are greatly
      amplified. Examples include:

      - Accumulating the sum of many terms
      - Taking small differences of relatively large numbers
      - Finding roots of polynomials
      - Certain eigenvalue computations

   .. container:: section
      :name: sec-linear-interp

      .. rubric:: Linear interpolation
         :name: linear-interpolation

      Suppose we are given some tabulated data, for example temperatures
      at certain heights in the atmosphere, and we wish to estimate the
      temperature at an intermediate height that is not tabulated. In
      effect we need to construct a *mathematical model* for the
      dependence of temperature on height between the tabulated values.

      **Linear interpolation** is the simplest type of interpolation,
      which fits a straight line between each neighbouring pair of data
      points.

      .. rubric:: Linear Interpolation Formula
         :name: linear-interpolation-formula

      Given two neighbouring data points $(x_1, y_1)$ and $(x_2, y_2)$,
      the equation of the straight line passing through these points is:

      .. container:: math-display

         $$y = \\frac{(x - x_1)y_2 + (x_2 - x)y_1}{x_2 - x_1}$$

      Thus, an estimate $\\hat{y}$ for the value of $y$ at $x =
      \\hat{x}$ is given by:

      .. container:: math-display

         $$\\hat{y} = \\frac{(\\hat{x} - x_1)y_2 + (x_2 -
         \\hat{x})y_1}{x_2 - x_1}$$

      The closer our given data points are to each other, the more
      accurate we might expect our interpolated value to be.

   .. container:: section
      :name: sec-numerical-analysis

      .. rubric:: Numerical analysis and Taylor–Maclaurin series
         :name: numerical-analysis-and-taylormaclaurin-series

      .. rubric:: What is numerical analysis?
         :name: what-is-numerical-analysis

      We have met the numerical process of *linear interpolation* for
      estimating values of a function given some dataset. Although we
      can write down a variety of numerical methods, one key aspect is
      to understand what *errors* are made. Since none of these methods
      will generally give exact answers, if we have two numerical
      methods for solving the same problem, we need to understand the
      size of the errors to know which method is superior.

      The analysis of numerical methods, their errors and other
      properties, forms the subject of *numerical analysis*, which is an
      important and vigorous topic in mathematics and computation.

      .. rubric:: Taylor–Maclaurin series
         :name: taylormaclaurin-series

      Suppose we have a function $f(x)$ with derivative $f'(x)$. Given a
      point $x = a$ and we wish to approximate $f(a + h)$ for nearby
      points $x = a + h$ (with $h$ small), then we can approximate:

      **Linear approximation:** $f(a + h) \\simeq f(a) + h f'(a)$

      **Quadratic approximation:** $f(a + h) \\simeq f(a) + h f'(a) +
      \\frac{h^2}{2} f''(a)$

      For better approximations, we use the **Taylor-Maclaurin series**:

      .. container:: math-display

         $$f(a + h) = f(a) + h f'(a) + \\frac{h^2}{2!}f''(a) +
         \\frac{h^3}{3!}f'''(a) + \\ldots + \\frac{h^n}{n!} f^{(n)}(a) +
         \\ldots$$

      .. rubric:: Taylor's theorem
         :name: taylors-theorem

      If the function $f(x)$ is differentiable at least $n+1$ times at a
      point $x = a$, then values of $f$ near to $a$ are given by:

      .. container:: math-display

         $$f(a + h) = f(a) + h f'(a) + \\frac{h^2}{2}f''(a) + \\ldots +
         \\frac{h^n}{n!} f^{(n)}(a) + O(h^{n+1})$$

      The notation $O(h^{n+1})$ means a quantity that tends to zero like
      a constant times $h^{n+1}$ when $h$ tends to zero. It is a
      convenient way to give the key information needed about the 'error
      term'.

      **Rule of thumb:** If the error term is $\\varepsilon = O(h^2)$,
      then if we halve $h$ the error $\\varepsilon$ is multiplied by a
      quarter. A scheme with $O(h^2)$ error is superior to one with
      $O(h)$ error, when halving $h$ only halves the error.

   .. container:: section
      :name: sec-convergence

      .. rubric:: Convergence of linear interpolation
         :name: convergence-of-linear-interpolation

      Let us illustrate these ideas by looking at the error we make when
      we apply linear interpolation to a smooth function $f(x)$. If we
      have data points at $x = x_1$ and $x = x_2$ with $h = x_2 - x_1$,
      then clearly the error goes down as we reduce $h$, but we need
      some theory to establish the order of this numerical method.

      Suppose $f(x)$ is at least twice differentiable in the interval
      $[x_1, x_2]$. The interpolation error is the difference between
      the interpolated value $\\hat{f}(\\hat{x})$ and the true value
      $f(\\hat{x})$. We wish to know how the interpolation error behaves
      as $h \\rightarrow 0$. We say that the interpolation *converges*
      if $\\hat{f}(\\hat{x}) - f(\\hat{x}) \\rightarrow 0$ as $h
      \\rightarrow 0$.

   .. container:: section
      :name: sec-lists-tuples-arrays

      .. rubric:: Python: lists, tuples and arrays
         :name: python-lists-tuples-and-arrays

      It is often convenient to refer to several (or many) pieces of
      data via single variable name, e.g., a list of atmospheric
      temperatures ``T`` at corresponding heights ``z``. We can do this
      in Python using *lists*, *tuples* or *arrays*. Lists and tuples
      are data structures available in Python whereas arrays are handled
      using the ``numpy`` module.

      We can create a (small) list by enclosing the entries in square
      brackets and separating them by commas.

      .. container:: example

         >> R = [3, 6, -2]

      If we want to access an individual element of a list, either to
      compute with it or to assign to it, we can do so using *indices*
      (also called *subscripts*) in square brackets after the list name.
      In Python, indices start at 0 (in some languages they start at 1).
      We can use negative indices to access the list (or tuple, or
      array) from the end.

      .. container:: example

         >> R[0] = 37

      Note that square brackets are used here because round brackets are
      used for calling functions (you have seen this with built-in
      functions e.g. ``sin(pi)`` and will meet it again later when you
      write your own functions).

      .. container:: example

         **Example:** What error message do you get if you try using
         round brackets to access the first entry in ``R``? How about if
         you try to change the value of the first entry using round
         brackets?

      A list can be extended by adding a new value at the end using the
      ``append`` method. Here round brackets are used because we are
      calling a function (a method is a function defined on an object).

      .. container:: example

         >> R.append(119)

      A Python tuple is very similar to a Python list, but is created
      using round brackets.

      .. container:: example

         >> R = (3, 6, -2)

      Again we can access the individual elements using indices in
      square brackets.

      .. container:: example

         >> print(R[0])

      However, when we try to append to the tuple, or change one of the
      values, we find that we cannot. This is because tuples are
      *immutable*, meaning that once defined, they cannot be changed.

      .. container:: example

         **Example:** Try appending to a tuple, or changing one of the
         values as we did with the list above. What error messages do
         you get?

      The tuples and lists we have just seen look like 1D vectors.
      However, if we try to treat them in this way, we will see that
      they do not behave as we require. For example, we expect that
      multiplying a vector by a scalar will result in a new vector with
      the same number of components where each component has been
      multiplied by the scalar:

      .. container:: math-display

         $$a\\begin{pmatrix} 1 \\\\ 4 \\\\ 3 \\end{pmatrix} =
         \\begin{pmatrix} a \\\\ 4a \\\\ 3a \\end{pmatrix}$$

      If we try to do this with a Python list (or tuple) the result is a
      new list (or tuple) that contains $a$ copies of the original list
      (or tuple). [Exercise: try it!] We need a different type of object
      for performing these mathematical operations... arrays!

      The Python module for handling arrays is ``numpy``. The most
      common way to import it is to give it the shortened name ``np``.

      .. container:: example

         >> import numpy as np

      We can now convert a list to an array

      .. container:: example

         >> C = np.array([3, 6, -2])

      Multiplying this array by a scalar now works as we require for
      mathematical operations [Exercise: try it!].

      We can create a (small) 2D array, or matrix, in a similar way,
      with a new list for each row.

      .. container:: example

         >> M = np.array([[0, 1], [-1, 0]])

      What's the difference between a list, a tuple, a vector, a matrix,
      and an array? We usually refer to objects as 'vectors' or
      'matrices' when we envisage performing matrix-vector arithmetic
      operations on them (see below), and as 'arrays' when they are just
      tables of numbers. A row vector is a $1 \\times n$ array with $n$
      columns, a column vector is an $m \\times 1$ array with $m$ rows.
      Python does not distinguish between the two - they are both
      represented as 1D arrays. A matrix is an $m \\times n$ array.
      Higher dimensional arrays are also possible. But note all arrays
      must be 'rectangular', i.e. have the same number of columns in
      every row and vice versa. Note that for 2D arrays the first index
      is the row index and the second is the column index.

      .. container:: example

         >> C[1] = 12

      **Warning:** Try setting ``C[1] = sqrt(3)``. If you print out the
      value of ``C[1]`` you will see that it is ``1``, rather than
      ``1.73205081...``. This is because ``C`` was created with integer
      entries and Python has assumed that you would like the entries to
      remain integers. You can check the type of array entries by
      looking at the value of ``C.dtype``, and you can set the type of
      entry when you create the array. Try setting
      ``C = np.array([3, 6, 2], dtype=float)`` and then setting
      ``C[1] = sqrt(3)``.

      We can create larger arrays in various ways. To create an array
      containing entries from 1 to 100 with an increment of 1 we can use
      ``np.arange``.

      .. container:: example

         >> z = np.arange(1, 100, 1)

      The first two numbers passed to ``np.arange`` are the start and
      the end of the sequence. The final number is the increment, and
      this defaults to 1 if left unspecified.

      .. container:: example

         >> z = np.arange(1, 100)

      Negative and non-integer increments can also be used. If the
      increment means that the final value will be missed, then the
      array terminates before the number specified by the ending value.
      For example, ``np.arange(1, 10, 2)`` generates the array
      ``[1, 3, 5, 7, 9]``.

      A common requirement is for an array to contain a guaranteed start
      and end point with evenly spaced elements in between. For this we
      can use ``np.linspace(start, end, n)``, where ``n`` is the number
      of entries.

      .. container:: example

         >> z = np.linspace(1, 5, 10)

      We can create arrays of zeros or ones using built-in ``numpy``
      functions.

      .. container:: example

         >> X0 = np.zeros((100,100))

      We can perform standard arithmetic operations on arrays provided
      their shapes **conform**, including ...

      .. container:: example

         >> A = np.array([[1, 2], [3, 4]])

      .. container:: example

         >> B = np.array([[5, 6], [7, 8]])

      addition and subtraction,

      .. container:: example

         >> S = A + B

      matrix multiplication,

      .. container:: example

         >> P = A @ B

      element-by-element multiplication,

      .. container:: example

         >> Q = A \* B

      raising each element to a power,

      .. container:: example

         >> Q = A**2

      and transpose.

      .. container:: example

         >> T = A.T

      Note that by 'conform' we mean that the matrix dimensions must be
      compatible, so for example we can add two $2\\times 3$ matrices,
      and we can multiply a $2\\times 3$ matrix by a $3\\times 4$
      matrix, but not a $2\\times 3$ by a $4\\times 2$ matrix. Python
      will flag an error if the dimensions make the operation
      impossible. We can check the shape of a matrix by printing its
      ``shape`` attribute.

      .. container:: example

         >> print(M.shape)

      **Warning:** Because ``numpy`` arrays are not strictly matrices,
      some operations are allowed that you might not expect. When
      operating on arrays, ``numpy`` compares their shapes to decide if
      they are *compatible*. The dimensions are compatible if they are
      equal or if one of them is 1. This is best illustrated with an
      example.

      .. container:: example

         >> X = np.array([[4, 2, 3], [1, 1, 0]]) >> Y = np.array([[2],
         [1]]) >> X + Y

      ``X`` has shape ``(2, 3)`` and ``Y`` has shape ``(2, 1)`` so both
      dimensions are compatible. In this case, ``Y`` will act like a
      ``(2, 3)`` array and Python will *broadcast* ``Y[:,0]`` to the
      other columns. The operation ``X+Y`` will add ``Y`` to each column
      of ``X``. You can read more about this
      `here <https://numpy.org/doc/stable/user/basics.broadcasting.html>`__,
      although it is outside the scope of this module.

      For complex matrices, that is matrices with complex entries, the
      transpose operation ``A.T`` becomes a 'transpose and take the
      complex conjugate of all the entries' operation, or a so-called
      **Hermitian transpose**. This is the 'natural' way to transpose a
      complex matrix, as you will find in later courses on algebra.

      Many additional linear algebra functions are provided by the
      ``numpy.linalg`` library. For square matrices ``A``, the
      ``linalg.matrix_power(A, n)`` function will raise the matrix ``A``
      to the power of ``n``.

      .. container:: example

         >> Y = np.linalg.matrix_power(A, 2)

      .. container:: example

         **Example:** Given the arrays ``a``, ``b``, and ``c``: >> a =
         np.array([[1, 0, 1], [0, 1, 0]]) >> b = np.array([[6, 5, 4],
         [3, 2, 1]]) >> c = np.array([-1, 1]) which of the following
         commands are allowed?

         =========== ========= ===========
         ``a + b``   ``a + c`` ``a + b.T``
         ``a @ b``   ``b @ a`` ``b @ c``
         ``b @ a.T`` ``c @ b`` ``a * b``
         =========== ========= ===========

         Try to work it out before checking using Python.

      Many built-in functions such as ``cos``, ``exp``, etc., can be
      applied to arrays. They act element-by-element.

      We can perform calculations on sub-arrays using the colon notation
      to refer to a range of subscripts. These are often referred to as
      **slices** of an array, with analogies to serving cake.

      .. container:: example

         >> A = np.array([[1, 2, 3], [4, 5, 6]]) >> A[0, :2] = 0 >> A[:,
         0] = -1

      Note that the notation ``[:2]`` refers to all entries up to but
      *not including* the entry with index 2.

   .. container:: section
      :name: sec-reading-saving

      .. rubric:: Python: reading and saving data
         :name: python-reading-and-saving-data

      We can save ``numpy`` arrays to text files using the
      ``np.savetxt`` command

      .. container:: example

         >> X = np.array([[4, 2, 3], [6, 7, 8]]) >>
         np.savetxt('my_array.txt', X)

      Python can read this data back in using the ``np.loadtxt``
      command.

      .. container:: example

         >> Y = np.loadtxt('my_array.txt')

      The ``savetxt`` and ``loadtxt`` commands have many options; use
      ``help`` if you want to find out more.

   .. container:: section
      :name: sec-plotting

      .. rubric:: Python: plotting
         :name: python-plotting

      Python has extensive graphics capability via the module
      ``matplotlib``. Here we will just use a couple of examples to
      introduce some of the basics.

      First we need to import the functions we need from the module. The
      standard way to do this is with the command

      .. container:: example

         import matplotlib.pyplot as plt

      .. container:: example

         **Example:** A particle's position $x$ is given as a function
         of time $t$ as $x = 2.5 \\cos(t)$. Plot its position vs time
         for $t \\in [0,10]$.

      First create a uniformly spaced list of times between 0 and 10:
      this command line specifies 101 points from 0 to 10 going [0, 0.1,
      0.2, …, 9.9, 10]:

      .. container:: example

         >> t = np.linspace(0, 10, 101)

      Compute the corresponding positions; note that we need to use the
      ``cos`` function defined in ``numpy`` to apply the ``cos``
      function element-by-element to compute a whole array of $x$'s; the
      ``cos`` function defined in the ``math`` module does not know
      about arrays.

      .. container:: example

         >> x = 2.5*np.cos(t)

      Plot the data.

      .. container:: example

         >> plt.plot(t, x)

      The plot has been created but before we display it, let us add
      axis labels and a title.

      .. container:: example

         >> plt.xlabel('t') >> plt.ylabel('x') >> plt.title('Position vs
         time')

      Now display the plot.

      .. container:: example

         >> plt.show()

      .. container:: example

         **Example:** Download the file ``USSA.txt`` from the ELE page
         to the current folder. Let us read the data set >> data =
         np.loadtxt('USSA.txt') and unpack the data; first column of the
         array contains heights, second column contains temperatures.
         Convert the heights from m to km. >> z = data[:, 0]/1000 >> T =
         data[:, 1] Plot the data. Indicate data points by black
         circles; join with black dotted lines. Make the line a bit
         thicker for clarity. >> plt.plot(T, z, 'ko:', linewidth=1.5)
         Add axis labels and a title. >> plt.xlabel('T (K)') >>
         plt.ylabel('z (km)') >> plt.title('US Standard Atmosphere') Now
         display the plot. >> plt.show() Now let us linearly interpolate
         to a uniformly spaced set of points between the fourth and
         fifth data points in the set. Note that here (contrast section
         9) ``zhat`` and ``That`` are arrays. >> zhat =
         np.linspace(z[4], z[5], 11) >> That = ((zhat - z[4])*T[5] ... +
         (z[5] - zhat)*T[4]) ... /(z[5] - z[4])

   Lecture Notes for Mathematical Modelling Module - Chapter 1

   Originally created as LaTeX, converted to HTML and hosted on GitHub
   Pages
