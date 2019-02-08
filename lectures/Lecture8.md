---
layout: post
title: Shottkey Two-State Model
---

### Review

We reviewed the fundamental equation of thermodynamics ([Lecture 5](Lecture5.md)) and thermodynamic potentials ([Lecture 6](Lecture6.md) and [Lecture 7](Lecture7.md))

### Shottkey Two-State Model

Suppose we have a system of $$N$$ distinguishable, non-interacting particles that each have two energy levels available to them. The ground state energy is $$\epsilon_0 = 0$$ and the excited state energy is $$\epsilon_1 = \epsilon$$. Let's calculate the expected value of the energy $$\langle E\rangle$$, the heat capacity $$C_V$$, the entropy, and the free energy per particle.

The $$N$$-particle partition function is simply the product of the single particle partition function. If the particles had been indistinguishable, we'd have to account for that by dividing by $$N!$$, i.e.,

$$Z^{\text{indistinguishable}}_N = \frac{Z_1^N}{N!}$$

Regardless, the single-particle partition function is just the sum of the Boltzmann factors of each energy level:

$$Z_1 = \sum_{i=0}^{1} e^{-\beta \epsilon_i}$$

$$Z_1 = 1+e^{-\beta\epsilon}$$

So the $$N$$-particle partition function is

$$Z_N = \left(1+e^{-\beta \epsilon}\right)^N.$$

We can find the internal energy by taking derivatives of the partition function:

$$\langle E\rangle = -\frac{\partial \ln Z_N}{\partial \beta}$$

Without going through the algebra,

$$\langle E\rangle = \frac{N\epsilon e^{-\beta\epsilon}}{1+e^{-\beta\epsilon}}$$

We can then use the thermodynamic definition of heat capacity, $$C_V = \frac{\partial U}{\partial T}\bigg)_V $$ to calculate

$$C_V = \frac{N\epsilon^2}{kT^2}\frac{e^{-\beta\epsilon}}{(1+e^{-\beta\epsilon})^2}$$

In class, we had a discussion about the low and high temperature limits of this equation. I would encourage you to think carefully about the limiting process: just because a term in the numerator goes to zero, that does not mean the expression goes to zero! Until you become comfortable with **the rates at which functions go to zero**, use L'Hopital's Rule. [Check out this example](limits.md)
