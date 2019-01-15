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
