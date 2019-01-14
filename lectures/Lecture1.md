---
layout: post
title: Mathematical methods in statistical mechanics
---


### Probability: Chapter 1

#### Definitions, axioms, correlated events
- A **random variable** $$x$$ is a variable which has a set of possible outcomes $$S=\{x_1, x_2, ..., x_n\}$$. These can be
    - discrete, like rolling a die $$S=\{1,2,3,4,5,6\})$$, or
    - continuous, like the velocity of a particle $$S=\{-\infty \leq v_x, v_y, v_z \leq \infty\}$$
- An **event** is any subset of outcomes $$E\subset S$$.
    - has a probability $$p(E)$$ associated with it.
    - e.g., what is the probability of rolling either a 1 or a 3 if I have a fair die? $$p(\{1,3\}) = 1/3$$.
- Define a set of axioms for this function $$p(E)$$
    - positivity: $$p(E) \geq 0$$
    - additivity: $$p(A \text{ or } B) = p(A) + p(B)$$
    - normalization: $$p(S) = 1$$
        - For discrete: $$\sum p(X) = 1$$
        - For continuous: $$\int p(x) dx = 1$$
- Objective vs subjective probabilities
    - **objective probability**: obtained experimentally from relative frequencies.
    - **subjective probability**: obtained from a theoretical estimate.
    - subjective probabilities will be critical in our studies of statistical mechanics.
- Correlated events
    -

#### Important Probability Distributions
First, how do we define expectation values?

$$\langle x \rangle = \int xp(x)dx$$

$$\sigma^2 = \langle x^2 \rangle - \langle x \rangle^2 = \int x^2p(x)dx - \left(\int xp(x)dx\right)^2$$
1. Gaussian
2.
$$p(x) = \frac{1}{2\pi\sigma^2}\exp\left[-\frac{(x \lambda)^2}{2\sigma^2}\right]$$

2. Binomial

Discrete random variable with two outcomes $$H$$ and $$T$$. The probability of obtaining exactly $$N_H$$ occurences of $$H$$ is given by:

$$p(N_H) = {N\choose N_H}p_H^{N_H}(1-p_H)^{N-N_H}$$

3. Poisson

#### Practice on your own
