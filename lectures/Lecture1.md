---
layout: post
title: Math methods
---

# Mathematical methods in statistical mechanics

## Expectations for mathematical understanding in this course

-   It is impossible to talk about many-body systems at equilibrium without somewhat advanced mathematics.
-   The point is not for you to be comfortable - we're going to probably go out of most people's comfort zone, but the point is for you to always feel supported by your instructors.
-   My goal is for you to walk out of this class feeling confident enough in your understanding of ensemble theory to be able to stand up in front of people - in a seminar, say - and be able to talk to members of the audience who _are_ experts.
-   We're not going to tackle the really nasty problems in stat mech. But we're going to approach the sort of 'canonical' problems rigorously. Anything short of that is not only _boring_ but it's a disservice to all of you.
-   I would go so far as to argue that the mathematics of statistical mechanics is really beautiful. I hope you'll come to love it as much as I do.

## Entropy & thermodynamics

### Entropy

-   You all are likely aware that statistical mechanics involves entropy.
-   At least you know the word entropy.
-   And you've probably heard that entropy has something to do with disorder. That's not untrue, but it's also not rigorous. A rigorous definition of entropy requires some understanding of probability. So I want to begin with an introduction to probability.

### Thermodynamics

-   You are all likely aware that thermodynamics involves a hot mess of partial derivatives. When I talk about the beauty of statistical mechanics _I am not talking about this_.
-   I'm going to be up front with you. I __HATE__ thermodynamics. The math is messy and tricky and just plain ugly. But we have to do it and, yeah, it's important. So I will follow up my review of probability with a review of multivariable calculus.

## Probability

-   Ok here we go, probability. Let's talk about random variables.

### Random variables

-   a **random variable** $x$ is a variable which has a set of possible outcomes $S={x_1, x_2, ...}$.
    -   These can be discrete, like rolling a die,
    -   or continuous, like the velocity of a particle $S={-\infty \leq v_x, v_y, v_z \leq \infty}$
-   An **event** is any subset of outcomes $E\subset S$ and it has a probability associated with it: $p(E)$.
    -   rolling a die: $p_{die}({1,3}) = 1/3$
-   Axioms
    -   positivity: $p(E)\geq 0$.
    -   additivity: $p(A\text{ or }B) = p(A) + p(B)$
    -   normalization: $p(S) = 1$. Random variable has to have _some_ outcome!
        -   I'm going to highlight this normalization point here because this normalization factor in statistical physics is really lovely and important and you're going to encounter it in beautiful and painful ways in the coming months.
-   Objective vs. Subjective probabilites
    -   _**objective probabilities**_ are obtained experimentally from relative frequencies. So I roll my die 87 times and I count the number of 1's, 2's, 3's and I get a frequency for each face. BAM I have a known set of probabilities.
    -   _**subjective probabilities**_ come from a theoretical estimate. So back when I said rolling a 1 or a 3 had a probability of 1/3, that came from the assumption that I had a fair die. I lacked a precise knowledge of the outcomes, so if I don't have any prior reason to think the die is unfair, I'm gonna give it the benefit of the doubt and say each face is equally likely.

### Please practice on your own.

-   There are probably hundreds of die rolling problems out there. I can't possibly cover all of them. I would ask you to take a look at some just to refresh your memories. Don't become an expert, just spend 10 minutes tonight before bed remembering what the hell is a royal flush anyway. Here are two examples of things you should be able to do:
    1) What's the probability of rolling a 1 on the first roll OR a 4 on the second roll? (hint: use $1-p_{fail}$)
    2) What's the probability of getting a royal flush?

### Correlated events

-   Let's imagine you have a barrel full of red and green balls.
-   Now, if you draw with replacement, each draw is independent of the previous. If you want to know the probability of drawing three red balls you can just multiply the individual probability of drawing one red ball three times - i.e.,
    $$p(\text{three red draws}) = p_{red}^3$$
-   But now, if you draw _without_ replacement, the probability of getting red on the second draw is going to depend on what color you pulled on the first draw!
-   Conditional probabilities are expressed in the following way:
    -   $p(B|A)$: probability of event $B$ occuring, given that some other event $A$ has occured.
    -   The most famous relationship between conditional probailities is
    -   **Bayes' Theorem**: $p(A\cap B) = p(B|A)p(A)$

### Combinatorics/Counting

-   **Permutations**: ordered arrangements of members of a set. So how many ways are there to permute the last three letters of the alphabet?
    -   So we need to calculate the number of sequences of $x,y,z$ that we can generate.
    -   Let's look at all those sequences. How many different possibilities are there for the first letter of my sequence?
    -   Four, right, because I can choose any of $x, y, z$.
    -   Ok I've used up one letter.
    -   Now for the second letter in the sequence I have one fewer option than I did before. So now I have two choices.
    -   Then when I get to the end of the sequence I have only _one_ option. So there are $3\times 2\times 1 = 3!$ ways of getting that sequence.
    -   In general, when you're doing permutations (i.e. you care about _order_) you can arrange $N$ elements in $N!$ ways.
-   **Combinations**: unique compositions of members of a set. Here we are not concerned with order. If you have a set that has $t$ categories, so let's say you have red, green, and blue balls, then $t=3$, and then you have $n_i$ objects in each category, then number of ways to you can arrange the elements of the set are
    $$\Omega = \frac{N!}{n_1! n_2! \cdots n_t!}$$
-   If you have two categories, then you this is where binomial coefficients come in, right? $$C(k, N) = {N\choose k} = \frac{N!}{k!(N-k)!}$$

#### Example: Bose-Einstein statistics
- I would not expect for you to be able to do this problem without help because it involves a "trick." But it's also a very cool examples
- _How many ways can $n$ indistinguishable particles be put into $M$ boxes?_
- Here's the trick: we're going to treat the particles _and_ the boxes as objects! So what do I mean?
    - Imagine you lay out your $n$ particles all in a row.
    - Then you divide up the particles by sticking $M-1$ partitions in between the particles at random.
    - It's the same problem, right, we have our particles in $M$ boxes, but now we're going to ask: "What are all the ways to arrange $n$ indistinguishable particles and $M-1$ indistinguishable partitions?"
    - Now it's just a binomial coefficient. I'm going to use extra parentheses just to make everthing super clear:
    $$\frac{((M-1)+n)!}{(M-1)!n!}$$
    - we have $(M-1 + n)$ total objects, partitions and particles, which, if they were distinguishable could be arranged in $(M-1+n)!$ ways, but because they are indistinguishable, we correct for the overcounting using this denominator.

### Practice problems
- Again, I would encourage you to do some practice problems or skim old statistics textbooks or look online at examples. I wouldn't ask you anything quite this tricky on homework but it's important to flex your combinatorial muscles a bit before stat mech.
- Heading into the home stretch for probability

### Important probability distributions

I'm gonna blast through this ok? I want these distributions in your notes, but I don't really want to _do_ anything with them yet.

1) Gaussian:
$$ p(x) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp{\left[-\frac{(x-\lambda)^2}{2\sigma^2}\right]}$$

-   This distribution is completely specified by it's mean $\lambda$ and variance $\sigma^2$. How could I prove that those parameters are actually the mean and variance?
-   What are the definitions of mean and variance?
$$\langle x\rangle = \int xp(x)dx = \lambda $$
$$\langle x^2\rangle - \langle x \rangle ^2 = \int x^2 p(x) dx - \lambda^2$$
-   You could integrate the distribution against the random variable $x$ and then against $x^2$ and prove to yourself that indeed $\lambda$ and $\sigma^2$ are the mean and variance. But that integration is naasstttyyy.
-   There are some extraordinarily clever ways of calculating means and variances using something called cumulants. I won't go through them here but if you're curious, head to [this lecture](https://ocw.mit.edu/courses/physics/8-333-statistical-mechanics-i-statistical-mechanics-of-particles-fall-2013/lecture-notes/MIT8_333F13_Lec5.pdf)

2) Binomial:
- describes random variable with two outcomes $A$ and $B$, relative probabilites $p_A$ and $p_B$.
- the probability that $A$ occurs exactly $N_A$ times is
$$p(N_A) = {N\choose{N_A}} p_A^{N_A} p_B^{N-N_A}$$
- I don't really want to say much more than that. Maybe there'll be a homework problem on the binomial distribution, that could be good.

3) Poisson:
- I don't think this distribution is going to come up in _my_ lectures, but I think it'll come up in later stuff, so I'll go ahead and introduce it now.
- This distribution is a limit of the binomial distribution where the number of trials is significantly larger than the number of successes $N >> k$. - So radioactive decay is a very good example of this where you have very rare decays occuring over relatively long periods of time.
- The probability is given by $$ P(k, t) = \frac{e^{-\alpha t}(\alpha t)^k}{k!}$$
    - $k$ is the number of successes and here we're looking at number of successes in a time interval $t$.
    - $\alpha$ is the success rate, so $\alpha t$ is the probability of "success" in an interval $t$ . So $$p = \alpha dt$$
    - Most of you are probably used to seeing $\alpha t$ merged into a single constant $\lambda$. I have kept these things separate because you'll want to be thinking about these things separately in one of your homework problems.
