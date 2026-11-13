# Chapter 1 — Communication Tools (Putnam Guide, pp. 9–28)

**Goal of this chapter:** proof technique (contradiction, induction, countability) and, more importantly, *how to write a solution a grader will give 10/10*. Everything here feeds every later chapter.

**How to use this log**
1. Work top to bottom. Tick boxes as you go. Add dated notes under each item — the notes are the point, not the ticks.
2. For every example: cover the solution, attempt it cold (set a timer), *then* read the Scratch + Solution. Two or more days later, re-derive and write it up from a blank page. That second write-up is where proof-writing skill actually gets built.
3. For every exercise: log date, minutes spent, status, and whether your write-up would survive the checklist in §1.5.
4. Status codes: `S` solved cold · `H` solved with a hint/partial look · `R` read solution, understood · `X` not yet.

**Progress**
- [ ] 1.1 Basics
- [ ] 1.2 Important Theorems (all 5 stated and proved by me)
- [ ] 1.3 Classical Examples (1.1–1.5)
- [ ] 1.4 Further Examples (1.6–1.13)
- [ ] 1.5 General Strategies (internalized, checklist copied to desk)
- [ ] 1.6 Exercises — Tier 1 done
- [ ] 1.6 Exercises — Tier 2 done
- [ ] 1.6 Exercises — Tier 3 attempted

---

## 1.1 Basics

**Proof by contradiction.** To prove $q$ from assumption $p$: assume $p$ and $\neg q$, derive a contradiction.

**Proof by induction.** To prove $P(n)$ for all $n \in \mathbb{N}$:
- Basis: prove $P(1)$.
- Inductive step: assume $P(n)$ for some $n \ge 1$, prove $P(n+1)$.

Two traps the guide flags:
- If the step $P(n) \Rightarrow P(n+1)$ actually uses $P(n-1)$ too, the basis must cover **two consecutive integers** (e.g. $P(1)$ and $P(2)$). Forgetting this is a classic lost-points error.
- **Strong induction:** assume $P(1), \dots, P(n)$ all hold, prove $P(n+1)$. Still needs a basis.

**Definition 1.1 (countable).** A set $S$ is *countable* if there is a bijection $f: S \to \mathbb{N}$; equivalently, an infinite $S$ is countable iff its elements can be listed $s_1, s_2, s_3, \dots$. $S$ is *uncountable* if it is infinite and not countable.

> Note: under this definition, "countable" means countably *infinite*. Finite sets are handled separately. Keep the convention straight when you write.

- [ ] Can I state all three definitions from memory, including the two-base-case trap?

Notes:

---

## 1.2 Important Theorems

The user's instruction to self: *all the theorems matter.* For each one: (a) state it from memory, (b) prove it on paper, (c) write one sentence on when you would reach for it.

### Theorem 1.1 (Useful Identities)
(a) $a^n - b^n = (a-b)(a^{n-1} + a^{n-2}b + \cdots + ab^{n-2} + b^{n-1})$

(b) If $n$ is **odd**, $a^n + b^n = (a+b)(a^{n-1} - a^{n-2}b + \cdots - ab^{n-2} + b^{n-1})$

(c) $x^3 + y^3 + z^3 - 3xyz = (x+y+z)(x^2+y^2+z^2 - xy - yz - zx)$

(d) $x^2+y^2+z^2 - xy - yz - zx = \tfrac12\big((x-y)^2 + (y-z)^2 + (z-x)^2\big)$

(e) $x^4 + 4y^4 = (x^2 + 2y^2 + 2xy)(x^2 + 2y^2 - 2xy)$  *(Sophie Germain identity)*

When to reach for them: (a) divisibility of $a^n - b^n$ by $a - b$, telescoping, geometric sums. (b) $a^n + b^n$ divisible by $a+b$ for odd $n$; primality of $2^n + 1$ type numbers. (c)+(d) together give: $x^3+y^3+z^3 = 3xyz \iff x+y+z = 0$ or $x = y = z$ (for reals). (e) factoring $n^4 + 4$, $n^4 + 4m^4$ — shows such numbers are composite.

- [ ] Verified each by expanding
- [ ] Memorized (a)–(e)

### Theorem 1.2
$\mathbb{N}, \mathbb{Z}, \mathbb{Q}$ are countable; $\mathbb{R}$ is uncountable.

Proof sketch to reproduce: list $\mathbb{Z}$ as $0, 1, -1, 2, -2, \dots$. For $\mathbb{Q}$, inject $\mathbb{Q} \hookrightarrow \mathbb{Z} \times \mathbb{N}$ via $p/q$ in lowest terms, then use Theorem 1.3(b). For $\mathbb{R}$: diagonal argument on decimal expansions of $[0,1]$ (handle the $0.4999\ldots = 0.5$ ambiguity by never choosing digits 0 or 9).

- [ ] Proved all four
- [ ] Handled the $0.999\ldots$ issue in the $\mathbb{R}$ proof

### Theorem 1.3
Let $A_1, A_2, A_3, \dots$ be countable sets. Then
(a) $\bigcup_{n=1}^{\infty} A_n$ is countable;
(b) $A_1 \times A_2 \times \cdots \times A_n$ is countable (finite product).

Proof sketch: (a) list $A_i = \{a_{i1}, a_{i2}, \dots\}$ and walk the grid $(i,j)$ along anti-diagonals, or inject $a_{ij} \mapsto 2^i 3^j$. (b) $\mathbb{N} \times \mathbb{N}$ is countable (same trick), then induct on $n$.

- [ ] Proved (a) and (b)

### Theorem 1.4
Let $A_1, A_2, \dots$ be sets with $|A_i| \ge 2$ for all $i$. Then the infinite product $A_1 \times A_2 \times A_3 \times \cdots$ (all sequences $(a_1, a_2, \dots)$ with $a_i \in A_i$) is **uncountable**.

Proof (Cantor's diagonal argument — the guide gives this one in full): suppose the product is countable and list its elements $s_i = (a_{i1}, a_{i2}, \dots)$. For each $i$ pick $b_i \in A_i$ with $b_i \ne a_{ii}$ (possible since $|A_i| \ge 2$). Then $b = (b_1, b_2, \dots)$ differs from every $s_i$ in coordinate $i$, so $b$ is not listed. Contradiction.

```
s1 : a11 a12 a13 a14 ...
s2 : a21 a22 a23 a24 ...
s3 : a31 a32 a33 a34 ...
          \ diagonal
```

Corollary to keep in your pocket: $\{0,1\}^{\mathbb{N}}$ is uncountable, hence $\mathcal{P}(\mathbb{N})$ is uncountable.

- [ ] Reproduced the proof from a blank page
- [x] Wrote down why $|A_i| \ge 2$ is needed (2026-10-17: so "the opposite" always exists)

### Theorem 1.5
If $X$ is countable, then the set of all **finite** subsets of $X$ is countable.

Proof sketch (the guide only has a video): let $F_n$ = set of $n$-element subsets of $X$. $F_n$ injects into $X^n$, which is countable by Theorem 1.3(b). Then $\bigcup_n F_n$ is countable by Theorem 1.3(a). Contrast with Example 1.1: *all* subsets is uncountable; *finite* subsets is countable.

- [ ] Proved it
- [ ] Can explain in one sentence why finite vs. all subsets differ

Notes on §1.2:

---

## 1.3 Classical Examples

These are "expected knowledge" — a Putnam problem may assume you've seen them. For each: attempt cold → read → re-derive 2+ days later.

### Example 1.1 — $\mathcal{P}(X)$ uncountable for infinite $X$
**Statement.** If $X$ is infinite, the power set $\mathcal{P}(X)$ is uncountable.
**Technique.** Contradiction + diagonal-style self-reference.
**Key idea.** Show no $f: X \to \mathcal{P}(X)$ is onto. Let $S = \{x \in X : x \notin f(x)\}$. If $f(a) = S$, then $a \in S \iff a \notin S$.
**Write-up lesson.** The Scratch shows how the definition of $S$ is *reverse-engineered* from "both $a \in S$ and $a \notin S$ must contradict." That reverse-engineering is the skill.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.2 — Base-$k$ representation exists and is unique
**Statement.** For integer $k \ge 2$, every positive integer $n$ has a unique representation $n = a_0 + a_1 k + \cdots + a_r k^r$, $a_j \in \{0, \dots, k-1\}$, $a_r \neq 0$.
**Technique.** Strong induction on $n$; existence and uniqueness proved separately.
**Key idea.** $a_0 = n \bmod k$; apply hypothesis to the quotient $q = (n - a_0)/k < n$. Uniqueness: reduce both representations mod $k$ to force $a_0 = b_0$, divide, apply hypothesis.
**Write-up lesson.** Note the basis case is "$n < k$", not "$n = 1$". Choose the basis to match what the inductive step actually needs.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.3 — Infinitely many primes; infinitely many primes $\equiv 3 \pmod 4$
**Statement.** (a) There are infinitely many primes. (b) There are infinitely many primes of the form $4k - 1$.
**Technique.** Contradiction ("to prove infiniteness, assume finiteness").
**Key idea.** (a) $p_1 \cdots p_n + 1$ has a prime factor not in the list. (b) $d = 4p_1 \cdots p_n - 1$ is odd, $\equiv -1 \pmod{p_i}$ for each listed $p_i$, and $\equiv 3 \pmod 4$; if all its prime factors were $\equiv 1 \pmod 4$ then $d \equiv 1 \pmod 4$. Contradiction.
**Watch.** Why does the same trick *fail* for primes $\equiv 1 \pmod 4$? (A product of numbers $\equiv 3$ can be $\equiv 1$.) Be able to say this.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.4 — Formulas for $\sum j, \sum j^2, \sum j^3$
**Statement.** Find closed forms for $\sum_{j=1}^n j$, $\sum_{j=1}^n j^2$, $\sum_{j=1}^n j^3$.
**Technique.** Telescoping: $\sum_{j=1}^n \big((j+1)^m - j^m\big) = (n+1)^m - 1$.
**Results.** $S_1 = \frac{n(n+1)}{2}$, $S_2 = \frac{n(n+1)(2n+1)}{6}$, $S_3 = \left(\frac{n(n+1)}{2}\right)^2$.
**Key idea.** Expand $(j+1)^{m+1} - j^{m+1}$ by the binomial theorem; the sum of the left side telescopes, the right side is a combination of $S_m, S_{m-1}, \dots$ you already know. This generalizes to any power.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.5 — $e$ is irrational
**Statement.** Prove $e$ is irrational.
**Technique.** Contradiction + "an integer strictly between 0 and 1".
**Key idea.** Suppose $e = a/b$. Multiply $e = \sum 1/k!$ by $b!$. The terms $k \le b$ are integers, so the tail $\sum_{k > b} b!/k!$ must be an integer. But $0 < \text{tail} < \frac{1}{b+1} + \frac{1}{(b+1)^2} + \cdots = \frac1b \le 1$.
**Write-up lesson.** The bound on the tail must be *strict* on both sides and you must say why $b!/k!$ is an integer for $k \le b$. Graders look for exactly those two sentences.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

Notes on §1.3:

---

## 1.4 Further Examples (actual competition problems)

### Example 1.6 — $a+b+c \mid abc \Rightarrow a+b+c$ composite
**Statement.** $a, b, c$ positive integers with $a + b + c \mid abc$. Prove $a + b + c$ is composite.
**Technique.** Contradiction.
**Key idea.** If $a+b+c$ were prime it would divide one of $a, b, c$, but $a+b+c > a, b, c > 0$.
**Write-up lesson.** Note the solution explicitly rules out $a+b+c = 1$ ("since it is more than 1, it must be prime"). Don't skip the edge case.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.7 — Putnam 1996 A4 (cyclic triples ⇒ linear order)
**Statement.** $S$ a set of ordered triples of distinct elements of finite $A$ with (1) $(a,b,c) \in S \iff (b,c,a) \in S$; (2) $(a,b,c) \in S \iff (c,b,a) \notin S$; (3) $(a,b,c),(c,d,a) \in S \iff (b,c,d),(d,a,b) \in S$. Prove there is an injective $g: A \to \mathbb{R}$ with $g(a) < g(b) < g(c) \Rightarrow (a,b,c) \in S$.
**Technique.** Two solutions: (i) induction on $|A|$ (insert a new element into an existing order, messy case analysis); (ii) **fix $a_0$ and define a total order** $x \preceq y \iff (a_0, x, y) \in S$, verify reflexive/antisymmetric/transitive/comparable, then $g(x_i) = i$.
**Key idea.** Condition (1)+(2) say: of the 6 orderings of $\{a,b,c\}$, exactly the 3 cyclic rotations of one of them are in $S$ — so $S$ picks an "orientation" of every triple. Condition (3) is transitivity in disguise.
**Lesson.** The guide says the second solution is "simpler but harder to find". When your induction is turning into a 5-case mess, stop and look for the structural object (here: an order relation).
- [ ] cold ___ min · status ___ · [ ] read both · [ ] re-derived solution (ii) (date: ___ )

### Example 1.8 — VTRMC 2017: $\sqrt{2 - x^2} = \sqrt[3]{3 - x^3}$
**Statement.** Determine the number of real solutions.
**Answer.** None.
**Technique.** Contradiction via a system: set $y$ equal to both sides, get $x^2 + y^2 = 2,\ x^3 + y^3 = 3$.
**Key idea.** From $x^2 + y^2 = 2$, $x, y \le \sqrt2$, so $x^3 \le \sqrt2 x^2$ and $y^3 \le \sqrt2 y^2$; add: $3 \le 2\sqrt2 < 3$.
**Watch.** The inequality $x^3 \le \sqrt2 x^2$ holds for negative $x$ too (LHS $\le 0 \le$ RHS). Say so in the write-up.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.9 — Sequence mod 10, invariant
**Statement.** Sequence $1,0,1,0,1,0,\dots$, each later term = sum of previous 6 mod 10. Prove $0,1,0,1,0,1$ never appears.
**Technique.** **Invariant.** Specifically a *linear* invariant found by solving for coefficients.
**Key idea.** Look for $I(y_1,\dots,y_6) = \sum a_i y_i$ with $I(y_1,\dots,y_6) = I(y_2,\dots,y_6, y_1 + \cdots + y_6)$. Matching coefficients forces $a_1 = a_6$, $a_2 = 2a_6$, $a_3 = 3a_6$, $a_4 = 4a_6$, $a_5 = 5a_6$, $a_6 = a_5 + a_6 \Rightarrow a_5 = 0$. So this only works **mod 5**: $I = y_1 + 2y_2 + 3y_3 + 4y_4 + y_6 \pmod 5$. Then $I(1,0,1,0,1,0) = 4 \not\equiv 2 = I(0,1,0,1,0,1) \pmod 5$.
**Lesson.** The Scratch is a model of honest problem solving: pattern-hunting fails, mod 2 / mod 5 splitting half-fails, alternating sum fails, *then* the systematic linear-invariant ansatz works. Keep a list of failed ideas — it's how you find the right one.
**Write-up to produce yourself** (guide only has video): define $I_n = x_n + 2x_{n+1} + 3x_{n+2} + 4x_{n+3} + x_{n+5} \bmod 5$, show $I_{n+1} \equiv I_n$, note $I_1 = 4$ while the forbidden block would give $2$.
- [ ] cold ___ min · status ___ · [ ] read · [ ] wrote full solution · [ ] re-derived (date: ___ )

### Example 1.10 — IMO 2021 Shortlist A1 ($4n+2$ numbers in $\{0,\dots,5^n\}$)
**Statement.** $A \subseteq \{0, 1, \dots, 5^n\}$ with $|A| = 4n + 2$. Prove there exist $a < b < c$ in $A$ with $c + 2a > 3b$.
**Technique.** Induction on $n$ + contradiction inside the inductive step.
**Key idea.** Rewrite as $c - b > 2(b - a)$: only *gaps* matter, so the interval can be translated. Assume failure: every triple satisfies $x_j - x_i \ge \frac{x_k - x_j}{2}$. Either the top $4n+2$ elements fit in a window of length $5^n$ (apply hypothesis) or $x_{4n+6} - x_5 > 5^n$ and the gaps below grow geometrically: $> 5^n/2,\ 3\cdot5^n/4,\ 9\cdot5^n/8,\ 27\cdot5^n/16$, total $> 5^n \cdot 81/16 > 5^{n+1}$.
**Lesson.** The author first tried building inequalities from the *bottom* and got nothing; starting from the *top* worked. When one direction gives junk, try the other.
- [ ] cold ___ min · status ___ · [ ] read · [ ] re-derived (date: ___ )

### Example 1.11 — Putnam 1989 B4 (uncountable almost-disjoint family)
**Statement.** Does there exist an uncountable collection of subsets of $\mathbb{N}$ such that any two distinct members have finite intersection?
**Answer.** Yes. *(Guide has video only; sketch below is mine — verify it.)*
**Key idea.** For each real $r \in [1,2)$ let $A_r = \{\lfloor 10^k r \rfloor : k \ge 1\}$ (the integers whose digits are the successive truncations of $r$). Distinct $r \ne r'$ agree on only finitely many initial digit strings, so $A_r \cap A_{r'}$ is finite. Uncountably many $r$. (Alternative: paths in the infinite binary tree, nodes labeled by positive integers.)
**Why it's here.** Uses Theorem 1.2 (uncountability of $\mathbb{R}$) as a *tool* rather than a destination.
- [ ] cold ___ min · status ___ · [ ] wrote full solution · [ ] re-derived (date: ___ )

### Example 1.12 — IMO 1961 P3: $\cos^n x - \sin^n x = 1$
**Statement.** Find all positive integers $n$ and reals $x$ with $\cos^n x - \sin^n x = 1$.
*(Guide has video only; sketch below is mine — verify it.)*
**Key idea.** $\cos^n x - \sin^n x \le |\cos x|^n + |\sin x|^n \le \cos^2 x + \sin^2 x = 1$ for $n \ge 2$, with equality forcing $|\cos x|, |\sin x| \in \{0, 1\}$ and the signs to cooperate. Then split: $n$ even $\Rightarrow$ $\sin x = 0$, i.e. $x = k\pi$; $n$ odd $\Rightarrow$ $(\cos x, \sin x) \in \{(1, 0), (0, -1)\}$, i.e. $x = 2k\pi$ or $x = -\pi/2 + 2k\pi$. Check $n = 1$ separately (same answer as odd case).
**Lesson.** "Prove the expression is $\le 1$, then analyze the equality case" — a pattern you'll reuse constantly in inequalities.
- [ ] cold ___ min · status ___ · [ ] wrote full solution · [ ] re-derived (date: ___ )

### Example 1.13 — VTRMC 2012: $3x - x^3 = \sqrt{x+2}$
**Statement.** Solve over the reals.
*(Guide has video only; sketch below is mine — verify it.)*
**Key idea.** Domain: $x \ge -2$; for $x > 2$ the LHS is negative, so $x \in [-2, 2]$. Substitute $x = 2\cos\theta$, $\theta \in [0, \pi]$: LHS $= -2\cos 3\theta$, RHS $= \sqrt{2 + 2\cos\theta} = 2\cos(\theta/2)$. So $\cos(\theta/2) = \cos(\pi - 3\theta)$, giving $\theta \in \{2\pi/7,\ 6\pi/7,\ 2\pi/5\}$ and $x = 2\cos\frac{2\pi}{7},\ 2\cos\frac{6\pi}{7},\ 2\cos\frac{2\pi}{5}$. (Sanity: $2\cos\frac{2\pi}{5} = \frac{\sqrt5 - 1}{2} \approx 0.618$; LHS $\approx 1.618$, RHS $= \sqrt{2.618} \approx 1.618$ ✓.)
**Lesson.** $x^3 - 3x$ and $\sqrt{2 + x}$ both scream $x = 2\cos\theta$ (triple-angle and half-angle). File the substitution.
- [ ] cold ___ min · status ___ · [ ] wrote full solution · [ ] re-derived (date: ___ )

Notes on §1.4:

---

## 1.5 General Strategies — the checklist

Copy this out by hand once. Then tape it where you work problems.

**Solving**
- [ ] Competition problems are solvable. Somebody knows the answer. Stay hopeful.
- [ ] Know your strengths; pick problems accordingly (the author would take a number theory 6 over an analysis 5).
- [ ] **Try small cases.** "The simplest and most under-appreciated approach."
- [ ] Read *all* problems first. Order ≈ difficulty, but it's subjective: skipping 2 for 3 is fine; skipping to 6 without 1–3 is not.
- [ ] One problem at a time, but budget time. Don't sink the whole session into one.

**Writing (during a competition)**
- [ ] **Do NOT bury the lead.** Final claim/answer in the first line.
- [ ] Reflect before writing. **Did I use every hypothesis?** An unused hypothesis almost always means a mistake.
- [ ] If the write-up is messy, spend a few minutes restructuring *before* writing.
- [ ] **Never write a claim you know is false.** One false statement and a grader stops reading. Partial credit is rare.

**Which proof method?**
- Reduces to smaller cases → induction.
- Recursive sequences → induction.
- Proving a negative / non-existence / infiniteness → contradiction (assume existence / finiteness).

**My own additions (fill in as I learn what I get wrong):**
-

---

## 1.6 Exercises (52)

**Tiering (my rough triage, not the author's):**
- **Tier 1** — A1/B1-level or quick VTRMC. Do all of these first; these are the problems that get you to 30 points.
- **Tier 2** — A2/B2-level, meatier VTRMC. The bread and butter.
- **Tier 3** — A4+/B5+/A6. Attempt for 45 min max, then read a solution and log the idea. Don't let these eat the week.

Fill in: **Date · Min · Status (S/H/R/X) · Write-up OK? · Notes/technique.**

### Tier 1
| # | Source | Problem (short) | Date | Min | Status | Write-up OK? | Notes |
|---|--------|-----------------|------|-----|--------|--------------|-------|
| 1.1 | — | $f_1 = \frac{2x-1}{x+1}$, $f_{n+1} = f_1 \circ f_n$; find $f_{1000}$ as $\frac{Ax+B}{Cx+D}$ | | | | | |
| 1.7 | VTRMC 1982 | Marbles: blue $\ge \frac12$ white, $\le \frac13$ red, white+blue $\ge 55$; min red | | | | | |
| 1.9 | VTRMC 1986 | $\sinh 3x$ as a polynomial in $\sinh x$ | | | | | |
| 1.11 | VTRMC 1989 | Three farmers, 10/16/26 chickens, each gets \$35; the two prices | | | | | |
| 1.12 | VTRMC 1990 | Pasture fields 10/3, 10, 24 acres; cows for 18 weeks | | | | | |
| 1.13 | VTRMC 1990 | Jigsaw: $3\frac{1000-x}{1000+x}$ min per piece; total time (use $\ln 2 \approx .69$) | | | | | |
| 1.14 | Putnam 1993 A1 | $y = c$ meets $y = 2x - 3x^3$; equal shaded areas; find $c$ | | | | | |
| 1.22 | Putnam 1998 A2 | Arc of unit circle in Q1; $A + B$ depends only on arc length | | | | | |
| 1.26 | VTRMC 2002 | $\sqrt{7 + \sqrt{40}} = a + b\sqrt2 + c\sqrt5 + d\sqrt7 + e\sqrt{10}$ | | | | | |
| 1.27 | Putnam 2002 A2 | Five points on a sphere; four lie on a closed hemisphere | | | | | |
| 1.33 | Putnam 2005 A1 | Every $n$ is a sum of $2^r 3^s$ with no summand dividing another | | | | | |
| 1.36 | Putnam 2009 A1 | $f(A)+f(B)+f(C)+f(D) = 0$ for every square; is $f \equiv 0$? | | | | | |
| 1.38 | Putnam 2009 B1 | Every positive rational = quotient of products of prime factorials | | | | | |
| 1.41 | Putnam 2012 A1 | $d_1, \dots, d_{12} \in (1, 12)$; three form an acute triangle | | | | | |
| 1.46 | Putnam 2014 B1 | Base-10 over-expansions (digits 0–10); which $N$ have a unique one? | | | | | |
| 1.49 | Putnam 2017 A1 | Smallest $S$: $2 \in S$, $n^2 \in S \Rightarrow n \in S$, $n \in S \Rightarrow (n+5)^2 \in S$; which integers are *not* in $S$? | | | | | |
| 1.50 | VTRMC 2019 | $S \subseteq \mathbb{R}$ with every point isolated; injective $f: S \to \mathbb{N}$ | | | | | |

### Tier 2
| # | Source | Problem (short) | Date | Min | Status | Write-up OK? | Notes |
|---|--------|-----------------|------|-----|--------|--------------|-------|
| 1.2 | VTRMC 1980 mod. | Partial order on $\{(m,n): m > 0, n < 0\}$; chains finite? bounded? collection countable? | | | | | |
| 1.3 | — | $a < b$ reals; find $n \in \mathbb{Z}$, prime $p$ with $a < n/p < b$ | | | | | |
| 1.4 | — | No uncountable family of disjoint X's in the plane; but possible for O's | | | | | |
| 1.5 | — | Mixed-radix representation: $g_0 = 1$, $g_{i-1} \mid g_i$, $n = \sum a_i g_i$ unique | | | | | |
| 1.6 | VTRMC 1982 | $E$ = even part, $C$ = complement; $ECECEA = EA$; max # distinct subsets | | | | | |
| 1.8 | VTRMC 1985 | Egyptian fractions: $3/5$ as distinct unit fractions; every positive rational | | | | | |
| 1.10 | VTRMC 1988 | $f(S) = S/3 \cup (S+2)/3$; sketch $f^3([0,1])$; can a bounded fixed set contain $1/2$? | | | | | |
| 1.17 | VTRMC 1995 | $\tau = \frac{1+\sqrt5}{2}$; $[\tau^2 n] = [\tau[\tau n] + 1]$ | | | | | |
| 1.18 | Putnam 1995 B5 | Bean heaps 3,4,5,6; take one bean (leaving $\ge 2$) or a whole heap of 2–3; first or second? | | | | | |
| 1.19 | VTRMC 1997 | Well-served city subsets; find a strongly connected well-served subset | | | | | |
| 1.20 | Putnam 1997 A2 | Penny passing 1, 2, 1, 2, …; infinite set of $n$ where one player gets all | | | | | |
| 1.21 | VTRMC 1998 | Ten cats, rules alternate (rotate / swap pairs with product $\equiv 1 \pmod{11}$); 900 jumps | | | | | |
| 1.23 | VTRMC 2000 | $\int_0^{\ell} \cos\theta(x)\,dx = \ell_2 - \ell_1$ in triangle $ABC$ | | | | | |
| 1.24 | VTRMC 2001 | Find $f: \mathbb{R}^+ \to \mathbb{R}^+$ with $f(f(x)) = \frac{3x+1}{x+3}$ | | | | | |
| 1.25 | Putnam 2001 B2 | $\frac1x + \frac1{2y} = (x^2+3y^2)(3x^2+y^2)$, $\frac1x - \frac1{2y} = 2(y^4 - x^4)$ | | | | | |
| 1.28 | Putnam 2002 B5 | An integer that is a 3-digit palindrome in $\ge 2002$ bases | | | | | |
| 1.29 | VTRMC 2003 | $2\cos^3\frac{\pi}{7} - \cos^2\frac{\pi}{7} - \cos\frac{\pi}{7}$ as $p/q$ | | | | | |
| 1.32 | VTRMC 2005 mod. | Permutation of $1..n$ with $j + a_j$ a power of 2 for all $j$ | | | | | |
| 1.34 | Putnam 2006 B1 | $x^3 + 3xy + y^3 = 1$ contains exactly one equilateral triangle; its area | | | | | |
| 1.35 | VTRMC 2009 | Walker 1 m/s, jogger 2 m/s, dog 3 m/s; $f(n)$ = dog distance at $n$-th return | | | | | |
| 1.37 | Putnam 2009 A4 | $S \ni 0$, closed under $\pm1$ and $x \mapsto \frac{1}{x(x-1)}$; is $S = \mathbb{Q}$? | | | | | |
| 1.39 | VTRMC 2011 | Extend an asymmetric relation to a dense one | | | | | |
| 1.40 | Putnam 2011 B1 | $\varepsilon < \lvert h\sqrt m - k\sqrt n \rvert < 2\varepsilon$ | | | | | |
| 1.43 | — | $(1 + x + x^2)^n$ has an even coefficient for $n \ge 2$ | | | | | |
| 1.44 | Putnam 2013 A2 | $f(n)$ = min top factor making $n \cdot a_1 \cdots a_r$ a square; $f$ injective | | | | | |
| 1.45 | Putnam 2013 B3 | Lattice of subsets, modular $f$; must $f(S) = \sum_{i \in S} f_i$? | | | | | |
| 1.48 | VTRMC 2017 | AM, GM, HM of $(a,b)$ all integers, $a \ne b$; minimize AM | | | | | |
| 1.51 | — | No four consecutive binomial coefficients in arithmetic progression | | | | | |

### Tier 3
| # | Source | Problem (short) | Date | Min | Status | Write-up OK? | Notes |
|---|--------|-----------------|------|-----|--------|--------------|-------|
| 1.15 | Putnam 1993 B6 | Three positive integers; replace $x \le y$ by $2x, y - x$; reach a 0 | | | | | |
| 1.16 | Putnam 1994 B5 | $f_\alpha(x) = \lfloor \alpha x \rfloor$; find $\alpha$ with $f_\alpha^k(n^2) = n^2 - k$ | | | | | |
| 1.30 | Putnam 2002 A5 | $a_{2n+1} = a_n$, $a_{2n+2} = a_n + a_{n+1}$; $\{a_{n-1}/a_n\}$ = all positive rationals | | | | | |
| 1.31 | Putnam 2004 B6 | Difference set $B$ of $A$ has unbounded gaps $\Rightarrow N(x)/x \to 0$ | | | | | |
| 1.42 | Putnam 2012 A4 | $T = \{b + mq\}$, $S = \{a \in A : ra \in T\}$; $\lvert A \rvert \lvert B \rvert < q \Rightarrow S$ is an AP | | | | | |
| 1.47 | Putnam 2014 B5 | Game on $GL_n(\mathbb{Z}/p)$, choose commuting elements; who wins? | | | | | |
| 1.52 | Putnam 2022 A6 | Largest $m$: $2n$ points in $(-1,1)$ with $\sum$ of interval lengths of $x_i^{2k-1}$ equal to 1 for $k \le m$ | | | | | |

---

## Running log (chronological)

Append one line per session: date · what I did · minutes · what went wrong in the write-up.

| Date | Did | Min | Write-up lesson |
|------|-----|-----|-----------------|
| 2026-10-17 | Set up this log | — | — |
| 2026-10-17 | Session 1 lesson: 1.1 basics, countable/bijection defs, Theorems 1.2–1.4 (Cantor diagonal) understood, Theorem 1.5 started. See logs/2026-10-17.pdf | ~90 | Cantor took an hour; the 3-string "game" version is what landed. Lesson exercises + main problem carried over. |

---

## Chapter 1 exit criteria

Before moving to Chapter 2, all of these should be true:
- [ ] Can state and prove Theorems 1.1–1.5 from memory.
- [ ] Re-derived Examples 1.1–1.5 from a blank page at least two days after first reading them.
- [ ] Wrote full solutions (not sketches) to Examples 1.9, 1.11, 1.12, 1.13 (the ones the guide leaves to video).
- [ ] All Tier 1 exercises status S or H, with write-ups that pass the §1.5 checklist.
- [ ] At least 15 Tier 2 exercises attempted, with the technique logged for each.
- [ ] Every Tier 3 problem attempted for 45 min and the key idea logged after reading a solution.
- [ ] The "My own additions" list in §1.5 has at least three entries drawn from mistakes I actually made.
