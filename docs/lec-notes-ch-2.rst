.. include:: custom.rst

Mathematical description of motion
==================================

Particles
---------

| In this module we stick to the simplest models of Newtonian mechanics.
  In particular, we approximate all bodies as point particles, that is,
  particles of zero size. In doing so we are ignoring
|    :math:`\bullet` that bodies can rotate
|    :math:`\bullet` that bodies can have internal motions

.. margin::

   **Reading:** Collinson and Roper §1.2. Note ideas of particle, speed,
   uniform motion, mass, force.

| Often this is an excellent approximation (e.g. planets,
  rollercoaster). It is also an important starting point for Newtonian
  mechanics because
| :math:`\bullet` one can build up an *extended* body (one of non-zero
  size) by adding up many point masses;
| :math:`\bullet` given an extended body, there is a special point
  called the *centre of mass*, which moves as though all the mass were
  concentrated at that point.

Position
--------

Given that we model a body as a point particle, we can define its
**position** at a given time :math:`t`. Introduce a set of fixed
right-handed axes based at an origin O.

.. figure:: _static/images/rhaxes.png
   :figclass: margin
   :alt: 
   :width: 5cm

At a given time the particle has position given by its coordinates
:math:`(x,y,z)`. Since, in general, the particle moves, :math:`x`,
:math:`y` and :math:`z` vary with time, so we represent position by
three functions of time :math:`(x(t),y(t),z(t))`.

We can equivalently represent the position of the particle at time
:math:`t` using a vector function of time :math:`\boldsymbol{r}(t)`.

.. math:: \boldsymbol{r}(t) = x(t) \boldsymbol{i} + y(t) \boldsymbol{j} + z(t) \boldsymbol{k} .

Velocity
--------

The **velocity** of a particle is the rate of change of its position:

.. math:: \boldsymbol{v}(t) = \frac{\mathrm{d} \boldsymbol{r}}{\mathrm{d} t} .

At each time :math:`t`, :math:`\boldsymbol{v}` is a vector whose
magnitude gives the **speed** :math:`|\boldsymbol{v} (t)|` of the
particle and whose direction gives the direction of motion. For brevity
we will write :math:`\boldsymbol{v} = \dot{\boldsymbol{r}}`; the dot
indicates a time derivative.

.. math:: \boldsymbol{v} = \dot{\boldsymbol{r}} = \dot{x} \boldsymbol{i} + \dot{y} \boldsymbol{j} + \dot{z} \boldsymbol{k} .

**Example:**

A particle has position

.. math:: \boldsymbol{r} = (\cos t^2 ) \boldsymbol{i} + (\sin t^2) \boldsymbol{j} .

Find its velocity and speed as functions of time.

Acceleration
------------

The **acceleration** :math:`\boldsymbol{a}(t)` of a particle is the rate
of change of its velocity:

.. math:: \boldsymbol{a}(t) = \frac{\mathrm{d} \boldsymbol{v}}{\mathrm{d} t}  = \frac{\mathrm{d}^2 \boldsymbol{r}}{\mathrm{d} t^2},

or

.. math:: \boldsymbol{a} = \dot{\boldsymbol{v}} = \ddot{\boldsymbol{r}} ,

where two dots indicate two time derivatives.

.. _example-1:

**Example:**

Find the acceleration of the particle in the previous example.

Units
-----

| In SI units, :math:`x`, :math:`y`, :math:`z`, :math:`\boldsymbol{r}`
  are measured in metres :math:`\mathrm{m}`,
| velocity and speed are measured in metres per
  second :math:`\mathrm{ms}^{-1}`,
| and acceleration is measured in metres per second
  squared :math:`\mathrm{ms}^{-2}`.

.. margin::

   Mathematics questions don’t always use units, but if a question uses
   units then the answer should use units. Checking that the answer has the
   correct units can be a quick way to identify that a mistake has been
   made.

.. _example-2:

**Example:**

Particles :math:`P_1` and :math:`P_2` have position vectors
:math:`\boldsymbol{r}_1 = u_0 t \boldsymbol{j} - g t^2 \boldsymbol{k} / 2`
and
:math:`\boldsymbol{r}_2 = v_0 t \boldsymbol{i} - g t^2 \boldsymbol{k} / 2`,
respectively, where :math:`u_0`, :math:`v_0`, g are constants. Show that
at :math:`t=0` the paths of the particles are at right angles, while as
:math:`t \rightarrow \infty` they become parallel.

Note: in many problems we are free to choose where to place and how to
orient our axes and when to fix our origin in time. Good choices can
often assist calculations.

Validity of common sense notions of space and time
--------------------------------------------------

We have appealed to ‘common sense’ notions of time and space. The
physical world can be more subtle.



1. In relativity different observers disagree about measurements of
space and time (important when speeds approach the speed of light, or
when very large masses are involved).



2. In quantum mechanics particles do not have definite positions and
velocities — these are replaced by probability distributions (important
for very small systems such as atoms, electrons,...).

However, Newtonian mechanics and ‘common sense’ notions are applicable
to many objects provided they are not moving too quickly (speed much
less than that of light) and not too small.

.. margin::

   **Reading:** Collinson and Roper §1.4 space and time, §4.1 motion in
   space.

Initial conditions
------------------

Given :math:`\boldsymbol{r}(t)`, plainly we can find
:math:`\boldsymbol{v}(t)` and :math:`\boldsymbol{a}(t)` by
differentiating. Conversely, given :math:`\boldsymbol{a}`, say, we can
integrate to find :math:`\boldsymbol{v}` and :math:`\boldsymbol{r}`.
This introduces (vector) constants of integration. Often we can use
**initial conditions** or other information to fix these constants.

.. _example-3:

**Example:**

A particle has acceleration

.. math:: \boldsymbol{a} = t \boldsymbol{i} + t^2 \boldsymbol{j} + \alpha \boldsymbol{k}

where :math:`\alpha` is a constant. Given that at :math:`t=0` the
particle is at the origin and has velocity
:math:`\boldsymbol{v} = \boldsymbol{i}`, obtain the position and
velocity at a general time.

**Answer:**

First integrate :math:`\boldsymbol{a}`:

.. math::

   \begin{aligned}
   \boldsymbol{v} = \int \boldsymbol{a} \, \mathrm{d} t
   & = &
   \int (t \boldsymbol{i} + t^2 \boldsymbol{j} + \alpha \boldsymbol{k}) \, \mathrm{d} t
   \nonumber \\
   & = &
   \frac{t^2}{2} \boldsymbol{i} + \frac{t^3}{3} \boldsymbol{j} + \alpha t \boldsymbol{k} + \boldsymbol{C} .
   \nonumber
   \end{aligned}

:math:`\boldsymbol{C}` is the constant of integration. Note that it is a
*vector* constant, so written bold in print, underlined when
hand-written.

.. margin::

   *Always* underline vectors in your own working. Many unnecessary errors
   arise from not taking enough care with notation, e.g. failing to
   distinguish :math:`v`, :math:`\boldsymbol{v}` and :math:`V`, or
   :math:`\omega` and :math:`w`.

At the moment it is unknown. But we do know
:math:`\boldsymbol{v} = \boldsymbol{i}` at :math:`t=0`:

.. math:: \boldsymbol{i} = 0 \boldsymbol{i} + 0 \boldsymbol{j} + 0 \boldsymbol{k} + \boldsymbol{C} .

So :math:`\boldsymbol{C} = \boldsymbol{i}`:

.. math::

   \boldsymbol{v} =
   \left( 1 + \frac{t^2}{2} \right) \boldsymbol{i} + \frac{t^3}{3} \boldsymbol{j} + \alpha t \boldsymbol{k} .

Integrate again

.. math::

   \begin{aligned}
   \boldsymbol{r} = \int \boldsymbol{v} \, \mathrm{d} t
   & = &
   \int \left\{
   \left( 1 + \frac{t^2}{2} \right) \boldsymbol{i} + \frac{t^3}{3} \boldsymbol{j} + \alpha t \boldsymbol{k}
   \right\} \, \mathrm{d} t
   \nonumber \\
   & = &
   \left( t + \frac{t^3}{6} \right) \boldsymbol{i} + \frac{t^4}{12} \boldsymbol{j} + \frac{\alpha t^2}{2} \boldsymbol{k}
   + \boldsymbol{D} \nonumber
   \end{aligned}

where :math:`\boldsymbol{D}` is another (vector) constant of
integration. But :math:`\boldsymbol{r} = 0` at :math:`t = 0`
:math:`\Rightarrow` :math:`\boldsymbol{D} = \boldsymbol{0}`. Hence

.. math::

   \boldsymbol{r} =
   \left( t + \frac{t^3}{6} \right) \boldsymbol{i} + \frac{t^4}{12} \boldsymbol{j} + \frac{\alpha t^2}{2} \boldsymbol{k} .

Practice problems
-----------------

A body has position vector
:math:`\boldsymbol{r}=\boldsymbol{i} \cosh t  + \boldsymbol{j} \cos (3t) + \boldsymbol{k} (t^2 +1)`.
Obtain its velocity, speed, and acceleration.

Two particles have position vectors
:math:`\boldsymbol{r}_1 (t) = \boldsymbol{i} \cos (2t) + \boldsymbol{j} \sin (2t) + \boldsymbol{k} ct`;
:math:`\boldsymbol{r}_2 (t) = \boldsymbol{i} \cos (2t) - \boldsymbol{j} \sin (2t) + \boldsymbol{k} ct`.
At what time or times are the particle paths parallel? What is the
maximum value that :math:`c` may take while permitting the paths to
become perpendicular at some time?

Newton’s Laws
=============

So far we have not discussed what *causes* a body to move, accelerate,
etc. We now begin a study of **Dynamics** (in its strictest sense—we
will broaden the topic later), which is concerned with forces acting on
a body and how these determine the motion.

In classical mechanics we begin with **Newton’s laws**:

**First law.** A body will remain at rest or continue to move in a
straight line with constant velocity unless a force acts on it.

**Second law.** When an external force is applied to a body, the force
produces an acceleration proportional to the force. The constant of
proportionality is the mass of the body.

**Third law.** When a body :math:`A` exerts a force on a body :math:`B`
the body :math:`B` exerts an equal and opposite force on :math:`A`.

(Note there are various alternative statements of Newton’s laws. In
particular in deeper treatments the first law becomes a statement about
the existence of **inertial frames** in which particles move in straight
lines when no forces act.) Force is a vector, having magnitude and
direction. It has units of newtons, symbol :math:`\mathrm{N}`.
:math:`1 \, \mathrm{N} = 1 \, \mathrm{kg}\,\mathrm{ms}^{-2}`.

.. container:: figure*

   Gravity Electromagnetic forces

   |image|          |image1|

   Tension Drag or air resistance

   |image2|            |image3|

   Friction forces, normal reaction forces

                              |image4|

If there are several forces :math:`\boldsymbol{F}_1`,
:math:`\boldsymbol{F}_2`, ... acting on a body then the total force is

.. math:: \boldsymbol{F} = \sum_i \boldsymbol{F}_i .

Newton’s second law relates the total force to the acceleration:

.. math::

   \mathrm{force}
   \ = \ 
   \mathrm{mass}
   \ \times \ 
   \mathrm{acceleration}

i.e. 

.. math:: \boldsymbol{F} =  m \boldsymbol{a} .

Consequently, if :math:`\boldsymbol{F} = \boldsymbol{0}` (no external
force acting) then :math:`\boldsymbol{a} = \boldsymbol{0}`, so,
integrating,

.. math:: \boldsymbol{v} = \int \boldsymbol{a} \, \mathrm{d} t = \boldsymbol{c} = \ \mathrm{constant} .

Thus Newton’s first law follows from his second. Mass is measured in
kilograms (:math:`\mathrm{kg}`). In Newtonian theory the mass of a body
is constant.

.. _example-4:

**Example:**

A body of mass :math:`3` is subjected to a force
:math:`\boldsymbol{F} = \sin t \, \boldsymbol{i} + \mathrm{e}^{-t} \, \boldsymbol{j}`. Initially it
is at rest at the origin. Find its subsequent motion.

.. _answer-1:

**Answer:**

By :math:`\boldsymbol{F} = m \boldsymbol{a}`, the acceleration is

.. math:: \boldsymbol{a} = \frac{1}{3} \sin t \, \boldsymbol{i} + \frac{1}{3} \mathrm{e}^{-t} \, \boldsymbol{j} .

Integrate:

.. math:: \boldsymbol{v} = - \frac{1}{3} \cos t \, \boldsymbol{i} - \frac{1}{3} \mathrm{e}^{-t} \, \boldsymbol{j} + \boldsymbol{C}.

At :math:`t = 0`, :math:`\boldsymbol{v} = \boldsymbol{0}`, so

.. math:: \boldsymbol{0} = - \frac{1}{3} \boldsymbol{i} - \frac{1}{3} \boldsymbol{j} + \boldsymbol{C} ,

.. math:: \boldsymbol{C} = \frac{1}{3} \boldsymbol{i} + \frac{1}{3} \boldsymbol{j} ,

so

.. math:: \boldsymbol{v} = \frac{1}{3} ( 1 - \cos t ) \boldsymbol{i} + \frac{1}{3} (1 - \mathrm{e}^{-t} ) \boldsymbol{j} .

Integrate again:

.. math::

   \boldsymbol{r} =
   \frac{1}{3} ( t - \sin t ) \boldsymbol{i} + \frac{1}{3} (t + \mathrm{e}^{-t} ) \boldsymbol{j} + \boldsymbol{D}.

At :math:`t = 0`, :math:`\boldsymbol{r} = \boldsymbol{0}`, so

.. math::

   \boldsymbol{0} =
   0 \boldsymbol{i} + \frac{1}{3} \boldsymbol{j} + \boldsymbol{D}
   \ \ \ \ \Rightarrow \ \ \ \ 
   \boldsymbol{D} = - \frac{1}{3} \boldsymbol{j} ;

.. math::

   \boldsymbol{r} =
   \frac{1}{3} ( t - \sin t ) \boldsymbol{i} + \frac{1}{3} (t - 1 + \mathrm{e}^{-t} ) \boldsymbol{j} .

.. margin::

   **Reading:** Collinson and Roper §§4.2, 4.3.

.. _practice-problems-1:

Practice problems
-----------------

A body of mass :math:`m` is acted on by a force
:math:`\boldsymbol{F}(t)=\mu (1 - t) \boldsymbol{i}
+ \lambda t^2 \boldsymbol{j}`, where :math:`\mu` and :math:`\lambda` are
constants; obtain its motion if at :math:`t=0`,
:math:`\boldsymbol{r}= X_0 \boldsymbol{i}` and
:math:`\boldsymbol{v}=V_0 \boldsymbol{k}`.

A small block of mass :math:`m` starts from rest on a slope of a hill at
an angle :math:`\pi/6` to the horizontal and at height :math:`h` above
the horizontal. Find the acceleration of the block along the slope, and
its speed along the slope when it reaches the foot of the hill. Assume
there is a friction force of magnitude :math:`mg/4` pointing along the
slope (:math:`g` is the acceleration due to gravity).

A particle of mass :math:`m` falls vertically under gravity
(gravitational acceleration :math:`g`) and experiences a drag force due
to air resistance of magnitude :math:`C |v|^2` opposing the motion,
where :math:`v` is the particle’s speed and :math:`C` is a constant.
Find the terminal fall speed of the particle, i.e. the speed at which
the drag force balances the weight.

Numerical estimates for derivatives
===================================

We have seen how computers can help us to do calculations involving
(possibly lots of) arithmetic. But how can they help us with problems
involving calculus? Certain problems can be addressed by symbolic
manipulation packages such as Maple. Here we will learn about another
approach, in which a calculus problem is replaced by a problem involving
only arithmetic; specifically, derivatives are replaced by arithmetic
expressions that approximate the derivatives. Variations on this idea
underpin a great deal of scientific computing.

First order Euler finite difference scheme
------------------------------------------

By rearranging the Taylor series for :math:`f(x+h)`, namely

.. math:: f(x+h) = f(x) + h f'(x) + \tfrac{1}{2} h^2 f''(x) + \tfrac{1}{3!} h^3 f'''(x) + \cdots, \notag

we obtain the Forward Euler formula

.. math::

   \label{eq:fwdeuler}
   f'(x) = \frac{f(x+h) - f(x)}{h} + O(h).

.. margin::

   The error is actually :math:`\tfrac{1}{2} h f''(x)+ \cdots` but the
   :math:`O(h)` notation for the error is convenient as it isolates the
   important information that the error goes down proportional to :math:`h`
   when we reduce :math:`h`.

Similarly, by rearranging the Taylor series for :math:`f(x-h)`, namely

.. math:: f(x-h) = f(x) - h f'(x) + \tfrac{1}{2} h^2 f''(x) - \tfrac{1}{3!} h^3 f'''(x) + \cdots, \notag

we obtain the Backward Euler formula

.. math::

   \label{eq:bwdeuler}
   f'(x) = \frac{f(x) - f(x-h)}{h} + O(h).

Both are first order accurate—i.e. the leading truncation error scales
like :math:`h` to the power 1 as :math:`h \rightarrow 0`.

Second order centred difference scheme
--------------------------------------

By combining the Taylor series for :math:`f(x+h)` and :math:`f(x-h)` we
obtain the centred difference formula

.. math::

   \label{eq:cd2}
   f'(x) = \frac{f(x+h) - f(x-h)}{2h} + O(h^2).

This scheme is second order accurate.

Fourth order centred difference scheme
--------------------------------------

By combining the Taylor series for :math:`f(x+2h)`, :math:`f(x+h)`,
:math:`f(x-h)`, and :math:`f(x-2h)`, we obtain the fourth order centred
difference formula

.. margin::

   It is a good exercise to check this works and see how the given
   coefficients ensure the cancellation of a key term.

.. math:: f'(x) = \frac{-f(x+2h) + 8 f(x+h) -  8 f(x-h) + f(x-2h)}{12h} + O(h^4).

Centred difference formula for second derivative
------------------------------------------------

By combining Taylor series for :math:`f(x+h)` and :math:`f(x-h)` we can
obtain a formula for the second derivative

.. math::

   \label{eq:d2dx}
   f''(x) = \frac{f(x+h) - 2 f(x) + f(x-h)}{h^2} + O(h^2).

This is second order accurate.

Convergence
-----------

.. margin::

   :code:`# Examine convergence of`

.. margin::

   :code:`# Forward Euler`

.. margin::

   :code:`interval = []`

.. margin::

   :code:`err = []`

.. margin::

   :code:`for p in range(8):`

.. margin::

   :code:`    h = 0.5**(p+1)`

.. margin::

   :code:`    d = (sin(1 + h) - sin(1))/h`

.. margin::

   :code:`    interval.append(h)`

.. margin::

   :code:`    err.append(abs(d - cos(1)))`

.. margin::

   :code:`loglog(interval, err, ’b*’)`

The order of accuracy of a finite difference scheme predicts its
convergence rate, as always, with the proviso that the function is
sufficiently smooth so that enough terms in the Taylor series exist. For
example, we can check the convergence of the Forward Euler scheme on a
function for which we know the true derivative.

.. _example-5:

**Example:**

Adapt this code to compare the convergence of Forward Euler and centred
differences. Do their convergence rates agree with their orders of
accuracy?

.. _example-6:

**Example:**

.. margin::

   :code:`# First load the data`

.. margin::

   :code:`shtl = np.loadtxt(’STS121ascent.txt’)`

.. margin::

   :code:`# Pick out first column (time)`

.. margin::

   :code:`time = shtl[:, 0]`

.. margin::

   :code:`# and second column (altitude)`

.. margin::

   :code:`z = shtl[:, 1]`

.. margin::

   :code:`# How many data points?`

.. margin::

   :code:`n = len(time)`

.. margin::

   :code:`# Estimate vertical velocity`

.. margin::

   :code:`w = ...`

Download the shuttle data file from the ELE page and load it into
Python. Extract the first column (time) and second column (altitude) of
data. Use forward Euler to estimate the vertical velocity and the
vertical acceleration. Plot altitude, vertical velocity, and vertical
acceleration versus time.

.. container:: float
   :name: fig:KatherineJohnson

   .. container:: center

      |image5|

Gravity and projectiles
=======================

Newton’s law of universal gravitation
-------------------------------------

Given two masses :math:`m` and :math:`m'`, there is a force of
attraction between them proportional to :math:`m m'` and inversely
proportional to the square of the distance between them.

Suppose :math:`m` and :math:`m'` have position vectors
:math:`\boldsymbol{r}` and :math:`\boldsymbol{r}'`, respectively. Then
the force on :math:`m` due to :math:`m'` is

.. math:: \boldsymbol{F} = - G m m' \frac{(\boldsymbol{r} - \boldsymbol{r}')}{|\boldsymbol{r} - \boldsymbol{r}'|^3} ,

and the force on :math:`m'` due to :math:`m` is

.. math:: \boldsymbol{F}' = - G m m' \frac{(\boldsymbol{r}' - \boldsymbol{r})}{|\boldsymbol{r} - \boldsymbol{r}'|^3} ,

where :math:`G` is the gravitational; constant:
:math:`G = 6.67 \times 10^{-11} \mathrm{m}^3\mathrm{s}^{-2}\mathrm{kg}^{-1}`.

.. figure:: _static/images/gravitymm.png
   :figclass: margin
   :alt: 
   :width: 75mm

Notes.

. :math:`|\boldsymbol{F}| = |\boldsymbol{F}'|
= \displaystyle{\frac{G m m'}{|\boldsymbol{r}' - \boldsymbol{r}|^2}}
= \displaystyle{\frac{G m m'}{( \mathrm{distance\ from}\ m\ \mathrm{to}\ m' )^2}}`

. Since :math:`m`, :math:`m' > 0`, :math:`\boldsymbol{F}` and
:math:`\boldsymbol{F}'` are in the directions shown; the force is
attractive.

. :math:`\boldsymbol{F} = - \boldsymbol{F}'`, in agreement with Newton’s
third law.

When considering objects moving over moderate scales over Earth’s
surface, e.g., apples, balls, aeroplanes, shells, it is an excellent
approximation to model the gravitational force from the Earth on an
object of mass :math:`m` as

.. math:: \boldsymbol{F} = m \boldsymbol{g}

where :math:`\boldsymbol{g}` is a constant vector pointing vertically
downwards towards the centre of the Earth.
:math:`|\boldsymbol{g}| = g \approx 9.81 \, \mathrm{ms}^{-2}` is the
acceleration due to gravity.

We shall revisit the full inverse square law when we consider planetary
motion; however, for now we will take the gravitational force as
:math:`\boldsymbol{F} = m \boldsymbol{g}`. This force is called the
**weight** of the body.

.. _`sec:projectiles`:

Projectiles
-----------

Consider a point particle (e.g. a ball or a shell), mass :math:`m`, in
motion, and suppose the only force acting on it is gravity. We neglect
air resistance for now.

| Suppose the particle is launched (e.g. from a gun) from horizontal
  ground and that its initial velocity is :math:`\boldsymbol{V}`. To
  describe the motion we need to choose some axes; a good choice
  simplifies matters.
| (1) Take the time of launch to be :math:`t=0`.
| (2) Take the origin :math:`O` at the point of launch.
| (3) Take :math:`z` to be vertically upwards with :math:`z=0` the
  ground, so that :math:`\boldsymbol{g} = - g \boldsymbol{k}`.
| (4) Take the :math:`x`-axis such that :math:`\boldsymbol{V}` lies in
  the :math:`(x,z)`-plane:

  .. math:: \boldsymbol{V} = V \cos \alpha \, \boldsymbol{i} + V \sin \alpha \, \boldsymbol{k} ,

  where :math:`V = |\boldsymbol{V}|` is the initial speed, and
  :math:`\alpha` is the angle of :math:`\boldsymbol{V}` to the
  horizontal.

Now, by Newton’s second law :math:`\boldsymbol{F} = m \boldsymbol{a}`

.. math::

   m \boldsymbol{a} = m \ddot{\boldsymbol{r}} = m \boldsymbol{g}
   \ \ \ \Rightarrow \ \ \ 
   \ddot{\boldsymbol{r}} = \boldsymbol{g} = \mathrm{constant}

.. math:: \boldsymbol{v} = \dot{\boldsymbol{r}} = \int \boldsymbol{g} \, dt = \boldsymbol{g} t + \boldsymbol{C}

where :math:`\boldsymbol{C}` is the constant of integration. At
:math:`t = 0`, :math:`\dot{\boldsymbol{r}} = \boldsymbol{V}`
:math:`\Rightarrow \ \ \boldsymbol{C} = \boldsymbol{V}`.

.. math:: \dot{\boldsymbol{r}} = \boldsymbol{V} + \boldsymbol{g} t .

Integrating again,

.. math::

   \boldsymbol{r} = \int ( \boldsymbol{V} + \boldsymbol{g} t ) \, dt
   =
   \boldsymbol{V} t + \frac{1}{2} \boldsymbol{g} t^2 + \boldsymbol{D} .

At :math:`t = 0`,
:math:`\boldsymbol{r} = \boldsymbol{0} \ \ \Rightarrow \ \ \boldsymbol{D} = \boldsymbol{0}`:

.. math:: \boldsymbol{r} = \boldsymbol{V} t + \frac{1}{2} \boldsymbol{g} t^2 .

This is the complete vector solution for the motion.

Now let us examine the solution in component form.

.. math::

   \begin{array}{llll}
   \boldsymbol{V} & = V \cos \alpha \boldsymbol{i} &                & + V \sin \alpha \boldsymbol{k} \\
   \boldsymbol{g} & =                          &                & - g \boldsymbol{k}             \\
   \boldsymbol{r} & = x \boldsymbol{i}             & + y \boldsymbol{j} & + z \boldsymbol{k}             \\
   \end{array}

.. math::

   \boldsymbol{a} = \boldsymbol{g} \ \ 
   \Rightarrow \ \ 
   \left.
   \begin{array}{lll}
   \ddot{x} & = & 0 \\
   \ddot{y} & = & 0 \\
   \ddot{z} & = & -g \\
   \end{array}
   \right\}
   \label{eq:accelxyz}

.. math::

   \boldsymbol{v} = \dot{\boldsymbol{r}} = \boldsymbol{V} + \boldsymbol{g} t \ \ 
   \Rightarrow \ \ 
   \begin{array}{lll}
   \dot{x} & = & V \cos \alpha \\
   \dot{y} & = & 0             \\
   \dot{z} & = & V \sin \alpha - g t \\
   \end{array}

.. math::

   \boldsymbol{r} = \boldsymbol{V} t + \frac{1}{2} \boldsymbol{g} t^2 \ \ 
   \Rightarrow \ \ 
   \begin{array}{lll}
   x & = & V t \cos \alpha \\
   y & = & 0               \\
   z & = & V t \sin \alpha - \frac{1}{2} g t^2
   \end{array}

Note we could, instead, have started with
eq:accelxyz and integrated, without using vectors.
Note also that :math:`y=0` for all times :math:`t`. This is a result of
choosing the initial velocity to be in the :math:`(x,z)`-plane; once the
motion starts in that plane it remains there. Now that we have checked
this, we can drop :math:`y` and just use :math:`x` and :math:`z` for
this type of problem.

.. margin::

   **Reading:** Collinson and Roper §5.1 gravity, §4.4 projectiles.

The above solution

.. math::

   \begin{aligned}
   x & = & V t \cos \alpha   \nonumber \\
   z & = & V t \sin \alpha - \frac{1}{2} g t^2  \nonumber
   \end{aligned}

gives the **trajectory** of the particle as the curve
:math:`(x(t),z(t))` parameterized by :math:`t`. To find :math:`z = z(x)`
as a function of :math:`x`, eliminate

.. math::

   t = \frac{x}{V \cos \alpha}
   \label{eq:ttraj}

to obtain

.. math::

   \begin{aligned}
   z & = & x \tan \alpha - \frac{g x^2}{2 V^2 \cos^2 \alpha}  \nonumber \\
     & = & x \left( \tan \alpha - \frac{g x}{2 V^2 \cos^2 \alpha} \right) . \nonumber
   \end{aligned}

This is the **trajectory equation**. :math:`z` is a quadratic function
of :math:`x`, so the curve is a **parabola**. It passes through the
:math:`x`-axis (:math:`z=0`) at

.. math:: x = 0 , \qquad \qquad x = \frac{2V^2}{g} \sin \alpha \cos \alpha = \frac{V^2}{g} \sin 2 \alpha .

If the ground is horizontal then the **range** of the projectile,
i.e. the distance before hitting the ground, is

.. math:: R = \frac{V^2}{g} \sin 2 \alpha .

The maximum value of :math:`z` along the trajectory, i.e. the
**height** :math:`h`, is achieved when :math:`\dot{z} = 0`, which occurs
at :math:`t = (V/g) \sin \alpha`, and is given by

.. math:: h = V t \sin \alpha - \frac{1}{2} g t^2 = \frac{V^2 \sin^2 \alpha }{2 g} .

Also, from eq:ttraj, we know :math:`t` as a function
of :math:`x`, so when the projectile lands at :math:`x = R` the **time
spent in flight** is

.. math:: T = \frac{R}{V \cos \alpha} = \frac{2 V}{g} \sin \alpha .

Now suppose we can vary :math:`\alpha`, with :math:`V` and :math:`g`
constant. Then the range :math:`R` is a maximum when
:math:`\sin 2 \alpha = 1`, which happens at :math:`\alpha = \pi / 4`. In
this case :math:`R = R_\mathrm{max} = V^2 / g`.

The height is a maximum when
:math:`\sin \alpha = 1 \ \ \Rightarrow \ \ \alpha = \pi/2` and the
particle is projected vertically upwards. Then
:math:`h = h_\mathrm{max} = V^2/(2g)`.

.. _example-7:

**Example:**

A particle is projected with velocity :math:`V` at an angle
(a) :math:`\pi/6`, (b) :math:`\pi/3` to the horizontal. Calculate its
range, height, and time of flight in each case.

.. _answer-2:

**Answer:**

Note :math:`\sin (\pi/3) = \sin (2\pi/3) = \sqrt{3}/2`,
:math:`\sin (\pi / 6) = 1/2`, so for (a)

.. math::

   R = \frac{\sqrt{3}}{2} \frac{V^2}{g} , \qquad
   h = \frac{V^2}{8 g} , \qquad
   T = \frac{V}{g};

and for (b)

.. math::

   R = \frac{\sqrt{3}}{2} \frac{V^2}{g} , \qquad
   h = \frac{3 V^2}{8 g} , \qquad
   T = \frac{\sqrt{3} V}{g} .

.. figure:: _static/images/twotrajectories.png
   :figclass: margin
   :alt: 
   :width: 65mm

.. _example-8:

**Example:**

A ball is projected with speed :math:`\sqrt{3gH}` in a plane
perpendicular to a vertical wall of height :math:`H` a distance
:math:`H` away. Find the range of angles of projection that allow the
ball to pass over the wall.

.. _answer-3:

**Answer:**

Let :math:`\alpha` be the angle of projection, and we know the launch
speed is :math:`V = \sqrt{3 g H}`. The equation of the trajectory is

.. math::

   \begin{aligned}
   z & = & x \tan \alpha - \frac{g x^2}{2 V^2 \cos^2 \alpha} \nonumber \\
     & = & x \tan \alpha - \frac{x^2}{6 H} (1 + \tan^2 \alpha ) \nonumber
   \end{aligned}

When :math:`x = H`,

.. math:: z = H \left( \tan \alpha - \frac{1}{6} - \frac{1}{6} \tan^2 \alpha \right)

and for the ball to go over the wall this :math:`z` must be
:math:`\ge H`, i.e. we need

.. math::

   \tan \alpha - \frac{1}{6} - \frac{1}{6} \tan^2 \alpha \ge 1 .
   \label{eq:trajwall}

Let :math:`Q = \tan \alpha`. Then we need :math:`Q^2 - 6 Q + 7 \le 0`.
The roots of the quadratic are given by

.. math:: Q = \frac{6 \pm \sqrt{36 - 28}}{2} = 3 \pm \sqrt{2} .

Thus, eq:trajwall is satisfied when
:math:`3 - \sqrt{2} \le \tan \alpha \le 3 + \sqrt{2}`. The ball passes
over the wall when

.. math:: 3 - \sqrt{2} \le \tan \alpha \le 3 + \sqrt{2}

.. math:: 1.01 \le \alpha \le 1.35 .

.. _practice-problems-2:

Practice problems
-----------------

A long jumper attains a horizontal component of her velocity of
:math:`8 \, \mathrm{ms^{-1}}` at take-off. What is the minimum vertical
component of velocity she needs at take-off in order to jump a distance
of :math:`6 \, \mathrm{m}` ? In this case, what would her maximum height
be? [Take :math:`g\simeq 10 \, \mathrm{ms}^{-2}`.]

A particle is projected with speed :math:`3 (gh / 2)^{1/2}` from a
point :math:`O` on a horizontal floor. The particle reaches a point a
horizontal distance :math:`3h` from :math:`O` on the edge of a table of
height :math:`h`. Find the two possible angles of projection.

If a particle is projected from the horizontal floor of a large room
whose ceiling is at a height of :math:`3 \, \mathrm{m}`, what will its
greatest possible range be if its speed of projection is
(a) :math:`8 \,\mathrm{ms^{-1}}`, (b) :math:`12 \, \mathrm{ms^{-1}}` ?
[Take :math:`g\simeq 10 \, \mathrm{ms}^{-2}`.]

.. _`sec:envelope`:

The envelope equation
---------------------

Suppose we have a gun that fires shells at a given speed :math:`V` and
at any angle :math:`\alpha` to the horizontal. Which points of the
:math:`(x,z)`-plane can we hit?

We know that the trajectory is given by

.. math:: z = x \tan \alpha - \frac{g x^2}{2 V^2 \cos^2 \alpha} .

Thus it goes through a point :math:`(X,Z)` if

.. math:: Z = X \tan \alpha - \frac{g X^2}{2 V^2 \cos^2 \alpha} ,

i.e. if

.. math:: Z = X \tan \alpha - \frac{g X^2}{2 V^2} (1 + \tan^2 \alpha),

i.e. if

.. math:: g X^2 \tan^2 \alpha - 2 V^2 X \tan \alpha + (2 V^2 Z + g X^2) = 0 .

Given :math:`g` and :math:`V`, we can hit :math:`(X,Z)` if this equation
has a real solution for :math:`\alpha`. The equation is a quadratic in
:math:`\tan \alpha` and has solutions.

.. math::

   \begin{aligned}
   \tan \alpha & = & \frac{-B \pm (B^2 - 4 A C)^{1/2}}{2 A}  \nonumber \\
               & = & \frac{V^2 X \pm (V^4 X^2 - g X^2 (2 Z V^2 + g X^2))^{1/2}}{g X^2} .
   \end{aligned}

There are three possibilities

#. The quadratic has two real roots: there are two possible angles for
   which the trajectory passes through :math:`(X,Z)`.

#. The quadratic has one repeated root: just one value of :math:`\alpha`
   allows us to hit :math:`(X,Z)`.

#. The quadratic as no real roots: it is impossible to hit :math:`(X,Z)`
   for any :math:`\alpha`.

Which case occurs depends on the discriminant
:math:`\Delta = B^2 - 4 A C` of the quadratic. If
:math:`\Delta / 4 = V^4 X^2 - g X^2 (2 Z V^2 + g X^2)`
- ... is positive then we have two real roots, case 1.
- ... is zero then we have one real root, case 2.
- ... is negative then we have no real roots, case 3.

The key case is case 2, which occurs when

.. math:: V^4 X^2 = g X^2 (2 Z V^2 + g X^2) ,

i.e.,

.. math::

   \label{eq:envelope}
   Z = \frac{V^2}{2 g} - \frac{g X^2}{2 V^2} .

All points that can be hit with just one angle :math:`\alpha` lie on
this curve :math:`\mathcal{C}`. If we sketch the curve we have

- :math:`X = 0 \ \ \Rightarrow \ \ Z = V^2 / 2 g` (maximum height for
  gun);
- :math:`Z = 0 \ \ \Rightarrow \ \ X = \pm V^2 / g` (maximum range for
  gun).

.. figure:: _static/images/envelope.png
   :alt: 
   :width: 170mm

The curve :math:`\mathcal{C}` is called the **envelope** of the
trajectories. It divides the :math:`(x,z)`-plane into the region within
range and the region out of range.
Equation eq:envelope is the **envelope equation**.

.. _example-9:

**Example:**

A ball is projected with speed :math:`V` in a plane perpendicular to a
wall of height :math:`H` a distance :math:`H` away. What is the
*minimum* speed required for the ball to pass over the wall?

.. _answer-4:

**Answer:**

Given :math:`V`, we can obtain the envelope :math:`\mathcal{C}` of the
trajectories launched from :math:`O` with this speed :math:`V`.

.. container:: float
   :name: fig:evelope_over_under

   |image6|
   |image7|

For the ball to go over the wall, the top of the wall
:math:`(X,Z) = (H,H)` must lie inside or on :math:`\mathcal{C}`. At the
minimum possible speed :math:`V`, the top of the wall
:math:`(X,Z) = (H,H)` must lie *on* :math:`\mathcal{C}`. Hence

.. math:: H = \frac{V^2}{2 g} - \frac{g H^2}{2 V^2} ,

.. math:: 2 = \frac{V^2}{gH} - \frac{g H}{V^2} .

Substitute :math:`\mu = V^2 / (g H)`, and solve the resulting quadratic
equation in :math:`\mu` to obtain

.. math:: \mu = 1 \pm \sqrt{2} .

Since :math:`V^2`, :math:`g` and :math:`H` are all positive, only the
positive root makes physical sense, i.e., :math:`\mu = 1 + \sqrt{2}`.
Therefore the minimum speed is

.. math:: V = \sqrt{\mu g H} = \left( (1 + \sqrt{2}) g H \right)^{1/2} .

.. _practice-problems-3:

Practice problems
-----------------

A particle is launched with speed :math:`V = \sqrt{4gh}` in a plane
perpendicular to a wall located a horizontal distance :math:`h` from the
point of launch. What is the maximum height of the wall over which the
particle can pass?

A gun is located at :math:`x = 0` on top of a hill whose height
:math:`z(x)` is described by :math:`z = 4h - x^2 / h`, where :math:`h`
is a constant. The gun fires shells at speed :math:`V = \sqrt{g h} / 2`.
(i) Determine the value of :math:`x` for the most distant point on the
hillside that the gun can hit. (ii) A target is located on the hillside
at :math:`x = 2h`. Determine the smallest value of :math:`x` to which
the gun must be moved so that the target is just within range.

.. _`sec:air_res_I`:

Projectiles with air resistance: part I
=======================================

Real projectiles are subject to air resistance. A reasonable
mathematical model for the aerodynamic drag force on a particle is

.. math:: \boldsymbol{F}_\mathrm{D} = - C |\boldsymbol{v}| \boldsymbol{v} ,

where :math:`\boldsymbol{v}` is the velocity of the particle and
:math:`C = \rho_\mathrm{a} C_\mathrm{D} A`, with :math:`\rho_\mathrm{a}`
the air density, :math:`C_\mathrm{D}` a drag coefficient, and :math:`A`
the cross-sectional area of the particle [1]_. For our purposes we can
take :math:`\rho_\mathrm{a}`, :math:`C_\mathrm{D}`, and :math:`A`, and
hence :math:`C`, as constants. Newton’s second law then becomes

.. math::

   \label{eq:proj_air_res}
   m \ddot{\boldsymbol{r}} = - m \boldsymbol{g} - C |\boldsymbol{v}| \boldsymbol{v} .

Although strictly the *drag coefficient* is :math:`C_{\mathrm{D}}` as
defined above, it is convenient in the informal discussion below to
refer to :math:`C` as the drag coefficient. Note that

.. math:: |\boldsymbol{F}_\mathrm{D} |= - C |\boldsymbol{v}|^2

and so the magnitude of the drag is quadratic in the speed of the body.

.. margin::

   Calculation of the drag on a body is a topic in *fluid dynamics*.
   Quadratic drag is appropriate for bodies such as cricket balls moving
   through the air (and we are assuming no wind), but Magnus effects can
   also arise from rotation. For a body moving in a viscous fluid, for
   example a bead sinking in liquid honey, the force is linear
   :math:`|\boldsymbol{F}_\mathrm{D} | \propto |\boldsymbol{v}|`.

We can find closed form solutions to this equation only in three special
cases:

#. when :math:`C = 0`, as we have seen above;

#. when :math:`\boldsymbol{g} = \boldsymbol{0}`;

#. when the motion is purely vertical.

When :math:`\boldsymbol{g} = \boldsymbol{0}` the direction of the
particle’s velocity never changes and the motion is effectively
one-dimensional. If we choose axes so that the motion is in the positive
:math:`x`-direction then the equation of motion becomes

.. math:: m \ddot{x} = - C \dot{x}^2 ,

which can be integrated twice to obtain

.. math:: x = \frac{m}{C} \log \left( 1 + \frac{t}{t_0} \right) ,

where :math:`t_0` is a constant of integration related to the initial
speed, and we have assumed :math:`x=0` at :math:`t=0`. [Exercise: check
that this solution satisfies the equation of motion.]

When the motion is purely vertical then again we have a one-dimensional
problem:

.. math::

   \label{eq:vertical_with_drag}
   m \ddot{z} = - m g \pm C \dot{z}^2 ,

with a minus sign when the motion is upward and a plus sign when the
motion is downward. It turns out that this, too, can be integrated to
give

.. math::

   z = \left\{
   \begin{array}{ll}
   \ \ \ \frac{m}{C} \log \left\{ \cos \left( \sqrt{gC/m} \, t \right) \right\}  &
   - \pi / 2 \sqrt{gC/m} < t \le 0 ,\\
   - \frac{m}{C} \log \left\{ \cosh \left( \sqrt{gC/m} \, t \right) \right\}  &
   t > 0 ,
   \end{array}
   \right.

where the constants of integration have been chosen so that the particle
comes to rest at :math:`z=0` at :math:`t=0`. For the first part the
particle is moving upwards and :math:`t<0`, then for :math:`t>0` it is
moving downwards, while at :math:`t=0` it is at maximum height.
[Exercise: check that this solution satisfies the equation of
motion—take care to choose the appropriate sign in
eq:vertical_with_drag.]

For more general cases our only option is to find a numerical solution.
So we now need to look at numerical methods for initial value problems.

.. _`sec:time_stepping`:

Numerical methods for Initial Value Problems
============================================

The methods we look at in this section are often referred to as *time
stepping* or *time integration* methods. To begin with we consider a
first order (i.e. a single derivative) ordinary differential equation
(ODE) for a single scalar variable

.. math::

   \label{eq:ODE1}
   \frac{d y}{d t} = f(y,t) .

We will see below that the ideas extend straightforwardly to systems of
equations (section `6.4 <#sec:step_systems>`__) and to higher order
equations (section `7.1 <#sec:step_higher_systems>`__).

Let us try to find a numerical solution at a set of uniformly spaced
times :math:`\{ t_0,\ t_1,\ \ldots,\ t_n,\ \ldots \}`, where
:math:`t_n = nh` and :math:`h` is the time step. Let :math:`y_n` be our
approximate numerical solution at time :math:`t_n`. We assume that we
are given the initial condition :math:`y_0`.

Single-step finite difference methods
-------------------------------------

Now we need some way to calculate :math:`y_{n+1}` from :math:`y_n`; this
will allow us to step forward from :math:`y_0` to :math:`y_1`, from
:math:`y_1` to :math:`y_2`, and so on until we have built up a solution
over the desired time range.

Forward Euler
^^^^^^^^^^^^^

.. margin::

   :code:`# Solve dy/dt = y(1 - y)`

.. margin::

   :code:`# using Forward Euler`

.. margin::

   :code:`# Final time and time step`

.. margin::

   :code:`Tstop = 5`

.. margin::

   :code:`nstop = 50`

.. margin::

   :code:`h = Tstop/nstop`

.. margin::

   :code:`# Initial value`

.. margin::

   :code:`y = 0.1`

.. margin::

   :code:`# Time step loop`

.. margin::

   :code:`for n in range(nstop):`

.. margin::

   :code:`    y = y + h*y*(1 - y)`

The simplest time stepping method is the forward Euler method. It is
obtained by using the forward Euler approximation
eq:fwdeuler for the time derivative

.. math:: \frac{\mathrm{d} y}{\mathrm{d} t} (t_n) \approx \frac{y_{n+1} - y_n}{h}.

The ODE eq:ODE1 then becomes

.. math::

   y_{n+1} = y_n + h f(y_n, t_n) .
   \label{eq:fwdeulerstep}

Thus, if we know :math:`y_n` then we can evaluate the right hand side
and hence obtain :math:`y_{n+1}`. Starting with the initial condition
:math:`y_0`, we can successively find :math:`y_1`, :math:`y_2`, etc.
This idea is at the heart of all single-step finite difference methods.

.. _example-10:

**Example:**

Use the Forward Euler method to obtain a numerical solution of
:math:`dy/dt = y(1-y)` at :math:`t = 5` given :math:`y = 0.1` at
:math:`t = 0`. Take :math:`h = 0.1`.

Midpoint method
^^^^^^^^^^^^^^^

There are many other single-step methods.

.. margin::

   For example, look up Runge-Kutta methods.

Here we mention just one other: the midpoint method.

Here we attempt to calculate :math:`dy/dt` in the middle of the
timestep, at :math:`t=t_n+h/2`. If the present moment is :math:`t_n`,
then :math:`t=t_n+h/2` is in the future. So first we need an estimate of
:math:`y` at the future time :math:`t=t_n+h/2`, :math:`y = y_*`, say. We
can use Forward Euler to obtain this estimate. Thus, the formula is

.. math::

   \begin{aligned}
       y_* & = & y_n + \frac{h}{2} f(y_n, t_n),\\
       y_{n+1} & = & y_n + h f\left(y_*, t_n+ h/2 \right).
   \end{aligned}

Multi-step methods
------------------

If we use the second order centred difference method
eq:cd2 to approximate the time derivative then the ODE
eq:ODE1 becomes

.. math:: y_{n+1} = y_{n-1} + 2hf(y_n,t_n) .

This method is known as the leapfrog method. It requires us to know both
:math:`y_{n-1}` and :math:`y_n` in order to step forward to
:math:`y_{n+1}`, so it is an example of a *multi-step method*.

.. margin::

   Other multi-step schemes include the Adams-Bashforth methods.

Note that in order to apply the leapfrog scheme we must do something
else, such as Forward Euler, for the first time step, since we don’t
have :math:`y_{-1}`.

Orders of accuracy and convergence
----------------------------------

Using the Taylor series eq:taylor_series shows
that the error made in one Forward Euler time step
eq:fwdeulerstep is :math:`O(h^2)`. However, the
number of steps needed to reach a given time :math:`T` is
:math:`\propto 1/h`, and the errors will accumulate step by step.
Therefore the error in the solution at time :math:`T` is expected to be
:math:`O(h)`. Thus, the Forward Euler method is said to be first-order
accurate. This analysis predicts that, if we repeat the calculation
using different values of :math:`h`, the error at time :math:`T` should
get smaller, i.e. the numerical solution should *converge* to the true
solution, at a certain rate as :math:`h \rightarrow 0`.

For both the midpoint method and the leapfrog method, Taylor series
analysis shows that the methods are second-order accurate. Thus, the
error at time :math:`T` is expected to be :math:`O(h^2)`, etc.

Note that these predictions depend on the validity of the Taylor series
expansion from which the schemes are derived. Worse convergence may be
achieved in practice if the solution is not sufficiently smooth. The
predictions can also fail if the scheme is unstable—see
section sec:stability.

.. _`sec:step_systems`:

Time stepping systems of equations
----------------------------------

To apply the above time stepping methods to systems of equations we
simply replace the scalar variable :math:`y` and function :math:`f` by
arrays or vectors :math:`\boldsymbol{y}` and :math:`\boldsymbol{f}`:

.. math::

   \label{eq:ODE12}
   \frac{d \boldsymbol{y}}{d t} = \boldsymbol{f}(\boldsymbol{y},t) .

For example, the forward Euler method becomes

.. math::

   \boldsymbol{y}_{n+1} = \boldsymbol{y}_n + h \boldsymbol{f}(\boldsymbol{y}_n, t_n) .
   \label{eq:fwdeulerstepsys}

For coding it may be convenient to split the equations into their
components.

.. _example-11:

**Example:**

Find and plot a numerical solution of the SIR model over 200 days. Use
the values of :math:`S_0`, :math:`I_0`, :math:`r`, and :math:`a` given
in section sec:built-in.

.. code-block:: python

   # Solve SIR using Forward Euler

   import matplotlib.pyplot as plt

   # Final time and time step
   Tstop = 200
   nstop = 200
   h = Tstop/nstop

   # Constants
   r = 3e-9
   a = 1/14

   # Initial values
   t = [0]
   S = [6e7]
   I = [1000]
   R = [0]

.. code-block:: python

   # Time step loop
   for n in range(nstop):
       t.append(t[n] + h)
       S.append(S[n] - h*r*I[n]*S[n])
       I.append(I[n] + h*(r*I[n]*S[n] - a*I[n]))
       R.append(R[n] + h*a*I[n])

   # Plot results
   plt.plot(t, S, 'b', label='S')
   plt.plot(t, I, 'r', label='I')
   plt.plot(t, R, 'k', label='R')
   plt.legend()
   plt.xlabel('Time (days)')
   plt.ylabel('Number')
   plt.show()

Does the maximum number of infected people agree with the value
predicted by eq:Imax?

In section sec:fpi we found the value of :math:`q`
needed to obtain :math:`I_\mathrm{max} = 10^5`. Set :math:`r = aq` for
this value of :math:`q` and re-run the code; do we get
:math:`I_\mathrm{max} \approx 10^5`? (You might need to run for more
days.)

Projectiles with air resistance: part II
========================================

We now have almost all the numerical methods we need to investigate
projectiles with air resistance. However, the time stepping methods we
have seen apply to first order ODEs whereas Newton’s second law gives us
second order ODEs. What can we do?

.. _`sec:step_higher_systems`:

Time stepping higher order ODEs
-------------------------------

Suppose we are given a second order ODE

.. math:: \frac{d^2 y}{d t^2} = f(y, \dot{y}, t) .

This can always be re-written as a pair of first order ODEs by
introducing a new variable :math:`z = \dot{y}`, say:

.. margin::

   This pair of ODEs will need two initial conditions, one on :math:`y` and
   one on :math:`z`. This makes it clear why the original second order ODE
   also needs two initial conditions.

.. math::

   \begin{aligned}
   \frac{d y}{d t} & = & z ; \nonumber \\
   \frac{d z}{d t} & = & f(y, z, t) . \nonumber
   \end{aligned}

We can apply any of the time stepping schemes we have met to this pair
of equations.

Clearly a similar trick can be used with higher order ODEs and with
systems of second order and higher order ODEs.

.. _`sec:air_resistance_examples`:

Projectiles with air resistance
-------------------------------

To solve eq:proj_air_res numerically we can
first split it into horizontal and vertical components

.. math::

   \begin{aligned}
   m \ddot{x} & = & \ \ \ \ \ \ \ \ \ - C |\boldsymbol{v}| \dot{x} , \nonumber \\
   m \ddot{z} & = & -m g              - C |\boldsymbol{v}| \dot{z} , \nonumber
   \end{aligned}

and then introduce new variables :math:`u = \dot{x}`,
:math:`w = \dot{z}` to obtain a system of first order equations

.. math::

   \begin{aligned}
     \dot{x}  & = & u , \nonumber \\
     \dot{z}  & = & w , \nonumber \\
   m \dot{u} & = & \ \ \ \ \ \ \ \ \ - C |\boldsymbol{v}| u , \nonumber \\
   m \dot{w} & = & - m g             - C |\boldsymbol{v}| w , \nonumber
   \end{aligned}

where :math:`\boldsymbol{v} = (u,w)` and
:math:`|\boldsymbol{v}| = (u^2 + w^2)^{1/2}`.

.. margin::

   Note how the air resistance term couples the horizontal and vertical
   component equations; we can’t solve them separately as we did in
   section `4.2 <#sec:projectiles>`__

Now we can use, for example, a Forward Euler method, as we did in
section `6.4 <#sec:step_systems>`__ to obtain a numerical solution.
Since we have four equations we will need four initial conditions, for
example the :math:`x`- and :math:`z`-components of the initial position
and velocity.

.. _example-12:

**Example:**

Write a Python code to solve these equations. You might want to take the
code of section `6.4 <#sec:step_systems>`__ as a template.

It is very important to test any code to make sure it does what it is
supposed to. For this problem we have closed form solutions in three
cases (section `5 <#sec:air_res_I>`__) that we can compare our numerical
solution against.

.. _example-13:

**Example:**

Let us reconsider the problem from section `4.2 <#sec:projectiles>`__,
but now including air resistance. A ball is projected with speed
:math:`\sqrt{3gH}` in a plane perpendicular to a vertical wall of height
:math:`H` a distance :math:`H` away. Let us fix the magnitude of the
drag coefficient :math:`C` by taking :math:`C/m = 0.1/H`. Find the range
of angles of projection that allow the ball to pass over the wall. We
can no longer solve this problem analytically, but we can still answer
the question by computing numerical solutions for different launch
angles :math:`\alpha`. It turns out that the solution is independent of
the values given for :math:`H` and :math:`g`, so we can choose to work
in units [2]_ for which :math:`H=1`, :math:`g=1`. It is a very good idea
to check that your code gives the correct solution for the case of zero
drag :math:`C/m = 0` first! Do you find that the range of angles to
clear the wall increases or decreases when air resistance is included?

.. _example-14:

**Example:**

We can also revisit the example from section `4.3 <#sec:envelope>`__. A
ball is projected with speed :math:`V` in a plane perpendicular to a
wall of height :math:`H` a distance :math:`H` away, with
:math:`C/m = 0.1/H`. What is the *minimum* speed required for the ball
to pass over the wall? Once again we can no longer solve the problem
analytically, but we can obtain an answer using a trial-and-error
approach with the code for the above example. (We will see another way
to tackle this example in section sec:adhoc.)

.. [1]
   You may notice an apparent inconsistency between treating a body as a
   point particle and allowing it to have a finite cross-sectional area.
   In this case it does not lead to any problems. But, more generally,
   we do need to be on the lookout for possible inconsistent assumptions
   and approximations in our modelling.

.. [2]
   A very useful technique in applied mathematics is
   *non-dimensionalization*. We won’t say more about this here, but that
   is effectively what we have done.

.. |image| image:: _static/images/schematic_gravity.png
   :width: 60mm
.. |image1| image:: _static/images/schematic_electromagnetic.png
   :width: 60mm
.. |image2| image:: _static/images/schematic_spring.png
   :width: 60mm
.. |image3| image:: _static/images/schematic_drag.png
   :width: 60mm
.. |image4| image:: _static/images/schematic_friction.png
   :width: 80mm
.. |image5| image:: _static/images/KatherineJohnson.jpg
   :width: 2.5cm
.. |image6| image:: _static/images/envelope_over.png
   :width: 70mm
.. |image7| image:: _static/images/envelope_under.png
   :width: 73mm
