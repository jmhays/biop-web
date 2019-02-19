---
  layout: post
  title: Extra Material for Problem Set 2
---

I do *not* expect you to understand the material presented here. I wanted to post this so that those of you who are confused about the sign convention in Problem Set 2 Problem 1 can be satisfied and happy.

The sneaky thing in Problem 1 is that we are *changing ensembles*. We're working in an isothermal-isobaric (well, really, iso-tension...?) ensemble. The parition function we derived in class is useful for $$N,V,T$$ ensembles! But we need something for an $$N,P,T$$ ensemble.

You see, we assumed that no external work was being done on the system. However, we have *another constraint* in our Lagrangian now, which is that the tension must be constant: $$\langle f\rangle = F$$. You *could* work through another nasty Lagrange multiplier problem (try it if you feel ambitious!) and you could find the correct partition function that way.

But there's a neat-o trick for switching ensembles super-fast. It's called a Legendre Transformation.


## Legendre Transformations

How does a Legendre transform work? The key idea is to use the product rule. If $$(J,x)$$ is a conjugate pair of variables, then $$d(Jx) = xdJ + Jdx$$ relates the variation $$dJ$$ in quantity $$J$$ to the variation $$dx$$ in quantity $$x$$.

Let's go through the details. Consider a function of two independent variables, call it $$f(x,y)$$. It's differential is

$$df = \frac{\partial f}{\partial x}\bigg)_y dx + \frac{\partial f}{\partial y}\bigg)_x dy$$

Let's define $$u\equiv\frac{\partial f}{\partial x}\bigg)_y$$ and $$w\equiv\frac{\partial f}{\partial y}\bigg)_x$$. I'm *only doing this to keep the ugly math symbols to a minimum*. You can write everything out with partials if you wish!

Our equation can now be rewritten as

$$df = udx + wdy$$

Much cleaner.

Now here's the clever part: use the product rule to compute the differential

$$d(wy) = ydw + wdy$$

and subtract this equation from $$df$$ to get

$$df - d(wy) = udx + wdy - ydw - wdy$$

$$ = udx - ydw$$

Call this cool new function the Legendre transformation $$g$$:

$$dg = udx - ydw$$.

To summarize, we have done a Legendre transformation from an original function $$f(x,y)$$ to a new function $$g(x,w)$$ by switching from variable $$y$$ to its conjugate variable $$w$$. Of course, one could instead switch $$x$$ to $$u$$ to obtain $$h(u,y)$$ or one could switch both independent variables to
get $$k(u,w)$$. We see therefore that for two variables, there are four possible variants on the function. To make the connection back to thermodynamics, we might call these various functions the potentials. :grin:

---

**Example: Gibbs Free Energy as a Legendre transformation of Helmholtz Free Energy**

Recall the [differential of Helmholtz Free Energy](../lectures/Lecture6.md):

$$dF = Jdx - S dT + \mu dN$$

This differential is extremized when $$(N, x, T)$$ are constant. What if we want to find a new differential that is extremized when $$(N, J, T)$$ are constant? We need to do a Legendre transformation of $$J, x$$.

So take $$d(Jx)$$ and subtract from the Helmholtz:

$$dF - d(Jx) = Jdx - SdT + \mu dN - Jdx - xdJ$$
$$ = -SdT + \mu dN - x dJ$$

Hey, that's the differential of the Gibbs Free Energy! I.e., $$dG = dF - d(Jx)$$.

---

In your homework, you need to work in the Gibbs ensemble - you need a new partition function. Let's start with the "$$F=ma$$" of statistical mechanics:

$$F = -k_B T \ln Z(N,x,T)\Rightarrow Z(N,x,T) = e^{-\beta F}$$

Now the Legendre transformation! Multiply both sides by $$e^{\beta(Jx)}$$:

$$Z(N,x,T)e^{\beta Jx} = e^{-\beta(F + JX)} = e^{-\beta G}$$

So the new partition function for Homework Problem 1 is:

$$Z(N,J,T) = Z(N,x,T)e^{\beta Jx}$$
