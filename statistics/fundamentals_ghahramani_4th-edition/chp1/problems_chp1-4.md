# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

## Section 1.4 Review Problems

* **Example 1**
  * No! There are more ways to make an 11 vs. a 12 when using two die.
* **Example 3**
  * $0.33 + 0.07 = 0.4$ so there is a 40% chance the next president has an O blood type.
* **Example 5**
  * $P(E) = 0.015$, $P(H) = 0.025$, $P(EH) = 0.0073$
  * $P(E \cup H) = 0.015 + 0.025 - 0.0073 = 0.0327$
  * $P(E \cup H)^c = 1 - 0.0327 = 0.9673$
* **Example 7**
  * $P(A \cup B) - P(AB) = 0.8 - 0.3 = 0.5$, this is the probability that either event A happens or event B happens but not both.
* **Example 9**
  * $P(B) = \frac23 * P(J)$, $P(B) = \frac43 * P(T)$
  * $\frac32b + b + \frac34b = 1$, $b = \frac4{13}$, $j = \frac6{13}$, $t = \frac3{13}$
* **Example 11**
  * $P(A) = 1 - P(A^c) = 1 - \frac3{13} = \frac{10}{13}$
* **Example 13**
  * $P(A \cup S) = P(A) + P(S) - P(AS)$
  * $0.85 = 0.75 + 0.45 - P(AS)$
  * $P(AS) = 0.35$
* **Example 15 (I kind of disagree with the book)**
  * It's random, but it's not a random uniform distribution.
* **Example 17 (This question is confusing and terribly worded)**
* **Example 19**
  * There are 25 outcomes in the sample space.
  * P(Does better in Calculus I than Calculus II) = $0.09+0.06+0.1+0.08+0.02+0.01+0.03+0.01+0.01 = 0.41$
  * P(Same) = $0.05+0.18+0.07+0.08 = 0.38$
  * P(Does better in Calculus II) = $0.04+0.02+0.08+0.01+0.02+0.04 = 0.21$
* **Example 21**
  * $s = 3p$
  * $s = 2a$
  * $s = 10i$
  * $s + \frac13s + \frac12s + \frac1{10}s = 1$
  * $s = \frac{15}{29} \approx 0.517$
* **Example 23**
  * **(a)** $\frac4{52} = \frac1{13} \approx 0.0769$
  * **(b)**
    * There are 12 face cards. There are 26 black cards. There are 6 face cards that are black. So $26 + 12 - 6 = 32$. Then $\frac{32}{52} = \frac8{13} \approx .615$
    * There are 4 queens, 13 hearts, and 1 queen and heart. So $4 + 13 - 1 = 16$. Then $1 - \frac{16}{52} = \frac{36}{52} = \frac9{13} \approx 0.69$
* **Example 25**
  * $P(D)$= Crime occurs during the day.
  * $P(D^c) = P(N)$ = Crime occurs at night.
  * $P(C)$= Crime occurs in city.
  * $P(C^c) = P(R)$ = Crime occurs outside of city.
  * $P(D) = 0.25$, $P(N) = 0.75$
  * $P(C) = 0.8$, $P(R) = 0.2$
  * $P(DR) = 0.1$, $P(C \cup N) = 0.9$
  * $P(C \cup N) = P(C) + P(N) - P(CN)$
  * $0.9 = 0.8 + 0.75 - P(CN)$, $P(CN) = 0.65$
  * Since we are trying to find $P(NR)$, notice that $P(N) - P(CN) = P(NR)$
  * How? From set theory of course.
    * $N - CN = N(R \cup D)$, by the difference property
    * $NR \cup ND$, by the distribution property
    * $ND = \emptyset$, thus we are left with $NR$
  * So $0.75 - 0.65 = 0.1 = P(NR)$
* **Example 27 (This is a proof which I skipped, it's just the Inclusion-Exclusion Principle)**
* **Example 29**
  * The answer is $\frac7{11}$, but I feel like I'm missing something because the problem was very easy.
* **Example 31**
  * $M$ = A on midterm
  * $F$ = A on final
  * $1 - (M^cF^c) = (M \cup F) = 1 - \frac{11}{33} = \frac{22}{33}$
  * $P(M \cup F) = P(M) + P(F) - P(MF)$
  * $\frac{22}{33} = \frac{17}{33} + \frac{14}{33} - P(MF)$
  * $P(MF) = \frac9{33} = \frac3{11}$
* **Example 33 (Looked it up initially because I have no number sense)**
  * A quadratic equation has no real roots when $b^2 - 4ac \lt 0$.
  * Going through all 36 outcomes from tossing two dice, you'll find 19 combinations result in real roots while 17 result in imaginary roots.
  * $(1,1); (1,2);(1,3);(1,4);(1,5);(1,6);(2,2);(2,3);(2,4);(2,5);(2,6);(3,3);(3,4);(3,5);(3,6);(4,5);(4,6)$ all result in imaginary roots.
* **Example 35**
  * $P(T) = \frac{333}{1000}$ = Probability number is divisible by 3.
  * $P(F) = \frac{200}{1000}$ = Probability number is divisible by 5.
  * $P(FT) = \frac{66}{1000}$ = Probability number is divisible by 3 and 5.
  * **(a)**
    * $P(F^cT) = P(T) - P(FT)$
    * $P(F^cT) = \frac{267}{1000}$
  * **(b)**
    * $P(F \cup T) = P(F) + P(T) - P(FT)$
    * $P(F \cup T) = \frac{467}{1000}$
    * $1 - P(F \cup T) = P(F^cT^c) = \frac{533}{1000}$
* **Example 37**
  * This is a strange problem which I kind of intuited. I reduced the problem to that of a 4 card deck where each card is a different suit. In this case, it is obvious there is a $\frac14$ chance of the last card being a spade.
* **Example 39**
  * The only reason this problem is hard is because it's so convoluted and confusingly worded.

<img src = "images\problem_1-4-39.jpg" alt = "Example 1.19 Solution" width = "400"/>

* **Example 41**
  * Let's say the first number we pick is 100. That means there are 99 possible numbers we could pick the second time that would be smaller. Let's say we picked 99. There would be 98 possible numbers that we could pick that'd be smaller.
  * So we are going to be adding a sequence of numbers in the following fashion: $99 + 98 + 97 + ... + 2 + 1$. This is a famous sequence of numbers which we can add up: $\frac{99 *100}{2} = 4950$. Another way to think about what we're doing is there are 49 pairs of numbers which add up to 100 $1 + 99$, $2 + 98$, ... and there will be a 50 leftover. So our formula will be $49 * 100 + 50 = 4950$.
  * Our probability is then $\frac{4950}{100^2} = 0.495$
* **Example 43**
  * I don't know how to do the proof. Basically though Boole's inequality states the probability of at least one event happening is no greater than the sum of the individual probabilities.
  * The formula described in the textbook is stating that the probability of all the events happening is no less than the sum of the complements of all the individual probabilities minus 1.
* **Example 45**
  * Not too sure about this one.

## Section 1.4 Self-Quiz

* **Example 1**
  * $P(A) = \frac13$, $P(B) = \frac14$, $P(AB) = 0$, $P(A \cup B) = \frac7{12}$, $1 - P(A \cup B) = P(A^cB^c) = \frac5{12}$
* **Example 2**
  * $P(B \cup E) - P(BE)$ = Probability that one, not both, of the assignments get done. $0.95 - 0.6 = 0.35$.
* **Example 3**
  * $P(F \cup E \cup I) = P(F) + P(E) + P(I) - P(EF) - P(FI) - P(EI) + P(EFI)$
    * $\frac23 = \frac13 + \frac12 + \frac14 - \frac15 - \frac15 - \frac15 + x$
    * $x = P(EFI) = \frac{11}{60} \approx 0.1833$