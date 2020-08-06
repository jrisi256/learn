# Fundamentals of Probability with Stochastic Processes: 4th Edition by Saeed Ghahramani - Chapter 1

## Section 1.2 Review Problems

* **Example 1**
  * $S = \{M, I, S, P\}$
  * $A = \{I\}$
* **Example 3**
  * Event $E$ represents at least two heads being flipped.
* **Example 5**
  * **(a)** Events $A$ and $B$ are mutually exclusive since they cannot occur at the same time.
  * **(b)** Events $A$ and $B$ are not complements of each other since $A^c$ would be the case that Vann's card is larger than or equal to Paul's card.
* **Example 7 (I didn't exactly get this question right)**
  * My answer which is kind of wrong $S = \{1, 2, ..., 19\}$, The book answer: $S = \{x: 0 < x < 20\}$
  * I think I thought about this too hard.
    * My programming answer: $x$ = floor($x$)
    * Another clever answer I came up with: $x \in \Bbb Z$
    * The book answer which was my mistaken sample space: $E = \{1, 2, 3, ..., 19\}$
* **Example 9**
  * $E$ is the event that the sum of the outcomes is odd.
  * $F$ is the event that at least one of the dice is 1.
  * $EF$ is the event that the sum of the two dice is odd and at least one of them was 1. We can infer from this that at most one of the die is a 1 and the other die is an even number.
  * $E^cF$ is the event that the sum of the two dice isn't odd and at least one of the die is 1. We can infer that this means the other die must be odd.
  * $E^cF^c$ is the event that the sum of the two dice is not odd and neither die is a 1. We can infer from this that both dice must be even, or they must be either 3 or 5.
* **Example 11**
  * $S = \{0 \le x \le 130\}$
  * $A = \{0, 1, 2, ..., 15\} \cup \{45, 46, 47, ..., 60\} \cup \{60, 61, 62, ..., 75\} \cup \{105, 106, 107,..., 120\} \cup \{120, 121, 122, ..., 130\}$
  * $A = \{0 \le x \le 15\} \cup \{45 \le x \le 75\} \cup \{105 \le x \le 120\}$
* **Example 13 (Almost got this one right)**
  * The event represents at least two tails being flipped, **consecutively**. Missed that last part.
* **Example 15 (Book used different notation from me)**
  * $S = \{(H_1, H_2); (H_1, H_3); (H_1, H_1); (H_2, H_1); (H_2, H_2); (H_2, H_3); (H_3, H_1); (H_3, H_2); (H_3, H_3)\}$
  * $A = \{(H_1, H_1); (H_2, H_2); (H_3, H_3)\}$
* **Example 17**
  * Band Saws = 30,000 - 36,000
  * Reciprocating Saws = 28,000 - 33,000
  * Hole Saw = 300,000 - 600,000
  * $S = \{30000 \le b \le 36000\} \cup \{28000 \le r \le 33000\} \cup \{300000 \le h \le 600000\}$
  * $A = \{b \ge 33000\} \cup \{h \lt 435000\}$
* **Example 19 (Set theory, lazy and looked it up but still had to work it out)**
  * **(a)** This is a case of the distributive law.
    * $(E \cup G)(F \cup G) = (EG) \cup F$
  * **(b)**
    * $(E \cup F)(E^c \cup F)(E \cup F^c)$
    * $(E^c \cup F)(E \cup F^c) = (E^cE) \cup (E^cF^c) \cup (FE) \cup (FF^c)$, by the Distributive Law
      * $(E^cE)$ and $(FF^c)$ simplify to $\emptyset$.
    * $(E \cup F) \cap [(FE) \cup (E^cF^c)] = [(E^cF^c) \cap (E \cup F)] \cup [(FE) \cap (E \cup F)]$, by the Distributive Law.
      * $[(E^cF^c) \cap (E \cup F)]$ simplifies to $\emptyset$ by DeMorgan's Law.
    * $(FE) \cap (E \cup F)$ simplifies to $FE$.
* **Example 21 (Basically got it right but my notation was a bit off)**
  * $E_t = \{A_1, A_2, ..., A_n\}$
* **Example 23 (More set theory stuff I looked up)**
  * **(a)**
    * $(E - EF) \cup F = E \cup F$
    * $E - EF = E \cap (E^c \cup F^c)$
    * $(EE^c) \cup (F^cE) \cup F$
    * $(F^c \cup F) \cap (F \cup E)$
    * $S \cap (F \cup E)$
    * True
  * **(b)** Just by looking at it, I saw there was going to be no union operation in the resulting equation. This is false.
  * **(c)** This equation on the other hand is very true. I saw it pretty quickly. It is a simple application of DeMorgan's First Law.
  * **(d)** Thinking about this visually, I see how this is true. The intersection of all these events must be a subset of the union of all the events.
* **Example 25 (I thought about this question a bit too hard)**
  * **(a)** 
    * $A_n$ = Event that 1st head occurs on "nth" flip.
    * S = $\bigcup\limits_{n = 1}^\infty A_n$ or $S = \{H, TH, TTH, TTTH, ...\}$
  * **(b)** $\bigcup\limits_{n = 1}^\infty A_{2n - 1} = \{H, TTH, TTTTH, ...\}$
* **Example 27**
  * $\bigcup\limits_{i = 1}^\infty E_i$ = The number is somewhere between $-\frac12$ and $\frac12$.
  * $\bigcap\limits_{i = 1}^\infty E_i$ = As we go to infinity, the number becomes 0.
* **Example 29**
  * **(a)**
    * $(A - AB) \cup B = A \cup B$
    * $A \cap (A^c \cup B^c) \cup B$
    * $(A^cA \cup AB^c) \cup B$
    * $(A \cup B) \cap (B^c \cup B)$, giving us our proof
  * **(b)**
    * $(A \cup B) - AB = AB^c \cup A^cB$
    * $(A \cup B) \cap (A^c \cup B^c)$, by the property of the $-$ operator and DeMorgan's Law.
    * $(AA^c) \cup (AB^c) \cup (A^cB) \cup (BB^c)$, by the Distributive Law
    * $(AB^c) \cup (A^cB)$, giving us our proof
* **Example 31 (I don't really understand the notation even if I understand the problem)**
  * Well there is going to be $7!$ ways of arranging the books. The notation is as follows...
    * $x_i \in A, 1 \le i \le 7, x_i \neq x_j$ if $i \neq j$
    * A = set of books $\{a_1, a_2, ..., a_7\}$
    * This notation is supposed to represent the set of all 7-letter words such that no letter is repeated. I.e. the set of all 7 combinations of arranging the books.
  * E = Given that three of the seven books are a 3-volume dictionary, the event that they are standing side-by-side in increasing order.
    * Let $a_1, a_2, a_3$ be the 3-volume dictionaries.
    * $\{a_1, a_2, a_3, x_i, x_j, x_l, x_m\} \cup \{x_i, a_1, a_2, a_3, x_j, x_l, x_m\} \cup \{x_i, x_j, a_1, a_2, a_3, x_l, x_m\} \cup \{x_i, x_j, x_l, a_1, a_2, a_3, x_m\} \cup \{x_i, x_j, x_l, x_m, a_1, a_2, a_3\}$
    * This means there are $4! * 5$ or $5!$ ways of arranging the books. We're effectively treating the 3-volume dictionary set as a single book.
    * $\{x_1x_2x_3x_4x_5x_6x_7 \in S\}$ where $x_ix_{i+1}x_{i+2} = a_1a_2a_3$ for some i such that $1 \le i \le 5$. This is the strange book notation I'm not so comfortable with.
* **Example 33 (I can't really figure this one out.)**

## Section 1.2 Self-Quiz

* **Example 1**
  * A = 
  * (Bill, Jody, Karl, Ann); (Bill, Ann, Karl, Jody)
  * (Karl, Jody, Bill, Ann); (Karl, Ann, Bill, Jody)
  * (Ann, Bill, Jody, Karl); (Jody, Bill, Ann, Karl)
  * (Ann, Karl, Jody, Bill); (Jody, Karl, Ann, Bill)
* **Example 2 (Had to look up how to express in proper notation**
  * $\bigcap\limits_{i = 1}^{100} E_i$, This means all patients survived.
  * $\{E_{1x}E_{2l}E_{3l}...E_{100l}\} \cup \{E_{1x}E_{2x}E_{3l}...E_{100}\} \cup ...$. This is my unprofessional way of notating the event that exactly one patient dies.
  * $\bigcup\limits_{i = 1}^{100} E_1E_2...E_{i-1}E_i^cE_{i+1}...E_{100}$. This is the book notation for notating the event that exactly one patient died.
* **Example 3 (Missed a step so had to look up the answer)**
  * $(E \cup F)(F \cup G)(EG \cup F^c)$
    * $(E \cup F)(F \cup G) = (EG \cup F)$, by *undoing* the distributive law.
  * $(EG \cup F)(EG \cup F^c)$
  * $(EG \cap EG) \cup (FF^c) \cup (EFG) \cup (EF^cG)$, by the distributive law.
    * $(EFG) \cup (EF^cG) = EG$, by page 7 (page 28 of pdf).
  * $EG \cup EG \cup FF^c = EG$
* **Example 4**
  * $E_1E_2E_4E_7 \cup E_1E_2E_5E_6E_7 \cup E_1E_3E_5E_6E_7 \cup E_1E_3E_4E_7$