---
layout: post
title: Mathematical methods in statistical mechanics
---


### Probability

#### Definitions and axioms
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

#### Counting events
**Permutations** are ordered arrangements of members of a set.

---

**Example: How many ways are there to arrange the last three letters of the alphabet?**


We need to calculate the number of different sequences we can make using the letters x, y, z.

We can choose one of three letters for the first element of the sequence. Once we choose one of the three, we've used up one letter. Now there are only two ways to choose the second element of the sequence. Finally, once we've used up two letters, there's only a single letter left to put in the last "spot" of the sequence. So there are $$ 3 \times 2 \times 1 = 3! $$ ways to arrange the last three letters.

---

In general, there are $$ N! $$ ways to arrange $$N$$ distinguishable elments in a sequence.

**Combinations** are unique compositions of members of a set. Here, order does not matter.

---

**Example: How many different ways are there to arrange the letters that spell the word "cheese"?**

If the *e*'s were distinguishable from one another, then we would have $$N! = 6!$$ ways of arranging the letters. However, this means that we count $$che_1e_2se_3$$ as different from $$che_2e_1se_3$$. That's no good! We need to correct for the over-counting by dividing by the number of ways to arrange just the *e*'s.

$$\Omega = \frac{6!}{3!}$$

---

In general, if you have $$N$$ objects that belong to one of $$t$$ categories and there are $$n_i$$ objects in each category, the number of unique compositions of the set is given by

$$ \Omega = \frac{N!}{n_1!n_2!\cdots n_t!}$$

---

**Example: Bose Einstein statistics. How many ways can *n* indistinguishable particles be arrange into *M* boxes?**

Enumerating all the possibilities is just too hard! Luckily, we can do something a little tricky.

- Lay out the $$n$$ particles in a row.
- Divide up the $$n$$ particles with $$M-1$$ partitions. This is effectively the same thing as putting the particles into $$M$$ boxes (draw it!)

Now we just have two sets of objects: particles and partitions.

$$\Omega = \frac{(n + M - 1)!}{n!(M-1)!}$$

---

#### Important Probability Distributions
First, how do we define expectation values?

$$\langle x \rangle = \int xp(x)dx$$

$$\sigma^2 = \langle x^2 \rangle - \langle x \rangle^2 = \int x^2p(x)dx - \left(\int xp(x)dx\right)^2$$

These integrations can get very complex. If you're interested in clever ways to find mean, variance, and higher moments, check out [this](https://en.wikipedia.org/wiki/Characteristic_function_(probability_theory)).

##### Gaussian
Gaussian/normal distribution:

$$p(x) = \frac{1}{2\pi\sigma^2}\exp\left[-\frac{(x - \lambda)^2}{2\sigma^2}\right]$$

We'll see a lot more of this distribution because

- momentum goes as $$p^2$$ in energy

- probability goes as the exponential of energy in statistical mechanics: $$\text{prob}(E) \sim \exp\left[p^2\right]$$

##### Binomial

Discrete random variable with two outcomes $$H$$ and $$T$$. The probability of obtaining exactly $$N_H$$ occurences of $$H$$ is given by:

$$p(N_H) = {N\choose N_H}p_H^{N_H}(1-p_H)^{N-N_H}$$

##### Poisson

The probability of achieving $$k$$ successes in time $$t$$ is given by

$$P(k, t) = \frac{e^{-\alpha t}(\alpha t)^k}{k!}$$

$$\alpha$$ is the rate of success per unit time. This is a limiting case of the binomial distribution where

- the number of trials $$N$$ is much larger than the number of successes $$k$$.
- and $$Np \rightarrow \alpha t $$

The easiest thing to do is to consider an example. Let's consider radioactive decay. This is a process in which $$N >> k$$. We ask "what is the probability of observing exactly $$k$$ decays in time $$t$$?"

- Split up your time interval $$t$$ into $$N$$ very small segments of size $$dt$$.
- Make them *so* small that only one event occurs in the interval $$dt$$. Assume that the probability of success is proportional to the interval $$dt$$, i.e., $$p = \alpha dt$$
- Then we can treat this as a binomial! Ultimately, you end up using the characteristic function of the binomial in the $$\lim_{dt\rightarrow 0}$$ and what pops out is the Poisson distribution.

So much is being left out here! For more details, check out [this](https://www.le.ac.uk/users/dsgp1/COURSES/LEISTATS/poisson.pdf) document.

#### Practice on your own
1. What is the probability of obtaining a royal flush in poker?
2. What is the probability of rolling a 1 on the first roll *or* a 4 on the second roll? Hint: use $$1-p_{fail}$$
3. The [Khan Academy](https://www.khanacademy.org/math/precalculus/prob-comb) may be of interest.
