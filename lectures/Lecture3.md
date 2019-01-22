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

$$\Omega_{H = 3} = {4 \choose 3} = 4 ~~~~ \Omega_{H = 4} = 1$$

The combination $$\{H, H, T, T\}$$ is most probable because there are more ways to produce it than any other combination.

---

The same principle is at work for systems of particles. There are many different microscopic states (analagous to the coin flip *sequences*) that can produce the same macrostate (analagous to the coin flip *compositions*). Let's be more precise in our terminology.

### Microstates and macrostates

Consider a system of $$N$$ particles in an insulated container (constant energy $$E$$) of volume $$V$$. Define a microstate $$\mu$$ to be the $$6N$$-dimensional vector that competely specifies the state of the system:

$$\mu=\begin{pmatrix} x_1, y_1, z_1, \ldots, x_N, y_N, z_N, p_{x_1}, p_{y_1}, p_{z_1}, \ldots p_{x_N}, p_{y_N}, p_{z_3} \end{pmatrix}$$

The macrostate $$M$$ of this system is defined by the macroscopic quantities that I observe, in this case, $$M=(N,V,E)$$ (we can derive all other thermodynamic quantities from these, for what it's worth). Now, what happens if we look at a different microstate $$\mu'$$, where we've flipped the sign on all the velocities

$$\mu'=\begin{pmatrix} x_1, y_1, z_1, \ldots, x_N, y_N, z_N, -p_{x_1}, -p_{y_1}, -p_{z_1}, \ldots -p_{x_N}, -p_{y_N}, -p_{z_N} \end{pmatrix}$$

Say the microstate $$\mu$$ belongs to our $$N,V,E$$ ensemble. Does $$\mu'\$$ belong as well? Yes! The energy, which is the only thing that could possibly be affected here, isn't changed by reversing the momenta since $$E\sim p^2$$. The point here is that **there are many $$\mu$$'s to a single $$M$$**.

Thinking back to our coin flipping problem, we can draw an analogy between the microstates and the sequences of flips and then between the macrostates and the combinations.

If you are studying a system in equilibrium, the thermodynamic variables you observe in the lab are the variables of the macrostate. Now, here's the really critical point: _**the macrostate you observe is composed of the set of most probable microstates.**_

But what does that have to do with entropy?

### Entropy

Let's consider a system not in equilibrium and figure out what equilibrium it reaches by maximizing multiplicities.

Suppose we have two systems, $$A_1$$ and $$A_2$$ that are independently in equilibrium and defined by the macrostates $$M_1 = (N_1, V_1, E_1)$$ and $$M_2 = (N_2, V_2, E_2)$$, respectively. We bring the two systems into thermal contact and allow energy to be exchanged. Neither particles nor volume are permitted to exchange. When the systems are brought into contact, the total energy is given by

$$E = E_1 + E_2$$

**Goal: find a condition on $$E$$ that describes the new equilibrium**

Another way of approaching this is to say "what amount of energy gets transferred between the two containers? What is the change in $$E_1$$?"

We can find equilibrium by *maximizing the multiplicity (number of microstates) of the final system*. Let's write down the multiplicity and then take the appropriate partials:

$$\Omega = \Omega_1(E_1)\Omega_2(E_2)$$

$$\frac{\partial\Omega}{\partial E_1} = \frac{\partial \Omega_1(E_1)}{\partial E_1}\Omega_2(E_2) + \Omega_1(E_1)\frac{\partial \Omega_2(E_2)}{\partial E_1}$$

Notice that we can rewrite $$\frac{\partial \Omega_2(E_2)}{\partial E_1} = \frac{\partial \Omega_2(E_2)}{\partial E_2}\frac{\partial E_2}{\partial E_1} = -\frac{\partial \Omega_2(E_2)}{\partial E_2}$$.

Substituting this into the above expression:

$$\frac{\partial\Omega}{\partial E_1} = \frac{\partial \Omega_1(E_1)}{\partial E_1}\Omega_2(E_2) - \Omega_1(E_1)\frac{\partial \Omega_2(E_2)}{\partial E_2}$$.

Setting this expression to zero:

$$\frac{\partial \Omega_1(E_1)}{\partial E_1}\Omega_2(E_2) = \Omega_1(E_1)\frac{\partial \Omega_2(E_2)}{\partial E_2}$$

Divide across by $$\Omega_1\Omega_2$$:

$$\frac{1}{\Omega_2(E_1)}\frac{\partial \Omega_1(E_1)}{\partial E_1} = \frac{1}{\Omega_2(E_2)} \frac{\partial \Omega_2(E_2)}{\partial E_2}$$

$$\frac{\partial \ln\Omega_1(E_1)}{\partial E_1} = \frac{\partial \ln\Omega_2(E_2)}{\partial E_2}$$

Let's define a quantity $$S = k \ln\Omega$$. Then we can write the above expression as

$$\frac{\partial S_1}{\partial E_1} = \frac{\partial S_2}{\partial E_2}$$

That's crazy! We just showed that maximizing *multiplicities* is equivalent to maximizing *entropy!* Assuming, of course, that you accept that this $$S = k\ln\Omega$$ is the same $$S$$ that you see in thermodynamics. Don't worry. We'll get there.

Two final comments:

1. We can unpack *even more* from the expression $$\frac{\partial \ln\Omega_1(E_1)}{\partial E_1} = \frac{\partial \ln\Omega_2(E_2)}{\partial E_2}$$. Because $$\Omega_1$$ and $$\Omega_2$$ are freely varying (independent) quantities, the only way for their partials to be equal is if the derivatives are constant. In other words:

$$\frac{\partial \ln\Omega_1(E_1)}{\partial E_1} = \frac{\partial \ln\Omega_2(E_2)}{\partial E_2} = \beta$$

  where $$\beta$$ is some constant. In fact, $$\beta$$ is going to turn out to be exactly $$1/k_B T$$. It shouldn't be surprising that the constant is some function of temperature. After all, we specified that the systems were coming into **thermal contact**: shouldn't the temperature be constant at thermal equilibrium?

2. Entropy can also be written in terms of probabilities. Again, not surprising because we just showed that multiplicities and probabilities are closely connected.

$$\frac{S}{k} = -\int_{\mu\in\Omega} p(\mu)\ln p(\mu) d\mu$$

  We're going to work some examples using the above expression in the next class.
