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

#### Partial Derivatives
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

Now do something very, very dangerous. Erase all the $dt$'s.

$$df = \frac{\partial f}{\partial x}\bigg)_y dx + \frac{\partial f}{\partial y}\bigg)_x dy$$

This is a "differential." It tells us how small perturbations to $$x$$ and $$y$$ produce perturbations in $$f$$.

**Definition: a differential $$df$$ is exact if $$\int df$$ is path independent**

We're going to see how powerful that is when we study thermodynamic state functions.


#### Extrema
#### Extrema: subject to constraints
#### Lagrange multipliers
