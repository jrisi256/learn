# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

## Section 1.7 Review Problems

* **Example 1**
  * There are 30 possible outcomes.
  * If the bus stops on the $\{10, 11, 12, ..., 30\}$ minute mark, this means the person will have waited for at least 10 minutes. There are 20 of these possible outcomes.
  * Therefore the probability is \frac{20}{30}.
* **Example 3**
  * **(a)** False. The textbook went over a similar example in section 1.6 where they talk about how there are infinitely many points which are the complement of $\frac13$ which has a probability equal to 0 of being picked. So the complement of points of $\frac13$ would have a probability equal to 1, but this is not the sample space.
  * **(b)** False. Our above example illustrates an example, the point $\frac13$ which has a probability of 0, but it is not the empty set.
* **Example 5**
  * The probability is 0 because the probability of picking any particular point is 0 (I think this answers the question).
* **Example 7**
  * $n = 1$, $E_1 = (0, 2]$, $P(E_1) = 1$
  * $n = 2$, $E_2 = (0, 1.5]$, $P(E_2) = 0.8$
  * ...
  * $n = 100$, $E_{100} = (0, 1.01]$, $P(E_{100}) = \frac{302}{500}$
  * As the interval converges to $(0, 1]$ the probability approaches $\frac35$.
* **Example 9**
  * **(a)**
    * $n = 1$, $E_1 = (0, 1)$
    * $n = 2$, $E_1 = (\frac12, \frac34)$
    * ...
    * $n = 100$, $E_{100} = (\frac{99}{200}, \frac{101}{200})$
    * The interval is converging on $\frac12$.
  * **(b)**
    * The probability of choosing $\frac12$ is 0. This sort of follows from example 3. So the *experiment* we are running is equivalent to picking an endless decimal at random. Let $A_1$ be the event that the first digit is 5. Then let $A_n$ be the event the selected number has 0 as its 2nd - n digits. Basically we are trying to pick the number $0.5\overline{00}$.
    * So...
    * $P(A_1) = \frac1{10}$, there are 10 digits to choose from $(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)$
    * $P(A_2) = \frac1{100}$, there are 100 digits to choose from to get 5 and 0.
    * So on and so forth.
    * $P(\frac12) = P(\bigcap\limits_{n=1}^\infty A_i) = \lim_{n\to\infty}(\frac1{10})^n = 0$. This is known as the **Continuity of Probability Function**.
* **Example 11**
  * Our base case must be $P(A_1 \cup A_2) = P(A_1) + P(A_2) - P(A_1A_2)$.
  * $P(A_1A_2) = P(A_1) + P(A_2) - P(A_1 \cup A_2)$.
  * $P(A_1A_2) = 1 + 1 - 1$, (the probability that at least of the events happen is 1).
  * We can now build up to our next case.
  * $P(A_1 \cup A_2 \cup A_3) = P(A_1) + P(A_2) + P(A_3) - P(A_1A_2) - P(A_1A_3) - P(A_2A_3) + P(A_1A_2A_3)$. It would be the case that $P(A_1A_2A_3)$ also equals 1. So on and so forth for all $n$.
* **Example 13**
  * I don't know how to make this a proof.

<img src = "images\problem_1-7-13.jpg" alt = "Example 1.19 Solution" width = "600"/>

* **Example 15**
  * I think this has something to do with uncountable infinite sets. I really don't know though, and the answer in the textbook is supremely unhelpful.

## Section 1.7 Self-Quiz

* **Example 1 (I got tricked on this question)**
  * The probability that two events intersect equaling 0 **does not** mean they are necessarily mutually exclusive. The intersection has to be  $\emptyset$. They give an example in the textbook where the intersection between events is a single point which has probability 0. So the intersection of the two events has a probability of 0, but they aren't mutually exclusive.
* **Example 2**
  * $n = 0$, $E_0 = [-\frac16, \frac43]$
  * $n = 1$, $E_1 = [0, 1]$
  * ...
  * $n = 100$, $E_{100} = [\frac{95}{294}, \frac6{17}]$
  * $n = 1000$, $E_{1000} = [\frac{995}{2994}, \frac{56}{167}]$
  * ...
  * Converging to $\frac13$ which has a probability of 0 of being picked.