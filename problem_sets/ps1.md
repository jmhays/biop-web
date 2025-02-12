---
  layout: post
  title: Problem Set 1
  author: Due at the beginning of class 1/31/19
---

[pdf version][1]

[1]:{{ site.url }}/biop-web/problem_sets/ps1.pdf

1. (10 pts) **Poisson distribution of stars in the galaxy**. Assuming that ~~stars~~ metabolites are randomly distributed in the ~~galaxy~~ cell with a density $$\alpha$$, show that the probability of finding the nearest ~~star~~ metabolite at a distance $$R$$ from the ~~earth~~ nucleus is $$p(R) = 4\pi R^2 \alpha \exp\left({-\frac{4\pi}{3}} R^3 \alpha\right)$$. #biology

2. (40 pts) **Lipid orientation in a nanodisc. Kind of.** :confused: $$N$$ spins are equally spaced around a circle in the *x-y* plane. Each spin can point either parallel or antiparallel to the $$z$$ direction. Niether orientation is preferred. However, the spins interact with each other through a nearest neighbor interaction. If two neighboring spins point in the same direction, they contribute an amount $$−J$$ to the total energy; if they point in opposite directions, they contribute an amount $$J$$. Thus the total energy of the system depends on the number of reversals, $$R$$, that occur around the ring.

$$E = JR − J(N − R) = J(2R − N)$$

a) (2.5 pts) Assume $$N$$ is even. What are the smallest and largest values that $$R$$ can have? What are the minimum and maximum values of $$E$$?

b) (10 pts) Find the total number of microscopic states of the system consistent with a given number of reversals, $$\Omega(R)$$. Note that this corresponds to the number of ways the $$R$$ reversals can be distributed among the *N* inter­spin locations.

c) (15 pts) Assume that $$N$$ is large. Find the entropy $$S$$ of the spin chain as a function of $$N$$ and $$R$$.

d) (10 pts) Find the energy of the spin chain as a function of temperature, $$E(T)$$. Make a sketch of the resulting function for the case $$J > 0$$ and indicate the low and high temperature asymptotes (consider only positive $$T$$).

e) (2.5 pts) What is the mean value of $$R$$ in the high temperature limit?

f) (Bonus: 5 pts) Provide some reasons why this is a terrible approximation to lipids in a nanodisc :grin:

3. (15 pts) **Fluctuations in the canonical ensemble.** An ideal gas is held at constant $$(N, V, T)$$.

a. (5 pts) Write down the partition function $$Z = \int \frac{1}{N! h^{3N}}e^{-\beta E(p,x)}~d^{3N}p~d^{3N}x$$ and compute the integral. Use the relationship $$\beta = \frac{1}{k_B T}$$ to write your answer as a function of $$N, V, T$$.

Hint: the integral over the coordinates is trivial! Think about the constraints imposed on the system. You may use Wolfram Alpha or any other resource of your choice to perform the integrals over momenta.

b. (10 pts) By taking clever partial derivatives of the partition function, compute the variance of the energy $$\left(\Delta E\right)^2= \langle E^2\rangle - \langle E\rangle^2$$. What do you notice about $$\frac{\sqrt{\left(\Delta E\right)^2}}{E}$$?

---

## Relationships you may need

$$ \frac{\partial S}{\partial E}\bigg)_{N,V,T} = \frac{1}{T}$$

Sterling's approximation: for large $$N$$,

$$ \ln N! \approx N\ln N - N$$

Taylor series:

$$e^{x} = 1 + x + \mathcal{O}(x^2) + \cdots $$

If $$x$$ is small, you can neglect high order $$x$$ terms in the expansion above.
