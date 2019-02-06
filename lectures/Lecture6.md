---
  layout: post
  title: Thermodynamic potentials
---

We've been working with systems that have either been isolated from the surroundings or have tightly controlled heat exchange with the surroundings.

Said another way, we've been *told* exactly what the heat exchange is for each of the systems we've studied.

Real life doesn't work that way: often we wish to study systems where we have constant temperature or pressure or volume rather than constant (or well-described) energy.

### Internal Energy
Let's start by summarizing what we know about internal energy. We found that three things can contribute to internal energy: mechanical work, heat, and addition of particles:

$$dU = đW + đQ + \mu dN$$

This is called the "fundamental equation of thermodynamics." For reversible processes, we found in [Lecture 5](Lecture5.md) that $$đW$$ and $$đQ$$ can be rewritten so that

$$dU = TdS + Jdx + \mu dN.$$

#### Natural variables
We say that $$S,x, N$$ are the **natural variables** of $$U$$. Why are $$S, x, N$$ so important that they get their own name? Because all the other thermodynamic quanitites can be expressed as partial derivatives of $$U$$ with respect to the natural variables!!

$$T = \frac{\partial U}{\partial S}\bigg)_{N,x}$$
$$J = \frac{\partial U}{\partial x}\bigg)_{N,S}$$
$$\mu = \frac{\partial U}{\partial N}\bigg)_{x,S}$$

Internal energy is minimized when it's **natural variables are held constant**

But you might be working with a system where the variables $$S, x, N$$ are not at all natural. Instead, you might be working with a system where $$T,x,N$$ are constant. In that case, internal energy is not minimized at equilbrium and is therefore not a meaningful thermodynamic potential. What thermodynamic potential *is* minimized under constant $$T,x,N$$?

### Helmholtz Free Energy: constant (N,x,T)

Let's define a function $$F = U - TS$$. Then

$$dF = dU - TdS - SdT $$
$$\Rightarrow dF = Jdx - SdT + \mu dN.$$

The natural variables of Helmholtz Free Energy are $$N, x, T$$ because all other thermodynamic quantities can be found in terms of partials of $$F$$ with respect to the natural variables:

$$ J = \frac{\partial F}{\partial x}\bigg)_{N,T}$$
$$ S = -\frac{\partial F}{\partial T}\bigg)_{N,x}$$
$$ \mu = -\frac{\partial F}{\partial N}\bigg)_{x, T}$$

The Helmholtz Free Energy is minimized when it's natural variables $$N, x, T$$ are held constant.

### Enthalpy (S, N, J)

Let's define a new function $$H = U - Jx$$. Then

$$dH = dU - Jdx - xdJ $$
$$\Rightarrow dH = TdS - xdJ + \mu dN.$$

The natural variables of Enthalpy are $$S, J, N$$ because all other thermodynamic quantities can be found in terms of partials of $$H$$ with respect to the natural variables:

$$ x = \frac{\partial H}{\partial J}\bigg)_{N,S}$$
$$ T = -\frac{\partial H}{\partial S}\bigg)_{N,x}$$
$$ \mu = -\frac{\partial H}{\partial N}\bigg)_{x, S}$$

The Enthalpy is minimized when it's natural variables $$S, N, J$$ are held constant.

### Gibbs Free Energy: constant (N, J, T)

We can do exactly the same thing for a new thermodynamic potential, Gibbs Free Energy.

$$G = U - TS - Jx$$

I'll spare you the algebra and just write the final differential.

$$dG = -S dT - x dJ + \mu dN$$

Again, the natural variables are $$N, J, T$$ and we can write $$S, x, \mu$$ in terms of these variables. Give it a shot!

### Maxwell Relations

We can also write various partial derivatives of thermodynamic quantities in terms of *other* partial derivatives using what we know about exact differentials. Let's consider the mixed partials of the Helmholtz Free Energy:

$$\frac{\partial^2 F}{\partial T\partial x} = \frac{\partial^2 F}{\partial x\partial T}$$

We know from above that $$J = \frac{\partial F}{\partial x}\bigg)_{N,T}$$ and $$S = \frac{\partial F}{\partial T}\bigg)_{N,x}$$. Therefore,

$$\frac{\partial J}{\partial T}\bigg)_{N,x} = \frac{\partial S}{\partial x}\bigg)_{N,T}$$
