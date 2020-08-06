# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

## Section 1.2

**Sample space**: Set of all possible outcomes usually denoted by $S$.  
**Event**: Subsets of the sample space i.e. specific individual outcomes or specific sets of outcomes.

For all following notation, the sample space is defined by $S$.

* **Subset**: Event $E$ is said to be a subset of event $F$ if whenever $E$ occurs, $F$ also occurs. This means all sample points/elements of $E$ are contained within $F$. Denoted  by $E \subseteq F$
* **Equality**: Events $E$ and $F$ are said to be equal if the occurrence of $E$ implies the occurrence of $F$ and vice versa.
  * $E \subseteq F$ and $F \subseteq E$ which means $E = F$.
* **Intersection**: An event is called the intersection of two events, $E$ and $F$, if it occurs only whenever $E$ and $F$ occur simultaneously. Denoted by $E \cap F$ or $EF$
* **Union**: An event is called the union of two events, $E$ and $F$, if it occurs whenever at least one of them occurs. Denoted by $E \cup F$.
* **Complement**: An event is called the complement of an event, $E$, if it only occurs whenever $E$ does not occur. Denoted by $E^{c}$.
* **Difference**: An event is called the difference of two events, $E$ and $F$, if it occurs whenever $E$ occurs but $F$ does not.
  * $E - F$ and $E^{c} = S - E$ and $E - F = E \cap F^{c}$
* **Impossibility**: An event is impossible if there is certainty in its non-occurrence. Denoted by $\varnothing$ and $S^{c}$
* **Mutually Exclusive**: If the joint occurrence of two events $E$ and $F$ is impossible, we say that $E$ and $F$ are mutually exclusive. Thus $E$ and $F$ are mutually exclusive if the occurrence of $E$ precludes the occurrence of $F$ and vice versa. Denoted by $E \cap F = \varnothing$.

Sets and set operations also follow certain laws from arithmetic:

* **Commutative**: $E \cup F = F \cup E$ and $EF = FE$
* **Associative**: $E \cup (F \cup G) = (E \cup F) \cup G$ and $E(FG) = (EF)G$
* **Distributive**: $(EF) \cup H = (E \cup H)(F \cup H)$ and $(E \cup F)H = (EH) \cup (FH)$
* **De Morgan's 1st Law**: $(E \cup F)^{c} = E^{c}F^{c}$
* **De Morgan's 2nd Law**: $(EF)^{c} = E^{c} \cup F^{c}$

## Section 1.3

**Axioms**: Self-evident or self-true statements which do not need proving. Simply assumptions (assumed true) which you can use to begin building more theory.  
**Theorems**: Through logical argumentation new statements emerge from our original axioms. These new statements are **theorems** and must be proven. 

Let $S$ be the sample space of a random phenomenon. Suppose that each event $A_{i}$ of $S$ has a number denoted by $P(A)$. If $P$ satisfies the following axioms then it is to be called a probability of A.

* **Axiom 1**: $P(A) \ge 0$
* **Axiom 2**: $P(S) = 1$
* **Axiom 3**: If $\{A₁, A₂, A₃, ...\}$ is a sequence of mutually exclusive events then the probability of the union of these events happening is equal to the summation of the probabilities for each of these events.
  * **Notation**: $P(\bigcup\limits_{i=1}^\infty A_i) = \sum\limits_{i=1}^\infty P(A_i)$
  * Also known as the axiom of countable additivity.
  * This also implies you can add the probability of mutually exclusive events to get the probability of the union of those events happening.
  * In English, this is usually denoted with **or**. For example, what is the probability of rolling a 1 **OR** a 2 **OR** a 3? You can simply add the individual probabilities to find out. You **CANNOT** do this for events which are not mutually exclusive.

We can finally come to some definition of probability. If we have a sample space $S$ then we also have $\mathcal{P}(S)$ which is the set of all subsets of $S$ (aka the **power set**). The aim of probability theory is to associate a number between 0 and 1 to every subset of the sample space. Probability is thus a function $P$ whose domain is $\mathcal{P}(S)$ and whose range is $[0, 1]$. Since the domain of the $P$ (probability function) is a collection of sets, it is called a **set function**.

In conclusion, probability is a **real-valued**, **non-negative**, **countably additive**, **set function**.

* **Theorem 1.3**: Let $S$ be the sample space. If $S$ has $N$ points that are all equally likely to occur then for any event $A$ of $S$: $P(A) = \frac{N(A)}{N}$ where $N(A)$ is the number of points of $A$.

## Section 1.4

* **Theorem 1.4**: For any event $A$, $P(A^{c}) = 1 - P(A)$.
* **Theorem 1.5**: If $A \subseteq B$ then $P(B - A) = P(B) - P(A)$.
  * **Corollary**: If $A \subseteq B$ then $P(A) \le P(B)$.
  * **Interpretation**: It is more likely for a computer to have at least one defect versus having exactly one defect.
  * **Note**: The condition of $A \subseteq B$ is very important. For example in rolling a single, fair die let's say we define:

$$B = \{1, 2\}$$
$$A = \{3, 4, 5\}$$
$$B - A = \{1,2\}$$
$$P(B - A) = \frac{1}{3}$$
$$P(B) = \frac{1}{3}$$
$$P(A) = \frac{1}{2}$$
$$P(B) - P(A) \neq P(B - A)$$

* **Theorem 1.6**: $P(A \cup B) = P(A) + P(B) - P(AB)$.
  * For mutually exclusive events, $P(AB) = 0$ since they never intersect.
  * For non-mutually exclusive events, we have to subtract off the intersection because otherwise we are double counting.
  * We can generalize to find $P(A_{1} \cup A_{2} \cup ... \cup A_{n})$ i.e. the probability that at least one of the $N$ events occur. This is called the **Inclusion-Exclusion Principle**. First find all of the possible intersections of these events and calculate those probabilities. Then add the probabilities of those intersections that are formed by an odd number of events and subtract the probabilities of those formed of an even number of events. The intuition being we have to add back in those intersections which we were subtracting out (we don't want to double under-count).

We should briefly mention here that in the real world probability can be referred to as **odds** which is really just the expression of probability as a ratio.

* The odds in favor of an event $A$ are $r$ to $s$ if $P(A) = \frac{r}{r + s}$
* The odds against event $A$ are $s$ to $r$.
* For example, the probability of drawing an ace from a 52 card deck is $\frac{4}{52}$ or $\frac{1}{13}$ which is approximately equivalent to 7.7%.
  * The odds in favor of drawing an ace are thus 4 to 48 or 1 to 12.
  * The odds against drawing an ace are 12 to 1.

## Section 1.5 - 1.7

Choosing a number at random from a given interval is impossible. It's equivalent to choosing all the digits at once successively. In the real world we turn to pseudo-random number generators and random-enough physical approximations.

The model to keep in mind is you have a box with $a - b + 1$ balls with each ball given exactly one number from $[a, b]$ and each number from $[a, b]$ can be found on only one ball. The balls are completely mixed up so then in a random selection every ball has the same chance as being drawn as any other ball.

## Section 1.8

To perform simulation, we must use pseudo-random numbers. To generate $n$ pseudo-random numbers from a uniform distribution on $(a, b)$, we take an initial value $x_{0} \in (a, b)$ which is called the **seed**. We then construct a function $f$ so that the sequence $\{x_{1}, x_{2}, ..., x_{n}\} \subset (a, b)$ obtained recursively from $x_{i + 1} = f(x_{i}), 0 \le i \le n - 1$ satisfies certain statistical tests for randomness.

Because the numbers generated are rounded to a certain number of decimal places, $f$ can only generate a finite number of pseudo-random numbers. This implies eventually some xⱼ will be generated a second time. From that point on, the same sequence of numbers that appeared after xⱼ's first appearance will reappear. Beyond that point, numbers are no longer sufficiently random. $f$ is constructed in such a way so as to postpone this for as long as possible.

It is surprising that there are deterministic real-valued functions $f$ that for each $i$ generate an $x_{i + 1}$ that is completely determined by $x_{i}$ and yet the sequence $\{x_{1}, x_{2}, ..., x_{n}\}$ will still pass certain statistical tests of randomness.
