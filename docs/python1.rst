Python: Introduction
====================

You can use Python in 'interactive' mode by following these
instructions:

Starting iPython
----------------

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

Basic Arithmetic Operations
---------------------------

You can type instructions at the command line prompt to tell Python to
carry out basic arithmetic operations: addition (``+``), subtraction
(``-``), multiplication (``*``), division (``/``), and exponentiation
(``**``).

      **Example:** Compute the volume of a pyramid of height :math:`150m`
      and base area :math:`50,000m^2`
      >>> 150*50000/3

      **Important notes:**

      - All multiplications need to be written out explicitly: ``2x``
        will give an error, whereas ``2*x`` is correct.
      - Parentheses (``()``) are used to group terms together. Every
        opening bracket must have a matching closing bracket.
      - Exponentiation has higher precedence than multiplication and
        division, which have higher precedence than addition and
        subtraction.
      - Python has a variable called ``pi``, which can be imported from
        the ``math`` module.

The math and cmath modules
--------------------------

Python keeps things tidy by collecting objects such as functions
together in modules. For example, the ``math`` module contains the
definitions of a lot of mathematical functions and useful constants
such as :math:`\pi`. To access these definitions, we need to import them
from the module:

      ::

         >>> from math import pi

The `math <https://docs.python.org/3/library/math.html>`__ and `cmath
<https://docs.python.org/3/library/cmath.html>`__ modules contain
functions to compute many standard mathematical functions.  The
``math`` functions are only defined for real input and output, whereas
the ``cmath`` functions will accept real and complex input and will
*always* return a complex number.

Commonly Used Mathematical Functions
------------------------------------

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

Variables
---------

You can store numbers, including the results of calculations, in named
locations in the computer memory, called **variables**, to use them
later. Variable names must start with a letter, followed by any number
of letters, digits, or underscore characters.  Variable names are case
sensitive: ``Temp`` is different from ``temp``.

Assignment
----------

There is a crucial conceptual difference between the use of '=' in
pencil-and-paper mathematics and the use of '=' in a programming
language such as Python. In pencil-and-paper mathematics, :math:`y = x^2
+ 4x + 5` is an *equation*. In Python, ``y = x**2 + 4*x + 5`` is an
*instruction*; it means evaluate the expression on the right hand side
and *assign* the result to the variable whose name appears on the left
hand side.

Sequences of commands
---------------------

Python executes the commands we give one at a time, in the order we
give them. The values of the variables change as each command is
executed. While in pencil-and-paper mathematics it would be
nonsensical to write :math:`p = 6`, :math:`p = 7`, :math:`p = p + 1`,
the following is perfectly valid in Python:

      ::

         >>> p = 6
         >>> p = 7
         >>> p = p + 1

Precision
---------

Computers have finite memory, and this means they cannot store real
numbers such as :math:`\pi` or :math:`\sqrt{2}` exactly; such numbers
can only be stored to some finite *precision*. By default Python
stores real numbers to a precision of about 15 decimal digits.

This is more than enough for most practical purposes. However, there
are certain calculations in which the effects of tiny precision errors
(also called *roundoff errors*) are greatly amplified. Examples
include:

      - Accumulating the sum of many terms
      - Taking small differences of relatively large numbers
      - Finding roots of polynomials
      - Certain eigenvalue computations
