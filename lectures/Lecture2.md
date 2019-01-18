---
layout: post
title: Mathematical methods in statistical mechanics
---

### Review of previous lecture: practice on your own

---

**1. What is the probability of obtaining a royal flush in poker?**

$$p(\text{royal flush}) = \frac{\Omega(E)}{\Omega(S)} = \frac{\text{# of ways to obtain royal flush}}{\text{# of ways to obtain any hand}}$$

$$\Omega(S) = {52\choose 5} = \frac{52!}{5!47!}$$

The number of ways to get a royal flush in *one* suit is just 1. Thus, the numerator is 4 because there are four suits in the deck.

**2. What is the probability of rolling a 1 on the first roll *or* a 4 on the second roll? Hint: use $$1-p_{fail}$$**

$$p_{fail} = p(\text{not rolling 1 on first AND not rolling 4 on second})$$


$$= 1 - p(\{2,3,4,5,6\})\times p(\{1,2,3,5,6\})$$

Assuming a fair die, we have $$p_{fail} = 5/6 \times 5/6 = 25/36.$$

---

### Multivariable calculus

#### Extrema
We need to know how to evaluate changes in functions of multiple variables: how temperature, pressure, and volume change with respect to one another; how metabolites affect the permeability, volume, and particle number within a cell; etc.

For functions of a single variable, we already know how to find extrema. If you have a function $$f(x) = (x-a)^2$$, you can find the extremum by setting the derivative to zero:

$$\frac{df}{dx} = 2(x-a) = 0 \Rightarrow x^* = a$$

(Draw this, see if it makes sense!)

For multiple variables, we just have more conditions. *All* the partials must be set to zero. If we want to find the extremum of $$f(x,y) = (x - x_0)^2 + (y - y_0)^2$$, we have to find all the partials:

$$\frac{\partial f}{\partial x}\bigg)_y = 2(x-x_0)$$

$$\frac{\partial f}{\partial y}\bigg)_x = 2(y-y_0)$$

and set them equal to zero. We find that the minimum is $$(x_0, y_0)$$. This is shown graphically below.

Let's do a more challenging example.

---

**Example: Take all the first and second partials of the ideal gas**

The equation of state (we'll define this carefully in a later lecture) for a gas of $$N$$ non-interacting particles is given by:

$$p(V, T) = \frac{N k_B T}{V}$$

We'll be more rigorous in our definitions of equation of state in the upcoming lectures but, for now, it's just an equation that defines the pressure of a gas as a funtion of $T$ and $V$

$$\left(\frac{\partial p}{\partial V}\right)\biggr\rvert_{T} = -\frac{Nk_B T}{V^2}$$

$$\left(\frac{\partial p}{\partial T}\right)\biggr\rvert_{V} = \frac{Nk_B}{V}$$

I won't go through all the second partials. Let's just look at two:

$$ \frac{\partial}{\partial V}\biggr\rvert_{T}\frac{\partial}{\partial T}\biggr\rvert_{V} p(V, T)= \frac{\partial}{\partial V}\biggr\rvert_{T}\frac{N k_B}{V} = - \frac{Nk_B}{V^2}$$

$$ \frac{\partial}{\partial T}\biggr\rvert_{V}\frac{\partial}{\partial V}\biggr\rvert_{T} p(V, T)= \frac{\partial}{\partial T}\biggr\rvert_{V}-\frac{N k_B T}{V^2} = - \frac{Nk_B}{V^2}$$


---

Notice that the two second partials are the same. We'll see the implications of this in a moment. First, we need to define something called a "differential".

#### Exact and inexact differentials

Let's recall the chain rule. If I have a function $$f(x)$$ where $$x(t)$$, then

$$\frac{df}{dt} = \frac{df}{dx}\frac{dx}{dt}.$$

This is trivially (heh) extended to multiple variables

$$\frac{df(x,y)}{dt} = \frac{\partial f}{\partial x}\bigg)_y\frac{dx}{dt} + \frac{\partial f}{\partial y}\bigg)_x\frac{dy}{dt}.$$

Now do something very, very dangerous. Erase all the $$dt$$'s.

$$df = \frac{\partial f}{\partial x}\bigg)_y dx + \frac{\partial f}{\partial y}\bigg)_x dy$$

This is a "differential." It tells us how small perturbations to $$x$$ and $$y$$ produce perturbations in $$f$$.

**Definition: a differential $$df$$ is exact if $$\int df$$ is path independent**

In order to determine exactness, check that the mixed partials are equal:

$$\frac{\partial^2f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x}$$

We're going to see how powerful that is when we study thermodynamic state functions. Looking back to our ideal gas example, we can already see that $$d p$$ is an exact differential, meaning that $$\int dp$$ is independent of the path taken. We can take all kinds of strange paths to get from one pressure to another, but it doesn't matter, $$\int dp$$ only depends on the start and end points.

#### Extrema: subject to constraints

Let's go back to the parabaloid $$f(x,y) = x^2 + y^2$$. When $$x$$ and $$y$$ are unconstrained, we find a minimum at $$(x^*, y^*) = (0,0)$$. But suppose we require that our answer lie on a plane defined by $$x + y = 6$$.

There are three options at this point for doing our optimization:

1) Plug in $$y = 6 - x$$ or $$x = 6-y$$ into the equation for $$f(x,y)$$ and turn everything into a single variable problem.

2) Take the differentials of $$f(x,y)$$ and $$g(x,y) = x + y - 6$$ and set them equal to zero.

3) Use Lagrange multipliers.

In this case, the easiest thing to do *may* be the first option. However, as we get to more complicated systems, we'll need option 3.

#### Lagrange multipliers
Define a new function $$\mathcal{L} = f - \lambda g$$. This function is called a "Lagrangian," and $$\lambda$$ is a Lagrange multiplier. $$g$$ is our constraint equation ($$x + y - 6$$ in the last example).

It's not a trivial thing to understand it intuitively (I would encourage those of you who are comfortable with the rest of the material to give it a shot).

- If you want a graphical interpretation, consult the [Khan Academy](https://www.khanacademy.org/math/multivariable-calculus/applications-of-multivariable-derivatives#lagrange-multipliers-and-constrained-optimization).
- If you want a really classic but also somewhat weird interactive explanation consult [Wolfram](http://demonstrations.wolfram.com/LagrangesMilkmaidProblem/)
- We can talk about the milkmaid problem in class if people are into it (that's essentially the Wolfram demo).

Otherwise, just trust me when I say this function is useful. The critically important point here is that **minimizing the Lagrangian accomplishes the constrained optimization problem.**

Let's make use of total differentials.

$$d\mathcal{L}(x_1, x_2, \ldots, x_n) = \frac{\partial f}{\partial x_1} dx_1 + \frac{\partial f}{\partial x_2} dx_2 + \cdots + \frac{\partial f}{\partial x_n} dx_n + \lambda\left(\frac{\partial g}{\partial x_1} dx_1 + \cdots + \frac{\partial g}{\partial x_n} dx_n\right)$$

All that mess on the right hand side needs to be zero in order for the point to be a minimum. The whole expression reduces to a system of equations in which the $$dx_i$$'s are treated independently. Why are they independent? Click [here](#lagrangian-deets) to get a more advanced description.

$$\matrix{\frac{\partial f}{\partial x_1} dx_1 - \lambda \frac{\partial g}{\partial x_1} dx_1 = 0 \\ \frac{\partial f}{\partial x_2} dx_2 - \lambda \frac{\partial g}{\partial x_2} dx_2 = 0 \\ \vdots \\ \frac{\partial f}{\partial x_n} dx_n - \lambda \frac{\partial g}{\partial x_n} dx_n = 0}$$

---

**Example: $$f(x, y) = x^2 + y^2$$ subject to the constraint $$x +y = 6$$. ***

$$\mathcal{L} = x^2 + y^2 - \lambda(x + y - 6)$$

Take the differential:

$$d\mathcal{L} = 2x dx + 2ydy - \lambda (dx + dy)$$

Gather up the $$dx$$ terms and set to zero. Do the same for $$dy$$ terms.

$$2x dx - \lambda dx = 0$$
$$2y dy- \lambda dy = 0$$

Solving for $$x$$, then $$y$$

$$ 2y = 2x = -\lambda$$

Right now, we don't care about $$\lambda$$. We eliminate it and find that $$(x^*,y^*) = (3,3)$$. Soon, we'll care a bit about $$\lambda$$

## Practice on your own

1. **Exact differentials.** Is the following expression an "equation of state" (path independent)?

    $$ \left(P(V,T) + \frac{a}{V}\right)\left(V - b\right) = RT $$

    Bonus: what kind of system does this equation describe?

2. **Lagrange multipliers. Challenging!** Find the distribution $$p(x)$$ such that
    - The quantity $$S = -p(x) \ln p(x)$$ is at a maximum.
    - The mean of $$p(x)$$ is given by $$\langle x \rangle = \mu$$
    - The variance of $$p(x)$$ is given by $$\langle x^2\rangle - \left(\langle x \rangle\right)^2 = \sigma^2$$

    If you get stumped, just *set up* the problem and don't solve it all the way.

    Hint: the correct distribution should be SUPER familiar! :grin:

---

## Lagrangian deets.

What we're ACTUALLY doing in a lagrange multiplier problem is solving THIS:

$$\vec{\nabla} \mathcal{L} = 0$$

We take the divergence here because the geometric interpretation of constrained optimization shows that, at the minimum, $$\nabla f$$ and $$\nabla g$$ are the same (to within some multiplicative factor $$\lambda$$).

$$ \vec{\nabla} f = \lambda \vec{\nabla}g $$

$$\begin{pmatrix}\frac{\partial f}{\partial x_1} \\ \frac{\partial f}{\partial x_2} \\ \vdots \\ \frac{\partial f}{\partial x_n}\end{pmatrix} = \lambda \begin{pmatrix} \frac{\partial g}{\partial x_1} \\ \frac{\partial g}{\partial x_2} \\ \vdots \\ \frac{\partial g}{\partial x_n} \end{pmatrix}$$

I think. :grimacing:
