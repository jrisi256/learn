# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

* **Example 1.13** (pg. 16 - 17)
  * $S = \{F_{2}F_{2}, F_{3}F_{3}, F_{2}F_{3}, F_{3}F_{2}, F_{4}F_{4}, F_{4}F_{2}, F_{2}F_{4}, F_{3}F_{4}, F_{4}F_{3}\}$
  * P(Two different floors) = $\frac{6}{9} = \frac{2}{3}$
  
* **Example 1.14**
  * $1, 2, 3, 4, 5, 6, 7, 8, 9$, Three of these numbers are divisible by 3. There will then be 111 rows each with 3 numbers divisible. Thus there are $111 * 3 = 333$ possible ways to choose a number that's divisible by 3. The probability would be $\frac{333}{1000}$.
  
* **Example 1.15** (this one was pretty tricky so I had to look at the answer)
  * We're going to define the event that a number is divisible by $k$ as follows $A = \{km: 1 \le m \le [\frac{N}{k}]\}$ where $[\frac{N}{k}]$ is the greatest integer less than or equal to $\frac{N}{k}$ (divide then round down).
  * In this situation, $N(A) = [\frac{N}{k}]$ and $P(A) = \frac{[\frac{N}{k}]}{N}$
  * E.g. $N = 5$, and we want to find the probability a randomly chosen number is divisible by 2 ($k = 2$).
    * $1 \le m \le [\frac{5}{2}]$ which means $N(A) = 2$ and $N = 5$ so $P(A) = \frac{2}{5} = 0.4$.

* **Example 1.16**
  * $P(A \cup B) = P(A) + P(B) - P(AB)$
  * $300 = 160 + P(B) - 120$
  * $N(B) = 260$, $P(B) = 260 / 400 = 65\%$

* **Example 1.17** (I have bad number sense unfortunately. Echoes of **Example 1.14** and **1.15**. I originally tried enumerating everything by hand and observing patterns, but it didn't really work.)
  * $P(A) = \frac{[\frac{1000}{3}]}{1000}$
  
  * $P(B) = \frac{[\frac{1000}{5}]}{1000}$

  * $P(AB) = \frac{[\frac{1000}{5 * 3}]}{1000}$
  
  * $P(A \cup B) = P(A) + P(B) - P(AB)$

  * $P(A \cup B) = \frac{333 + 200 - 66}{1000} = \frac{467}{1000}$

* **Example 1.18**
  * $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(AB) - P(AC) - P(BC) + P(ABC)$
  * $P(A \cup B \cup C) = 0.25 + 0.2 + 0.13 - 0.1 - 0.08 - 0.05 + 0.04 = 0.39$
  * $1 - P(A \cup B \cup C) = P(A^cB^cC^c) = 1 - 0.39 = 0.61$

* **Example 1.19** (Venn Diagram)

<img src = "images\example_1-19.jpg" alt = "Example 1.19 Solution" width = "400"/>