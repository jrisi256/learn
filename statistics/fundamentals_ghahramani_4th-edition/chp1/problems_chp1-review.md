# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

## Chapter 1 Review Problems

* **Example 1**
  * There are 231 possible response times for the animal $[200, 430]$.
  * There are 126 possible response times for the animal to respond within 3.25 minutes $[200, 325]$.
  * $P(A) = \frac{126}{231} \approx 0.545$
* **Example 3**
  * **(a)** $E_1 = \{1, 3, 5, 7, 9\}$
  * **(b)** $E_2 = \{3, 6, 9\}$
* **Example 5 (Slight notation omission, forgot to include the complements)**
  * $E_1E_2E_3 \cup E_1^cE_2E_3 \cup E_1E_2^cE_3 \cup E_1E_2E_3^c$
* **Example 7**
  * **(a)** False. We know nothing about often $B$ occurs when $A$ doesn't occur.
  * **(b)** True. If $B$ always happens when $A$ happens, then we know that if $B$ didn't happen, $A$ must not have happened. Otherwise $B$ would have happened.
* **Example 9 (Messed up sample space a little)**
  * $S = \{AJ, AJ^c, A^cJ, A^cJ^c\}$
  * $E = AJ \cup A^cJ \cup AJ^c$
* **Example 11**
  * **(a)** The events aren't mutually exclusive therefore some *double-counting* is happening. This will lead to an overestimation of how likely it is for at least one of the events to happen.
  * **(b)** The events aren't independent. For example, the probability of $A$ happening influences the probability of $B$ happening. In this case, you cannot simply multiply the probabilities to get the probability of both happening.
* **Example 13**
  * $P(I \cup T) = P(T) + P(I) - P(IT)$
  * $0.9 = 0.8 + 0.6 - P(IT)$
  * $P(IT) = 0.5$
* **Example 15**
  * $N(M \cup S) = N(M) + N(S) - N(MS)$
  * $N(M \cup S) = 37 + 20 - 12 = 45$
  * $63 - N(M \cup S) = 63 - 45 = 18 = N(M \cup S)^c = N(M^cS^c)$
* **Example 17**
  * $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(AB) - P(AC) - P(BC) + P(ABC)$
  * $P(A \cup B \cup C) = P(A) + P(B) + P(C) - 0 - 0 - 0 + P(ABC)$
  * In the case that $P(AB), P(AC), P(BC)$ are all $0$, then $P(ABC)$ must also be $0$. I don't have a written proof for this, but I am able to visualize it.
* **Example 19**
  * $P(E \cup R \cup Y) = P(E) + P(R) + P(Y) - P(ER) - P(EY) - P(RY) + P(ERY)$
  * $0.8 = 0.6 + 0.3 + 0.45 - 0.25 - 0.2 - 0.4 + P(ERY)$
  * $P(ERY) = 0.3$
* **Example 21**
  * $\frac{10}{13} = P(A) + P(B) + P(C)$, don't need to worry about intersections because they're all $0$.
  * $A = 2B, B = 3C, A = 6C$
  * $\frac{10}{13} = A + \frac12A + \frac16A$
  * $A = \frac6{13}, B = \frac3{13}, C = \frac1{13}$
* **Example 23**
  * $S = \{A_1B_1, A_1B_2, A_1B_3, A_1B_4, A_2B_1, A_2B_2, A_2B_3, A_2B_4, A_3B_1, A_3B_2, A_3B_3, A_3B_4, A_4B_1, A_4B_2, A_4B_3, A_4B_4\}$
  * The probability they chose the same tire would be $\frac4{16} = \frac14 = 0.25$.
* **Example 25**
  * $(A - B) \cup (B - A)$ is known as the symmetric difference and is often (but not always) denoted like so $A \triangle B$. However, it's also equivalent to $P(A \triangle B) = P(A) + P(B) - 2P(AB)$. I can appreciate this fact visually. You subtract the intersection once because you are overcounting otherwise when trying to find the probability of at least one of the events happening (or both). You subtract out the intersection again to find the probability only one of the events happen (not both).
* **Example 27 (I always hate the book's notation for these problems)**
  * $S = \{a_1a_2b_1b_2c_1c_2; a_1c_2b_1b_2c_1a_2; ...\}$, there will be $6!$ combinations.
  * I'm going to use a picture to describe the event that the last two books come from the same publisher.

<img src = "images\problem_review1-27.jpg" alt = "Chapter 1 Review Example #27 Solution" width = "600"/>

* **Example 29**
  * $A = O, B = \frac1{10}A, B = 2C$
  * $O + B + A + C = 1$
  * $1 = A + \frac1{10} + A + \frac1{20}A$
  * $A = \frac{20}{43}, O = \frac{20}{43}, C = \frac1{43}, B = \frac2{43}$
* **Example 31 (I had to look this one up because I have bad number sense)**

<img src = "images\problem_review1-31.jpg" alt = "Chapter 1 Review Example #31 Solution" width = "600"/>

* **Example 33**

<img src = "images\problem_review1-33.jpg" alt = "Chapter 1 Review Example #33 Solution" width = "500"/>

* **Example 35 (This problem was really fucking annoying)**

<img src = "images\problem_review1-35.jpg" alt = "Chapter 1 Review Example #35 Solution" width = "400"/>

## Chapter 1 Self-Test

* **Example 1**

<img src = "images\problem_selftest1-1.jpg" alt = "Chapter 1 Self-Test #1 Solution" width = "550"/>

* **Example 2 (I did not follow the notation of the book)**
  * $800 \le T + F + C + K + S \le 1300$
  * $E = |S - C| \le 100$, the difference between the number of baseballs and soccer balls will not exceed 100.
* **Example 3**
  * $S = \{A_1A_2A_3; A_1A_2A_3^c; A_1A_2^cA_3; A_1^cA_2A_3; A_1^cA_2^cA_3; A_1A_2^cA_3^c; A_1^cA_2A_3^c; A_1^cA_2^cA_3^c\}$
  * $E = \{A_1A_2A_3^c; A_1A_2^cA_3; A_1^cA_2A_3; A_1^cA_2^cA_3; A_1A_2^cA_3^c; A_1^cA_2A_3^c; A_1^cA_2^cA_3^c\}$
* **Example 4**
  * $P(A \cup B) = P(A) + P(B) - P(AB)$
  * $P(A \cup B) = 0.134 + 0.113 - 0.0226 = 0.2244$
  * $P(A \cup B)^c = 1 - 0.2244 = 0.7756 = P(A^cB^c)$
* **Example 5**
  * $P(E) = 0.4, P(E^cF^c) = 0.35, P(E \cup F) = 0.65$
  * $P(E \cup F) - P(E) = (E \cup F)E^c = E^cF = 0.25$
* **Example 6**

<img src = "images\problem_selftest1-6.jpg" alt = "Chapter 1 Self-Test #6 Solution" width = "550"/>

* **Example 7**
  * $E_1 = (0,2), P(E_1) = \frac23$
  
  * $E_2 = (\frac12, \frac32), P(E_2) = \frac56$
  
  * ...
  
  * $P(E_{100}) = \frac{201}{300}$
  
  * Convering to $\frac23$
* **Example 8**
  * $1 - 0.54 = 0.46$
* **Example 9 (99% certain the book has a typo in this problem)**
  * Let's work through the problem as presented by the book.
  * $P(L) = 0.32, P(A) = 0.43, P(A^cL^c) = 0.13, P(A \cup L) =0.87$
  * This would lead to the following conclusion, $0.12 = -P(AL)$ which is impossible.
  * In the solution guide, it says $P(AL) = 0.12$ so it seems like the error got introduced because they forgot about the sign.
  * If we want $P(AL) = 0.12$, then $P(A^cL^c) = 0.37$ which would lead to $P(A \cup L) =0.63$.
  * Then we could do $P(A \cup B) - P(AB) = 0.51$.
  * We could also do $P(A) + P(B) - 2P(AB) = 0.51$.
* **Example 10**
  * $P(E \cup L \cup N) = P(E) + P(L) + P(N) - P(EL) - P(EN) - P(LN) + P(ELN)$
  
  * $P(E \cup L \cup N) = \frac13 + \frac12 + \frac13 - \frac34 + 0$
  
  * $P(E \cup L \cup N) = \frac5{12}$

  * $1 - P(E \cup L \cup N) = P(E^cL^cN^c) = \frac7{12}$