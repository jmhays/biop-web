---
layout: post
title: Entropy
---

### Review of previous lecture: practice on your own

---

1. **Exact differentials.** Is the following expression an "equation of state" (path independent)?

    $$ \left(P(V,T) + \frac{a}{V}\right)\left(V - b\right) = RT $$

    Bonus: what kind of system does this equation describe?

    You know how to do this. Check $$\frac{\partial ^2 P(V,T)}{\partial V\partial T} = \frac{\partial ^2 P(V,T)}{\partial T\partial V}$$

    $$\frac{\partial ^2 P(V,T)}{\partial T\partial V} = \frac{\partial ^2 P(V,T)}{\partial V\partial T} = -\frac{R}{(V-b)^2}$$

    This is an equation of state! $$dP$$ is an exact differential. This equation describes a [Van der Waals gas](https://www.youtube.com/watch?v=y8W5aAsBXSQ&vl=en).

2. **Lagrange multipliers. Challenging!** Find the distribution $$p(x)$$ such that
    - The quantity $$S = -\int p(x) \ln p(x)dx$$ is at a maximum.
    - The mean of $$p(x)$$ is given by $$\langle x \rangle = \mu$$
    - The variance of $$p(x)$$ is given by $$\langle x^2\rangle - \left(\langle x \rangle\right)^2 = \sigma^2$$

    The Lagrangian is for this system is

    $$\mathcal{L} = -\int p(x) \ln p(x)dx - \lambda \left(\int x p(x)dx - \mu\right)- \beta \left(\int x^2 p(x)dx - \mu^2 - \sigma^2\right) - \gamma \left(\int p(x)dx - 1\right)$$

    Now solve the system of equations $$\frac{\partial \mathcal{L}}{\partial p} = 0$$:

    $$-\frac{\partial }{\partial p}\int dx \left[p(x) \ln p(x)- \lambda x p(x) - \beta x^2 p(x) - \gamma p(x)\right] = 0$$

    $$\int dx \left[\ln p(x) + 1 - \lambda x - \beta x^2 - \gamma\right] = 0$$

    One obvious way to get this to work is to have

    $$\ln p(x) + 1 - \lambda x - \beta x^2 - \gamma = 0$$

    Solving for $$p(x)$$ gives

    $$ p(x) = e^{-(1+\gamma) - \lambda x - \beta x^2}$$

    We can then plug this equation into our various constraints:

    $$\langle x \rangle = \mu\Rightarrow \int x e^{-(1+\gamma) - \lambda x - \beta x^2}dx = \mu$$

    $$\langle x^2 \rangle -\mu^2 = \sigma^2\Rightarrow \int x^2 e^{-(1+\gamma) - \lambda x - \beta x^2}dx - \mu^2 = \sigma^2$$

    $$\int e^{-(1+\gamma) - \lambda x - \beta x^2}dx = 1$$

    And after tons of grunt work, we get a normal distribution!

    $$p(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left[-\frac{(x-\mu)^2}{2\sigma^2}\right]$$

    This means that the normal distribution is the "maximum entropy" distribution for known mean and variance. But what the actual hell does that even mean? Check out [this little post](http://bjlkeng.github.io/posts/maximum-entropy-distributions/) for more information
---

### Multiplicity

Let's go back to flipping a coin

---

Suppose we flip a coin 4 times. Assuming that this is a fair coin, what is the most likely

1. Sequence of H's and T's?

2. Composition of H's and T's?

Because we have a fair coin with independent trials, all the different sequences (there are $$\Omega = 4!$$ of them) are equally probable. So there's no preferred sequence.

However, there *is* a preferred *composition*. To see this, let's write down the *multiplicities* of each possible composition.

$$\Omega_{H=0} = 1 ~~~~ \Omega_{H=1} = {4\choose 1} = 4 ~~~~ \Omega_{H=2} = {4\choose 2} = 6 $$

$$\Omega_{H = 3} = {4 \choose 3} = 4 ~~~~ \Omega_{H = 4} = 1$$$

The combination $$\{H, H, T, T\}$$ is most probable because there are more ways to produce it than any other combination.

---
