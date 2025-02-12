---
  layout: post
  title: Problem Set 2
  author: Due at the beginning of class on 2/21/2019
---

Total point value: 100 pts. If I did my algebra correctly :grin:

## Problem 1 (45 pts)
A single, long, straight, chain molecule is made up of $$N$$ non-interacting microscopic segments. The energy $$E_i$$ and length $$\ell_i$$ of each segment $$i = 1, 2, 3, ... , N$$ are determined by that segment's internal state $$\nu_i$$. Three internal states are possible (representing, for example, the torsional isomers of the polymer backbone): State 1 has an energy of $$\epsilon_i=0$$ and a length of $$\ell_i = \ell$$. States 2 and 3 are degenerate, with energies of $$\epsilon_i = \epsilon$$ and lengths of $$\ell_i = \ell - \delta$$. The quantities $$\epsilon, \ell$$, and $$\delta$$ are all positive constants. The molecule is held under tension $$f$$, i.e., the work required to change the total length $$L$$ by an infinitesimal amount $$dL$$ is $$fdL$$. (Note: The segments remain bound to one another, implying some kind of interaction, however, we consider them as non-interacting because the energy of the inter-segment bond does not vary with $$\nu_i$$, and is therefore not part of our calculation.)

a. (15 pts) Calculate the intramolecular partition function $$Z(\beta, \beta f, N )$$ for this model polymer in an ensemble characterized by $$\beta, \beta f,$$ and $$N$$. (Note: The total energy $$E$$ and the total length, $$L$$, are allowed to fluctuate, but the number of segments, $$N$$, is kept fixed.) Write your answer as an explicit function of $$\beta, f, N,$$ and model parameters ,$$\epsilon, \ell$$ and $$\delta$$.

Hint: Check out a [new resource](extra.md) I've added

b. (15 pts) Compute the average total length L in this ensemble by differentiating $$Z(\beta, \beta f, N )$$ appropriately. Is your result an increasing or decreasing function of temperature? Give a physical interpretation of your answer.

c. (15 pts) Compute the root mean square fluctuation in length, $$\sqrt{(L-L_0)^2}$$ by further differentiation of $$Z(\beta, \beta f, N )$$. How does this quantity compare in magnitude with $$L$$ and why is your result expected or unexpected?

## Problem 2 (30 pts)

Consider a box of total volume V that is divided by a sliding partition into two chambers of volumes $$V_1$$ and $$V_2$$. The chambers contain $$N_1$$ and $$N_2$$ particles, respectively, of an ideal gas. The walls of the box are held at fixed temperature $$T$$. We wish to determine the equilibrium position of the partition.

(a) (10 pts) Write out an expression for the total free energy of the sytem by summing
the free energies of each partition. Which free energy did you choose and why?

(b) (10 pts) Using $$V_2 = V − V_1$$, set $$\frac{\text{my favorite free energy}}{\partial V_1}\bigg)_{\text{my favorite macrostate}}= 0$$ and solve for the equilibrium ratio $$\frac{V_1}{V_2}$$.

(c) (5 pts) Verify that your solution also corresponds to a maximum of the entropy $$S$$.

(d) (5 pts) Verify that your solution for b. corresponds to equal pressures in each chamber.

## Problem 3 (25 pts)

We showed in class that the probability for a system to have energy $$\epsilon_i$$ is proportional to $$e^{−\beta \epsilon_i}$$. You also showed in the last problem set that the average energy of a system can be expressed in terms of the partition function $$Z = \sum_i e^{-\beta\epsilon_i}$$:

$$U = \langle E\rangle = -\frac{\partial}{\partial\beta}\ln Z$$

Now you will related this result to thermodynamics.

(a) (15 pts) Using only thermodynamics, show that

$$U = \frac{\partial (F/T)}{\partial (1/T)}\bigg)_{N,V}$$

for Helmholtz free energy $$F$$. **BEWARE: YOU MAY NOT ASSUME THIS IS AN IDEAL GAS**

(b) (10 pts) Show that these results are consistent if we identify $$\beta = \frac{1}{k_B T}$$ and $$F = −k_B T \ln Z$$ for arbitrary constant $$k_B$$.
