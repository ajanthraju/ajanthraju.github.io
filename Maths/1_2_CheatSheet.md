# Master Formula Cheat Sheet: Logic, Sets, & Relations
> **Target Exams:** GATE, TRB IT, TNEB AE.

---

## 1. Propositional & First-Order Logic

### Core Identities
* **Implication:** $P \rightarrow Q \equiv \neg P \vee Q$
* **Contrapositive (Logically Equivalent):** $P \rightarrow Q \equiv \neg Q \rightarrow \neg P$
* **Converse (Not Equivalent):** $P \rightarrow Q \not\equiv Q \rightarrow P$
* **Inverse (Not Equivalent):** $P \rightarrow Q \not\equiv \neg P \rightarrow \neg Q$

### De Morgan's Laws
* **Logic:** $\neg (P \wedge Q) \equiv \neg P \vee \neg Q$
* **Logic:** $\neg (P \vee Q) \equiv \neg P \wedge \neg Q$
* **Sets:** $(A \cup B)^c = A^c \cap B^c$
* **Sets:** $(A \cap B)^c = A^c \cup B^c$

### Quantifier Negation
When pushing a negation inside, the quantifier flips:
* $\neg \forall x P(x) \equiv \exists x \neg P(x)$
* $\neg \exists x P(x) \equiv \forall x \neg P(x)$

---

## 2. Set Theory & Cardinality
Let $n$ be the total number of elements in a set $S$.

### Subsets
* **Total Subsets (Power Set):** $2^n$
* **Total Proper Subsets:** $2^n - 1$
* **Pairs of Nested Subsets** ($A \subseteq B \subseteq S$): $3^n$

### Inclusion-Exclusion Principles
* **2 Sets:** $$|A \cup B| = |A| + |B| - |A \cap B|$$
* **3 Sets:** $$|A \cup B \cup C| = |A| + |B| + |C| - (|A \cap B| + |B \cap C| + |A \cap C|) + |A \cap B \cap C|$$

### Symmetric Difference (XOR)
Elements in A or B, but not both:
$$|A \Delta B| = |A| + |B| - 2|A \cap B|$$

---

## 3. Relations Combinatorics
For a relation defined on a single set containing $n$ elements (visualized as an $n \times n$ matrix):

* **Total Possible Relations:** $2^{n^2}$
* **Reflexive Relations:** $2^{n^2 - n}$
* **Symmetric Relations:** $2^{\frac{n(n+1)}{2}}$
* **Anti-Symmetric Relations:** $2^n \times 3^{\frac{n^2 - n}{2}}$
* **Equivalence Relations:** Matches the **Bell Numbers** (The number of valid ways to partition a set). 
  * *Sequence for n = 1, 2, 3, 4, 5:* $1, 2, 5, 15, 52$.

---

## 4. Functions & Mappings ($A \to B$)
Let $|A| = m$ (Source/Domain) and $|B| = n$ (Target/Co-domain).

### Standard Mappings
* **Total Functions:** $n^m$ (Target raised to the Source).

### Constrained Mappings
* **One-to-One (Injective):** This is a permutation $P(n, m)$.
  * Formula: $n \times (n-1) \times (n-2) \dots$ for $m$ terms.
  * *Condition:* $m \leq n$.
* **Onto (Surjective) specifically when $n=2$:** * Formula: $2^m - 2$
  * *Condition:* $m \geq n$.
* **Bijections ($A \to A$):** * Formula: $m!$ (Factorial).
  * *Condition:* $m = n$.

### Derangements (The "No Fixed Points" Permutation)
A mapping from $A \to A$ where no element maps back to itself ($f(x) \neq x$).
* **Formula (Subfactorial):** $$!m = m! \left( 1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \dots + (-1)^m \frac{1}{m!} \right)$$
* **Exam Quick-Recall Sequence ($m = 1$ to $5$):**
  * $!1 = 0$
  * $!2 = 1$
  * $!3 = 2$
  * $!4 = 9$
  * $!5 = 44$
