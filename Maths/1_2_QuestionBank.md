# Chapter Practice Bank: Logic & Set Theory
> **Difficulty Level:** Advanced (GATE / TRB IT / TNEB AE)
> **Topics Covered:** Propositional Logic, First-Order Logic, Inference, Set Operations, Relations, and Function Combinatorics.

---

## Part 1: Propositional Logic & Equivalences

### Q1: Nested Implications
**Question:** Which of the following propositional logic formulas is logically equivalent to $P \rightarrow (Q \rightarrow R)$?
* (A) $(P \wedge Q) \rightarrow R$
* (B) $(P \rightarrow Q) \rightarrow R$
* (C) $(P \vee Q) \rightarrow R$
* (D) $P \rightarrow (Q \wedge R)$

> **Answer: (A)**
> **Deconstruction:** Apply the implication identity ($X \rightarrow Y \equiv \neg X \vee Y$) twice. 
> $P \rightarrow (\neg Q \vee R)$ becomes $\neg P \vee \neg Q \vee R$. 
> Using De Morgan's Law, factor out the negation: $\neg (P \wedge Q) \vee R$, which translates back to $(P \wedge Q) \rightarrow R$.

### Q2: Tautology, Contradiction, or Contingency
**Question:** The proposition $(P \vee Q) \wedge (\neg P \wedge \neg Q)$ can be classified as a:
* (A) Contradiction
* (B) Tautology
* (C) Contingency
* (D) Logically equivalent to $P \wedge Q$

> **Answer: (A) Contradiction**
> **Deconstruction:** By De Morgan's Law, $(\neg P \wedge \neg Q) \equiv \neg (P \vee Q)$. 
> The expression becomes $(P \vee Q) \wedge \neg (P \vee Q)$. This is the classic form of a contradiction ($A \wedge \neg A$), which is always False.

### Q3: Distributing Negations
**Question:** What is the logical negation of the statement $P \rightarrow (Q \wedge R)$?
* (A) $P \rightarrow (\neg Q \vee \neg R)$
* (B) $P \wedge (\neg Q \vee \neg R)$
* (C) $\neg P \vee (Q \wedge R)$
* (D) $P \wedge (\neg Q \wedge \neg R)$

> **Answer: (B)**
> **Deconstruction:** The negation of an implication $\neg(X \rightarrow Y)$ is always $X \wedge \neg Y$. 
> Here, $X = P$ and $Y = (Q \wedge R)$. 
> Negating $Y$ using De Morgan's Law gives $\neg Q \vee \neg R$. Combine them to get $P \wedge (\neg Q \vee \neg R)$.

### Q4: Database Logic Filters
**Question:** In a database, a query condition is `NOT (Status = 'Active' AND Age > 30)`. What is the logically equivalent filter?
* (A) `Status != 'Active' OR Age <= 30`
* (B) `Status != 'Active' AND Age <= 30`
* (C) `Status = 'Active' OR Age <= 30`
* (D) `Status != 'Active' OR Age > 30`

> **Answer: (A)**
> **Deconstruction:** Apply De Morgan's Law: $\neg(A \wedge B) \equiv \neg A \vee \neg B$. 
> The operator flips to OR. The strict inequality `>` negates to `<=`.

### Q5: Advanced Equivalence
**Question:** Which expression is logically equivalent to $C \rightarrow (\neg B \rightarrow D)$?
* (A) $(C \wedge \neg B) \rightarrow D$
* (B) $(C \rightarrow \neg B) \rightarrow D$
* (C) $C \rightarrow (\neg B \wedge D)$
* (D) $(C \vee \neg B) \rightarrow D$

> **Answer: (A)**
> **Deconstruction:** Similar to Q1. Convert to ORs: $\neg C \vee (B \vee D)$. 
> Group the non-D terms: $(\neg C \vee B) \vee D$. 
> Factor out the NOT: $\neg(C \wedge \neg B) \vee D$. 
> Convert back to implication: $(C \wedge \neg B) \rightarrow D$.

---

## Part 2: First-Order Logic & Inference

### Q6: Existential Translation
**Question:** Let $E(x)$ mean "$x$ is an employee" and $M(x)$ mean "$x$ is a manager". Translate: "Some employees are not managers".
* (A) $\exists x (E(x) \wedge \neg M(x))$
* (B) $\forall x (E(x) \rightarrow \neg M(x))$
* (C) $\neg \exists x (E(x) \wedge M(x))$
* (D) $\exists x (E(x) \rightarrow \neg M(x))$

> **Answer: (A)**
> **Deconstruction:** "Some" dictates the existential quantifier ($\exists$). Existential statements map to conjunctions ($\wedge$), indicating that a specific entity simultaneously holds both properties.

### Q7: Universal Translation Trap
**Question:** Let $S(x)$ mean "$x$ is a student" and $L(x)$ mean "$x$ is lazy." Translate: "No student is lazy".
* (A) $\forall x (S(x) \rightarrow \neg L(x))$
* (B) $\neg \exists x (S(x) \rightarrow L(x))$
* (C) $\forall x (\neg S(x) \vee L(x))$
* (D) $\exists x (S(x) \wedge \neg L(x))$

> **Answer: (A)**
> **Deconstruction:** "No student is lazy" means "For all individuals in the universe, if they are a student, then they are not lazy."

### Q8: Negating Quantifiers
**Question:** What is the logical negation of $\exists x \forall y (P(x, y) \rightarrow Q(x, y))$?
* (A) $\forall x \exists y (P(x, y) \wedge \neg Q(x, y))$
* (B) $\forall x \exists y (\neg P(x, y) \rightarrow \neg Q(x, y))$
* (C) $\forall x \exists y (P(x, y) \vee \neg Q(x, y))$
* (D) $\exists x \forall y (P(x, y) \wedge \neg Q(x, y))$

> **Answer: (A)**
> **Deconstruction:** Step 1: Flip all quantifiers ($\exists \to \forall$, and $\forall \to \exists$). Step 2: Negate the inner statement. The negation of an implication $(P \rightarrow Q)$ is $(P \wedge \neg Q)$.

### Q9: Modus Tollens
**Question:** If we know that "If it rains ($R$), the ground is wet ($W$)" is True, and the ground is NOT wet ($\neg W$), which rule concludes it did not rain ($\neg R$)?
* (A) Modus Ponens
* (B) Modus Tollens
* (C) Disjunctive Syllogism
* (D) Hypothetical Syllogism

> **Answer: (B) Modus Tollens**
> **Deconstruction:** Modus Tollens states that if an implication is true, the falsity of the consequent guarantees the falsity of the antecedent ($R \rightarrow W, \neg W \vdash \neg R$).

### Q10: Complex Inference
**Question:** Given premises $A \rightarrow B$, $C \rightarrow D$, and $\neg B \vee \neg D$. Which validly follows?
* (A) $\neg A \vee \neg C$
* (B) $A \vee C$
* (C) $\neg A \wedge \neg C$
* (D) $A \wedge C$

> **Answer: (A)**
> **Deconstruction:** This is the Destructive Dilemma. If two conditional statements are true, and at least one of their consequences is false, then at least one of their antecedents must be false.

---

## Part 3: Sets & Cardinality

### Q11: Distributive Laws of Sets
**Question:** The expression $A \cap (B \Delta C)$ is logically equivalent to:
* (A) $(A \cap B) \Delta (A \cap C)$
* (B) $(A \Delta B) \cap (A \Delta C)$
* (C) $(A \cap B) \cup (A \cap C)$
* (D) $A \Delta (B \cap C)$

> **Answer: (A)**
> **Deconstruction:** Just as multiplication distributes over addition, Set Intersection ($\cap$) distributes perfectly over the Symmetric Difference ($\Delta$).

### Q12: Symmetric Identity
**Question:** For any set $A$, what is $A \Delta A$?
* (A) $A$
* (B) The Universal Set
* (C) $\emptyset$
* (D) $2A$

> **Answer: (C) $\emptyset$**
> **Deconstruction:** Symmetric difference means "elements in one set or the other, but not both." Comparing a set to itself, every element is in both. Therefore, the result is empty.

### Q13: Base Inclusion-Exclusion
**Question:** If $|A| = 3$, $|B| = 4$, and $|A \cup B| = 5$, find $|A \cap B|$.
* (A) 1
* (B) 2
* (C) 0
* (D) 7

> **Answer: (B)**
> **Deconstruction:** $|A \cup B| = |A| + |B| - |A \cap B|$. $5 = 3 + 4 - X$. Therefore, $X = 2$.

### Q14: System Nodes (Applied Inclusion-Exclusion)
**Question:** 100 active nodes. 45 run Spark, 50 run Flink, 20 run both. How many run NEITHER?
* (A) 25
* (B) 15
* (C) 5
* (D) 35

> **Answer: (A)**
> **Deconstruction:** Nodes running at least one: $45 + 50 - 20 = 75$. Nodes running neither: $100 - 75 = 25$.

---

## Part 4: Relations

### Q15: Matrix Counting (Anti-Symmetry)
**Question:** Let $A$ have 5 elements. Formula for total distinct Anti-Symmetric relations?
* (A) $2^5 \times 3^{10}$
* (B) $2^{25}$
* (C) $2^{10}$
* (D) $3^{25}$

> **Answer: (A)**
> **Deconstruction:** The 5 diagonal elements have 2 choices (In/Out) = $2^5$. The remaining 10 mirrored pairs (like 1,2 and 2,1) have 3 valid anti-symmetric states (only A, only B, or neither) = $3^{10}$.

### Q16: Matrix Counting (Total Relations)
**Question:** Total possible relations on a set of exactly 3 elements?
* (A) 9
* (B) 64
* (C) 512
* (D) 8

> **Answer: (C)**
> **Deconstruction:** Total pairs in $A \times A = 3 \times 3 = 9$. Total subsets of these pairs = $2^{n^2} = 2^9 = 512$.

### Q17: The "Even Sum" Relation
**Question:** Relation $R$ on integers: $xRy$ if $x + y$ is even. What type of relation is $R$?
* (A) Equivalence Relation
* (B) Reflexive and Symmetric, but not Transitive
* (C) Partial Order Relation
* (D) Symmetric and Transitive, but not Reflexive

> **Answer: (A)**
> **Deconstruction:** Reflexive ($x+x=2x$, even). Symmetric ($x+y$ is even $\implies y+x$ is even). Transitive (if $x+y$ is even, they share parity; if $y+z$ is even, they share parity; thus $x$ and $z$ share parity, so $x+z$ is even).

### Q18: The Inequality Relation
**Question:** Relation $R$ on integers: $aRb$ if $a \leq b$. Properties?
* (A) Reflexive, Symmetric, Transitive
* (B) Reflexive, Anti-symmetric, Transitive
* (C) Anti-symmetric, Transitive, not Reflexive
* (D) Reflexive, Symmetric, not Transitive

> **Answer: (B)**
> **Deconstruction:** This forms a Partial Order. It is Reflexive ($a \leq a$), Anti-symmetric (if $a \leq b$ and $b \leq a$, then $a=b$), and Transitive.

### Q19: Symmetric AND Anti-Symmetric
**Question:** If relation $R$ is both Symmetric and Anti-symmetric, what MUST be true?
* (A) $R$ consists only of pairs where $a = b$ (Diagonal elements).
* (B) Impossible to be both.
* (C) Must be an Equivalence Relation.
* (D) Must be Empty.

> **Answer: (A)**
> **Deconstruction:** Symmetry forces two-way streets. Anti-symmetry forbids them unless $a=b$. Thus, only self-loops (or the empty set) satisfy both rules simultaneously.

---

## Part 5: Functions & Mappings

### Q20: Function Types ($x^3 - x$)
**Question:** $f: \mathbb{R} \rightarrow \mathbb{R}$ defined by $f(x) = x^3 - x$. Describe $f$.
* (A) Onto but not One-to-One
* (B) Bijection
* (C) One-to-One but not Onto
* (D) Neither

> **Answer: (A)**
> **Deconstruction:** Not One-to-One because $f(0)=0$ and $f(1)=0$. It is Onto because a continuous odd-degree polynomial extends to infinity in both directions, covering the entire Y-axis.

### Q21: Function Types ($x^3$)
**Question:** $f: \mathbb{R} \rightarrow \mathbb{R}$ defined by $f(x) = x^3$. Describe $f$.
* (A) One-to-One but not Onto
* (B) Onto but not One-to-One
* (C) Neither
* (D) Bijection

> **Answer: (D)**
> **Deconstruction:** Every distinct $x$ yields a distinct $x^3$ (preserves sign). It covers all real numbers. It is a perfect bijection.

### Q22: Counting Injective Functions
**Question:** Set $A$ has 4 elements, Set $B$ has 5. How many distinct One-to-One functions exist?
* (A) 120
* (B) 625
* (C) 1024
* (D) 24

> **Answer: (A)**
> **Deconstruction:** Permutation without replacement. $5 \times 4 \times 3 \times 2 = 120$.

### Q23: Counting Bijective Functions
**Question:** Set $A$ has 4 elements. Total Bijective functions from $A \to A$?
* (A) 256
* (B) 16
* (C) 24
* (D) 4

> **Answer: (C)**
> **Deconstruction:** A bijection on the same set is a permutation. $4! = 4 \times 3 \times 2 \times 1 = 24$.

### Q24: Complementary Counting Trap
**Question:** $|A| = 3, |B| = 4$. How many functions are NOT One-to-One?
* (A) 40
* (B) 24
* (C) 64
* (D) 12

> **Answer: (A)**
> **Deconstruction:** Total possible functions = $|B|^{|A|} = 4^3 = 64$. Perfect One-to-One functions = $4 \times 3 \times 2 = 24$. Functions that fail to be One-to-One = $64 - 24 = 40$.

### Q25: Function Composition Algebra
**Question:** $f(x) = 2x, g(x) = x + 3$. Find $f(g(x)) - g(f(x))$.
* (A) 0
* (B) 3
* (C) $x + 3$
* (D) -3

> **Answer: (B)**
> **Deconstruction:** $f(g(x)) = 2(x+3) = 2x + 6$. $g(f(x)) = (2x) + 3 = 2x + 3$. Subtracting them: $(2x + 6) - (2x + 3) = 3$.
