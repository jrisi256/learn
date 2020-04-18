# Fundamentals of Probability with Stochastic Processes: 4th Edition

## Book Info

* Author: Saeed Ghahramani
* Title: Fundamentals of Probability with Stochastic Processes: 4th Edition
* Publication Year: 2019

### Chapter 1

#### Review of Set Theory

For all following notation, the sample space is defined by *S*.

* **Subset**: Event *E* is said to be a subset of event *F* if whenever *E* occurs, *F* also occurs. This means all sample points/elements of *E* are contained within *F*.
  * **Notation**: E ⊆ F
* **Equality**: Events *E* and *F* are said to be equal if the occurrence of *E* implies the occurrence of *F* and vice versa.
  * **Notation**: E ⊆ F and F ⊆ E which means E = F.
* **Intersection**: An event is called the intersection of two events, *E* and *F*, if it occurs only whenever *E* and *F* occur simultaneously.
  * **Notation**: E ∩ F or EF
* **Union**: An event is called the union of two events, *E* and *F*, if it occurs whenever at least one of them occurs.
  * **Notation**: E ∪ F
* **Complement**: An event is called the complement of an event, *E*, if it only occurs whenever *E* does not occur.
  * **Notation**: Eᶜ
* **Difference**: An event is called the difference of two events, *E* and *F*, if it occurs whenever *E* occurs but *F* does not.
  * **Notation**; E - F and Eᶜ = S - E and E - F = E ∩ Fᶜ
* **Impossibility**: An event is impossible if there is certainty in its non-occurrence.
  * **Notation**: ∅ and Sᶜ
* **Mutually Exclusive**: If the joint occurrence of two events *E* and *F* is impossible, we say that *E* and *F* are mutually exclusive. Thus *E* and *F* are mutually exclusive if the occurrence of *E* precludes the occurrence of *F* and vice versa.
  * **Notation**: E ∩ F = ∅

Sets and set operations also follow certain laws from arithmetic:

* **Commutative**: E ∪ F = F ∪ E and EF = FE
* **Associative**: E ∪ (F ∪ G) = (E ∪ F) ∪ G and E(FG) = (EF)G
* **Distributive**: (EF) ∪ H = (E ∪ H)(F ∪ H) and (E ∪ F)H = (EH) ∪ (FH)
* **De Morgan's 1st Law**: (E ∪ F)ᶜ = EᶜFᶜ
* **De Morgan's 2nd Law**: (EF)ᶜ = Eᶜ U Fᶜ

#### Review of Probability Axioms (statements which don't need to be proven true)

Let *S* be the sample space of a random phenomenon. Suppose that each event *Aᵢ* of S has a number denoted by *P(A)*. If *P* satisfies the following axioms then it is to be called a probability.

* **Axiom 1**: P(A) ≥ 0
* **Axiom 2**: P(S) = 1
* **Axiom 3**: If {A₁, A₂, A₃, ...} is a sequence of mutually exclusive events then the probability of the union of these events happening is equal to the summation of the probabilities for each of these events.
  * Also known as the axiom of countable additivity.
  * This also implies you can add the probability of mutually exclusive events to get the probability of the union of those events happening.
  * In English, this is usually denoted with *or*. For example, what is the probability of rolling a 1 **OR** a 2 **OR** a 3? You can simply add the individual probabilities to find out. You **CANNOT** do this for events which are not mutually exclusive.
* **Theorem 1.6**: Yes I know my theorems are out of order so sue me. It seemed appropriate to place here. This theorem states that: P(A ∪ B) = P(A) + P(B) - P(AB).
  * For mutually exclusive events, P(AB) is 0 since they never intersect.
  * For non-mutually exclusive events, we have to subtract off the intersection because otherwise we are double counting.
* From **Axiom 3** and **Theorem 1.6**, we can generalize to find the P(A₁ ∪ A₂ ∪ ... Aₙ) i.e. the probability that at least one of the events occur. **Inclusion-Exclusion Principle**: To calculate P(A₁ ∪ A₂ ∪ ... Aₙ) first find all of the possible intersections of these events and calculate those probabilities. Then add the probabilities of those intersections that are formed by an odd number of events and subtract the probabilities of those formed of an even number of events. The intuition being we have to add back in those intersections which we were subtracting out (we don't want to double under-count).

Some theorems we can deduce from these axioms:

* **Theorem 1.1**: P(∅) = 0
* **Theorem 1.2**: If {A₁, A₂, A₃, ..., Aₙ} is a sequence of mutually exclusive events, then the probability of the union of these events happening is equal to the summation of the probabilities for each of these events.
  * Axiom 3 is stated for a countably infinite collection of mutually exclusive events. Theorem 1.2 demonstrates this property holds for a finite collection of mutually exclusive events as well.

We can finally come to some definition of probability. If we have a sample space *S* then we also have ℙ(S) which is the set of all subsets of *S* (aka the **power set**). The aim of probability theory is to associate a number between 0 and 1 to every subset of the sample space. Probability is thus a function *P* whose domain is ℙ(S) and whose range is [0, 1]. Since the domain of the *P* (probability function) is a collection of sets, it is called a **set function**.

In conclusion, probability is a **real-valued**, **non-negative**, **countably additive**, **set function**.

* **Theorem 1.3**: Let *S* be the sample space. If *S* has *N* points that are all equally likely to occur then for any event *A* of *S*: P(A) = N(A) / N.
* **Theorem 1.4**: For any event *A*, P(Aᶜ) = 1 - P(A)
* **Theorem 1.5**: If A ⊆ B then P(B - A) = P(B) - P(A).
  * **Corollary**: If A ⊆ B then P(A) ≤ P(B).
  * **Interpretation**: It is more likely for a computer to have at least one defect versus having exactly one defect.
  * **Note**: The condition of A ⊆ B is very important. For example in rolling a single, fair die let's say we define:
    * B = {1, 2}
    * A = {3, 4, 5}
    * B - A = {1,2}
    * P(B - A) = 1 / 3
    * P(B) = 1 / 3
    * P(A) = 1 / 2
    * P(B) - (P) != P(B - A)