# Engineering Mathematics: Mathematical Logic (Complete Reference)
> **Coverage:** Propositional Logic, First-Order Logic, Inference Rules, and Normal Forms.
> **Target Exams:** GATE, TRB IT, TNEB AE.

---

## 1. Core Concepts and Connectives

Mathematical logic translates natural language into formal symbols to remove ambiguity.

| Name | Symbol | Translation | Shortcut / Truth Condition |
| :--- | :--- | :--- | :--- |
| **Negation** | $\neg P$ | NOT $P$ | Opposite of $P$. |
| **Conjunction** | $P \wedge Q$ | $P$ AND $Q$ | True ONLY if **both** are True. |
| **Disjunction** | $P \vee Q$ | $P$ OR $Q$ | False ONLY if **both** are False. |
| **Implication** | $P \rightarrow Q$ | If $P$ then $Q$ | False ONLY if $T \rightarrow F$ (Broken Promise). |
| **Bi-conditional** | $P \leftrightarrow Q$ | $P$ iff $Q$ | True if $P, Q$ have the **same** value. |

### Essential Identities

The most frequent transformation in competitive exams:

$$P \rightarrow Q \equiv \neg P \vee Q$$

**The Contrapositive:**

$$(P \rightarrow Q) \equiv (\neg Q \rightarrow \neg P)$$

**De Morgan's Laws:**

$$\neg (P \wedge Q) \equiv \neg P \vee \neg Q$$

$$\neg (P \vee Q) \equiv \neg P \wedge \neg Q$$

---

## 2. Rules of Inference

Inference rules allow us to move from **Premises** to a **Conclusion** without constructing a full truth table.

1.  **Modus Ponens:** If $P \rightarrow Q$ and $P$ are true, then $Q$ is true.
2.  **Modus Tollens:** If $P \rightarrow Q$ and $\neg Q$ are true, then $\neg P$ is true.
3.  **Hypothetical Syllogism:** If $P \rightarrow Q$ and $Q \rightarrow R$, then $P \rightarrow R$.
4.  **Disjunctive Syllogism:** If $P \vee Q$ and $\neg P$, then $Q$.
5.  **Constructive Dilemma:** If $(P \rightarrow Q) \wedge (R \rightarrow S)$ and $(P \vee R)$, then $(Q \vee S)$.

---

## 3. First-Order Logic (FOL)

FOL uses quantifiers to define the scope of a variable.

* **Universal ($\forall x$):** "For every $x$". Usually paired with Implication ($\rightarrow$).
    * *Example:* $\forall x (S(x) \rightarrow L(x))$ (All students have laptops).
* **Existential ($\exists x$):** "There exists some $x$". Usually paired with Conjunction ($\wedge$).
    * *Example:* $\exists x (S(x) \wedge L(x))$ (Some students have laptops).

### Negating Quantifiers

$$\neg (\forall x, P(x)) \equiv \exists x, \neg P(x)$$

$$\neg (\exists x, P(x)) \equiv \forall x, \neg P(x)$$

---

## 4. Deconstructed Practice Problems (1–18)

### Problem 1: Negation of Implication
**Question:** Simplify $\neg (P \rightarrow Q)$.
**Deconstruction:** Using the identity $P \rightarrow Q \equiv \neg P \vee Q$, we get $\neg (\neg P \vee Q)$. Applying De Morgan's Law, the negation flips $\neg P$ to $P$, $\vee$ to $\wedge$, and $Q$ to $\neg Q$.
**Solution:** $P \wedge \neg Q$.

### Problem 2: Logical Equivalence
**Question:** Equivalent to "If I study hard ($P$), then I will pass ($Q$)"?
**Deconstruction:** Only the **Contrapositive** is logically equivalent. This requires swapping the terms and negating both.
**Solution:** $\neg Q \rightarrow \neg P$.

### Problem 3: FOL Translation
**Question:** Translate "Every student in the class has a laptop."
**Deconstruction:** "Every" implies $\forall$. In FOL, universal statements usually take the form "If $x$ is a student, then $x$ has a laptop."
**Solution:** $\forall x (S(x) \rightarrow L(x))$.

### Problem 4: "Only If"
**Question:** Translate "Internet ($I$) only if Subscriber ($S$)."
**Deconstruction:** "Only if" identifies a **Necessary** condition, which goes on the right side of the arrow.
**Solution:** $I \rightarrow S$.

### Problem 5: Nested Quantifiers
**Question:** Translate $\forall x \exists y L(x, y)$ ($x$ loves $y$).
**Deconstruction:** Read left to right. "For every person $x$, there is at least one person $y$ that $x$ loves."
**Solution:** "Everybody loves somebody."

### Problem 6: Tautology Check (Inference)
**Question:** Is $((P \rightarrow Q) \wedge \neg Q) \rightarrow \neg P$ a tautology?
**Deconstruction:** This is the symbolic form of **Modus Tollens**. If we try to make it false by setting the conclusion $\neg P$ to False ($P=T$), the premise $((T \rightarrow Q) \wedge \neg Q)$ becomes False regardless of $Q$.
**Solution:** Yes, it is a Tautology.

### Problem 7: "Unless" Logic
**Question:** "System fails ($F$) unless backup kicks in ($B$)."
**Deconstruction:** "A unless B" means "If not B, then A" ($\neg B \rightarrow A$) OR "If not A, then B" ($\neg A \rightarrow B$).
**Solution:** $\neg B \rightarrow A$ (also equivalent to $B \vee F$).

### Problem 8: Constructive Dilemma
**Question:** Given $P \rightarrow Q, R \rightarrow S$, and $P \vee R$.
**Deconstruction:** Since we have either $P$ or $R$, we are guaranteed to get either result $Q$ or $S$.
**Solution:** $Q \vee S$.

### Problem 9: Negation of Quantifiers
**Question:** Negate $\forall x (P(x) \rightarrow Q(x))$.
**Deconstruction:** $\neg \forall$ becomes $\exists$. The negation of $(P \rightarrow Q)$ is $(P \wedge \neg Q)$.
**Solution:** $\exists x (P(x) \wedge \neg Q(x))$.

### Problem 10: False Hunting
**Question:** Is $P \rightarrow (Q \rightarrow P)$ a Tautology?
**Deconstruction:** Try to make it False. Set the result $(Q \rightarrow P)$ to False ($Q=T, P=F$). Now check the start: $P \rightarrow \dots$. If $P=F$, the whole implication is True.
**Solution:** Yes, it is a Tautology.

### Problem 11: Necessary vs Sufficient
**Question:** If $Square \rightarrow Rectangle$, what is NOT necessarily true?
**Deconstruction:** In $P \rightarrow Q$, $P$ is sufficient and $Q$ is necessary. Reversing them ($Q \rightarrow P$) is the "Converse" and is not guaranteed.
**Solution:** "Being a rectangle is sufficient for being a square" ($R \rightarrow S$).

### Problem 12: FOL Identity
**Question:** Equivalent to $\neg \exists x (P(x) \wedge Q(x))$?
**Deconstruction:** Negate the $\exists$ to get $\forall$. Negate the inside to get $\neg P(x) \vee \neg Q(x)$. This is the OR-form of $P(x) \rightarrow \neg Q(x)$.
**Solution:** $\forall x (P(x) \rightarrow \neg Q(x))$.

### Problem 13: Duality Principle
**Question:** Dual of $(P \wedge Q) \vee \neg P$.
**Deconstruction:** Swap $\wedge$ for $\vee$ and $\vee$ for $\wedge$. Leave $\neg P$ alone.
**Solution:** $(P \vee Q) \wedge \neg P$.

### Problem 14: Bi-conditional
**Question:** Equivalent to $(P \rightarrow Q) \wedge (Q \rightarrow P)$?
**Deconstruction:** This is the definition of a two-way implication (Bi-conditional).
**Solution:** $P \leftrightarrow Q$.

### Problem 15: Universal Instantiation
**Question:** Given $\forall x (P(x) \rightarrow Q(x))$ and $P(a)$.
**Deconstruction:** What is true for the whole set is true for a specific member $a$. Since $P(a)$ is true, $Q(a)$ must follow.
**Solution:** $Q(a)$.

### Problem 16: CNF Conversion
**Question:** CNF of $(P \rightarrow Q) \rightarrow R$.
**Deconstruction:** Convert to $\neg (\neg P \vee Q) \vee R \rightarrow (P \wedge \neg Q) \vee R$. To make it CNF (Product of Sums), distribute the $R$: $(P \vee R) \wedge (\neg Q \vee R)$.
**Solution:** $(P \vee R) \wedge (\neg Q \vee R)$.

### Problem 17: Satisfiability
**Question:** Is $(P \vee Q) \wedge (\neg P \vee \neg Q)$ satisfiable?
**Deconstruction:** This is the XOR gate. It is true if $P=T, Q=F$. Since at least one row in the truth table is True, it is satisfiable.
**Solution:** Yes.

### Problem 18: Functional Completeness
**Question:** Which sets are functionally complete?
**Deconstruction:** A set is complete if it can derive $\{\neg, \wedge, \vee\}$. Both $\{\neg, \vee\}$ and $\{\neg, \rightarrow\}$ can do this.
**Solution:** Both $\{\neg, \vee\}$ and $\{\neg, \rightarrow\}$.

---

## 5. Summary Table for Exams

| Term | Meaning |
| :--- | :--- |
| **Tautology** | Always True. |
| **Contradiction** | Always False. |
| **Satisfiable** | True in at least one case. |
| **Contingency** | Neither Tautology nor Contradiction. |
| **Valid Argument** | Conclusion is True whenever Premises are True. |
