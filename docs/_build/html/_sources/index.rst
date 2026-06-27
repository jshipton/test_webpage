Mathematical Modelling
######################

.. toctree::
   :maxdepth: 2
   :hidden:

   self
   python1
   numerical_analysis
   interpolation
   python2
   lec-notes-ch-2
   glossary

.. _intro:

Introduction
============

      This module will show how to use the mathematics of calculus,
      vectors, and matrices to model and understand real physical
      systems. We will use Newtonian dynamics to look at projectiles,
      oscillations, and other mechanical systems.

.. _ overview:

Overview of Mathematical Modelling
----------------------------------

      .. figure:: _static/images/IsaacNewton.png
         :figclass: margin

      This module will introduce you to some of the kinds of
      mathematical models that are used to understand and predict the
      behaviour of the real world, along with some of the analytical and
      computational methods used to work with those models.

      .. figure:: _static/images/lotkavolterra.png
         :figclass: margin

         A model of competing populations.

      Some types of mathematical models are based on physical principles
      that are so well established that they are considered to be 'Laws
      of Nature'; Newton's Laws of Motion and his Law of Gravitation are
      prime examples.

      .. figure:: _static/images/butterfly.png
         :figclass: margin

         A solution trajectory for the Lorenz equations.

      Other types of mathematical model are rather more empirical,
      though they can still be extremely useful. Examples that we will
      look at include Lotka-Volterra models for population dynamics.

      The term **Dynamical System** can refer to any system with time
      dependence. Examples include Newtonian dynamics, population
      dynamics, the spread of infectious diseases, and much more.

      **Example:** To make progress as applied mathematicians we must
      work with **approximate models**. For example, consider a car
      on a rollercoaster. What factors can we ignore, and which are
      essential?

      .. figure:: _static/images/rollercoaster.png

         A sketch of a rollercoaster.

      In some cases (actually rather rare in the messy real world) we
      can solve a mathematical model using :term:`analytical`
      methods, for example based on calculus, vectors, or matrices,
      and obtain exact formulae.

.. _python:

Python
------

      To learn about computational methods in mathematical modelling we
      will use the language **Python**. The key concepts behind coding
      in Python are the same as those behind coding in many modern
      programming languages.

      In the first few weeks of this module we will spend some time
      learning enough Python to be able to do something interesting.

      .. rubric:: Getting Started
         :name: getting-started

      - You can use Python on any PC across the University, in
        particular during our computer practical laboratory sessions.
        You need to launch Anaconda Navigator and we will use Jupyter
        Lab.
      - If you have your own laptop or desktop you can install Anaconda
        following the `instructions
        here <https://www.anaconda.com/download>`__.

      There are many excellent resources for learning Python. See the
      books on the reading list below and links under the Python tile on ELE.

.. _books:

Books
-----

      +----------------------+----------------------+----------------------+
      | Author               | Title                | Notes                |
      +======================+======================+======================+
      | **Collinson and      | **Particle           | Course book;         |
      | Roper**              | Mechanics**          | strongly recommended |
      +----------------------+----------------------+----------------------+
      | **Dyke and           | **Guide to           | Nice                 |
      | Whitworth**          | Mechanics**          | discussion           |
      +----------------------+----------------------+----------------------+
      | **Smith and Smith**  | **Mechanics**        | More advanced        |
      +----------------------+----------------------+----------------------+
      | **Lunn**             | **A First Course in  | Even more advanced   |
      |                      | Mechanics**          |                      |
      +----------------------+----------------------+----------------------+
      | **Strogatz**         | **Nonlinear Dynamics | Very clearly written |
      |                      | and Chaos**          | with nice examples   |
      +----------------------+----------------------+----------------------+

.. _python-books:

Python Books
------------

      +---------------------------+------------------------------------------+
      | **Kong, Siauw and Bayen** | **Python programming and numerical       |
      |                           | methods: A guide for engineers and       |
      |                           | scientists**                             |
      +---------------------------+------------------------------------------+
      | **Langtangen**            | **A primer on scientific programming     |
      |                           | with Python**                            |
      +---------------------------+------------------------------------------+

      *Most of these are available online - follow the links under the
      Access your Reading List tile on ELE.*
