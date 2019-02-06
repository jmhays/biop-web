---
  layout: post
  title: Applications of thermodynamic potentials
---

We discused two example problems using thermodynamic potentials.

---

**Equilibrium temperature of objects in thermal contact.** Suppose that we have to objects which are separately in equilibrium with macrostates defined by $$M_1 = (N_1, V_1, E_1)$$ and $$M_2 = (N_2, V_2, E_2)$$. Then we bring them into thermal contact. What is the final temperature the two systems come to?

Earlier, we had extremized entropy and determined that $$\frac{\partial S_2}{\partial U_2}\bigg)_{N,V,U} = \frac{\partial S_1}{\partial U_1}\bigg)_{N,V,U} = \frac{1}{T}.$$ Now we want to know if we can predict the final temperature $$T$$ using what we know about the subsystems.

We know the total energy of the system is constant:

$$\Delta U = \Delta U_1 + \Delta U_2 = 0$$

But how can we rewrite $$\Delta U_1$$ and $$\Delta U_2$$ in terms of things we can measure?

We could measure the constant volume heat capacities of the two subsystems (before bringing them into contact) using a constant volume calorimeter. We know from earlier lectures that $$C^{(1)}_V = \frac{\partial U_1}{\partial T}\bigg)_V$$. So

$$ \Delta U_1 = \int_{T_1}^T C_V^{(1)}(T) dT, ~~~~ \Delta U_2 = \int_{T_2}^T C^{(2)}_V(T) dT $$

If the heat capacities are independent of temperature, we can write

$$ \Delta U_1 = C_V^{(1)}(T - T_1), ~~~~ \Delta U_2 =  C^{(2)}(T-T_2),$$

so that

$$ T = \frac{C_V^{(1)} T_1 + C_V^{(2)} T_2}{C_V^{(1)} + C_V^{(2)}}$$

---

Ignore literally everything I have to say about enthalpy. I'm letting go of it as something I'll never fully understand.

---

**Collapse of polymer** Let's return to the polymer problem we did in [Lecture 4](Lecture4.md), but analyze it in terms of Helmholtz Free Energy.

Write down the Helmholtz Free Energy of each configuration:

$$F_c = U_c + TS_c = 0$$

$$F_o = U_o + TS_o = \epsilon + k_BT \ln 4$$

In the low temperature limit, the closed conformation becomes more favorable since $$F_c << F_o$$. At low temperatures, system behavior is driven by the internal energy. Conversely, in the high temperature limit, entropy becomes the driving force, and the open states become more populated until all microstates are equally probable.

---

Here we have only qualitatively connected problems in thermodynamics to their statistical counterparts. There is quantitative relationship between Helmholtz Free Energy and the parition function, which we discuss during the last class.

$$F = -k_BT\ln Z$$
