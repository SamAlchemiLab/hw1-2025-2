---
description: 김한샘, 어주호
---

# HW1 2025-2

***

## Q0: Adam Smith needs revision

***

### (a) Normal-form model & identical payoff mapping

* Formalize players, strategy sets, and the outcome set using the static game theory notation from the lecture note.
* Encode the movie rules into a single identical payoff function $$u_i:S\to\mathbb R$$ that depends only on the action profile.
* Present a compact table that summarizes payoffs by the number of players who go for the blonde.

***

#### Players and strategy sets (normal form)

Let the player set be $$N=\{1,2,3,4,5\}$$. Each player $$i\in N$$ simultaneously chooses one of two pure actions:

$$
S_i=\{B,\;R\}\quad\text{with}\quad B=\text{“go for the blonde”},\;\;R=\text{“go for a brunette”}.
$$

So the action profile is

$$
s=(s_1,\dots,s_5)\in S\equiv\prod_{i\in N}S_i=\{B,R\}^5
$$

####

####

#### Count statistic for convinience

Define the count of “blonde” attempts at profile $$s$$ by

$$
n_B(s)\;\equiv\;\#\{i\in N:\;s_i=B\}.
$$

This statistic lets us write payoffs compactly and identically across players.

#### Payoff primitives and movie-implied rules

Normalize match values as,

$$
Blonde = 2 ,  Brunette = 1 ,  No match = 0 .
$$

Then encode the three rules the clip implies:

1. If **exactly one** player chooses $$B$$ $$(n_B=1)$$: that unique player is matched to the blonde (value $$2$$), all others choosing $$R$$ get a brunette (value $$1$$).
2. If **two or more** choose $$B$$ $$(n_B\ge 2)$$: they block one another at the blonde (value $$0$$ for all $$B$$-choosers); each $$R$$-chooser still gets a brunette (value $$1$$).
3. If **nobody** chooses $$B$$ $$(n_B=0)$$: by symmetry one player is (ex-ante) redirected to the blonde and the remaining four match with brunettes, so each player’s expected payoff is&#x20;

$$
5\tfrac{1}{5}\cdot 2+\tfrac{4}{5}\cdot 1=\tfrac{6}{5}
$$

####

####

####

#### Identical payoff function

Putting the cases together, for any player $$i\in N$$ and any profile $$s\in S$$,

$$
u_i(s)= \begin{cases} 2, & \text{if }n_B(s)=1\text{ and }s_i=B,\\[2pt] 1, & \text{if }n_B(s)=1\text{ and }s_i=R,\\[2pt] 0, & \text{if }n_B(s)\ge 2\text{ and }s_i=B,\\[2pt] 1, & \text{if }n_B(s)\ge 2\text{ and }s_i=R,\\[2pt] \tfrac{6}{5}, & \text{if }n_B(s)=0\;\;\text{(all play }R\text{; symmetric reassignment).} \end{cases}
$$

***

#### Answer

* Players: $$N=\{1,2,3,4,5\}$$.
* Strategies: $$S_i=\{B,R\}$$ for each $$i$$.
* Outcomes: $$S=\{B,R\}^5$$ (normal form).
* Identical payoff function $$u_i:S\to\mathbb R$$ as defined above, parameterized by $$n_B(s)$$ and consistent with the blonde/brunette rules and a symmetric, ex-ante reassignment when $$n_B=0$$.

***

### (b) Pure-strategy Nash equilibria

* Reduce the 5-player game to layered 2×2 matrices (Player 1 as rows, Player 2 as columns; players 3–5 fixed per layer).
* Use the identical payoff rule from (a): Blonde $$=2$$, Brunette $$=1$$, No-match $$=0$$; when all five choose $$R$$, each gets $$6/5$$. We denote $$n_B(s):=\#\{i: s_i=B\}$$.
* PSNE definition (static normal form): $$s$$ is a PSNE iff $$s_i\in BR_i(s_{-i})$$ for every $$i$$.

***

#### Step 1. Best-response matrix

For any player $$i$$, let $$m\in\{0,1,2,3,4\}$$ be the number of other players choosing $$B$$. Payoffs to $$i$$:

$$
\begin{array}{c|ccccc} \text{Action of }i & m=0 & 1 & 2 & 3 & 4\\\hline B & 2 & 0 & 0 & 0 & 0\\ R & \tfrac{6}{5} & 1 & 1 & 1 & 1 \end{array}
$$

If $$m=0\Rightarrow B$$ is strictly better; if $$m\ge1\Rightarrow R$$ is strictly better. We will now embed this in 2×2 payoff matrices for Players 1–2 while fixing $$(s_3,s_4,s_5)$$ (“a layer”).

#### Step 2. Layered 2×2 matrices (Players 1–2 shown; Players 3–5 fixed)

We write each 2×2 with entries $$(u_1,u_2)$$, suppressing $$(u_3,u_4,u_5)$$ to save space; the latter follow the same rule as in (a). Stars ($$⋆$$) mean mutual best responses in the full 5-player game (i.e., a PSNE).

**(i) Layers with** $$k:=\#\{j\in\{3,4,5\}: s_j=B\}=0$$ **(layer** $$RRR$$**)**

$$
\begin{array}{c|cc} & \text{P2: }B & \text{P2: }R\\\hline \text{P1: }B & (0,0) & (2,1)\star\\ \text{P1: }R & (1,2)\star & \bigl(\tfrac{6}{5},\tfrac{6}{5}\bigr) \end{array}
$$

* Off-diagonal cells are mutual best responses ⇒ two PSNE in this layer:\
  $$(B,R,R,R,R)$$ and $$(R,B,R,R,R)$$.

**(ii) Layers with** $$k=1$$ **(one among players 3–5 plays** $$B$$**; e.g.,** $$BRR,\ RBR,\ RRB$$**)**

$$
\begin{array}{c|cc} & \text{P2: }B & \text{P2: }R\\\hline \text{P1: }B & (0,0) & (0,1)\\ \text{P1: }R & (1,0) & (1,1)\star\ , \end{array}
$$

* Here both players strictly prefer $$R$$ regardless of the other (since $$m\ge1$$).
* The unique cell that sustains everyone’s best responses (including players 3–5) is $$(R,R)$$, yielding exactly one $$B$$ overall—namely the single $$B$$ among players 3–5—so we get one PSNE per such layer:\
  $$BRR\Rightarrow (R,R,\mathbf{B},R,R)$$, $$RBR\Rightarrow (R,R,R,\mathbf{B},R)$$, $$RRB\Rightarrow (R,R,R,R,\mathbf{B})$$.

**(iii) Layers with** $$k\ge2$$ **(e.g.,** $$BBR, BRB, RBB, BBB$$**)**

$$
\begin{array}{c|cc} & \text{P2: }B & \text{P2: }R\\\hline \text{P1: }B & (0,0) & (0,1)\\ \text{P1: }R & (1,0) & (1,1) \end{array}
$$

* Players 1–2 would again pick $$R$$. However, some of players 3–5 are playing $$B$$ while $$n_B\ge2$$, so those $$B$$-players earn $$0$$ and can profitably deviate to $$R$$ (to get $$1$$). Hence no 5-player PSNE exists in any $$k\ge2$$ layer.

#### Step 3. Eight-layer summary

<table><thead><tr><th width="93.1070556640625">Layer</th><th width="75.55670166015625">K</th><th width="301.7406005859375">PSNE in the 5-player game</th><th></th></tr></thead><tbody><tr><td><span class="math">RRR</span></td><td>0</td><td><span class="math">(\mathbf{B},R,R,R,R), (R,\mathbf{B},R,R,R)</span></td><td></td></tr><tr><td><span class="math">RRB</span></td><td>1</td><td><span class="math">(R,R,R,R,\mathbf{B})</span></td><td></td></tr><tr><td><span class="math">RBR</span></td><td>1</td><td><span class="math">(R,R,R,\mathbf{B},R)</span></td><td></td></tr><tr><td><span class="math">BRR</span></td><td>1</td><td><span class="math">(R,R,\mathbf{B},R,R)</span></td><td></td></tr><tr><td><span class="math">RBB</span></td><td>2</td><td>none</td><td></td></tr><tr><td><span class="math">BRB</span></td><td>2</td><td>none</td><td></td></tr><tr><td><span class="math">BBR</span></td><td>2</td><td>none</td><td></td></tr><tr><td><span class="math">BBB</span></td><td>3</td><td>none</td><td></td></tr></tbody></table>

***

#### Answer

All and only the profiles with **exactly one** $$B$$ are PSNE:

$$
(B,R,R,R,R),\ (R,B,R,R,R),\ (R,R,B,R,R),
$$

$$
\ (R,R,R,B,R),\ (R,R,R,R,B).
$$

The payoff-matrix case analysis above shows: $$k=0$$ contributes two PSNE (Players 1 or 2 as the unique $$B$$); each $$k=1$$ layer contributes one PSNE (Player 3, 4, or 5 as the unique $$B$$); no PSNE exist when $$k\ge2$$.

***

### (c) Symmetric mixed-strategy Nash equilibrium

* Define a symmetric mixed strategy σi\sigma\_iσi​ where every player independently chooses $$B$$ with probability $$p$$ and $$R$$ with probability $$1-p$$; specify the distribution of “others choosing $$B$$”.
* Compute the expected payoff of each pure action against the common mix using the law of total expectation.
* Impose indifference to solve for $$p^\star$$⋆.
* Report the equilibrium payoff $$U^\star$$, and characterize best-responses $$BR(p)$$ via the payoff difference $$\Delta(p)$$.

***

#### Symmetric mixing and the distribution of others

Let each of the other four players choose $$B$$ with probability $$p$$ independently. Then the number of other $$B$$-choosers

$$
m\sim \mathrm{Binomial}(4,p),\qquad \Pr[m=k]=\binom{4}{k}p^k(1-p)^{4-k}.
$$

#### Expected payoff from choosing B

If player $$i$$ plays $$B$$, he obtains the blonde (utility $$2$$) iff no one else chooses $$B$$ (i.e., $$m=0$$); otherwise his payoff is $$0$$. Hence

$$
U(B\mid p)=2\cdot \Pr[m=0]=2(1-p)^4.
$$

#### Expected payoff from choosing R

If player $$i$$ plays $$R$$, two cases matter:

* When $$m=0$$ (i.e., all five choose $$R$$), symmetry implies a fair reassignment: one player is (ex-ante) redirected to the blonde and four to brunettes, so each player’s payoff is $$6/5$$.
* When $$m\ge 1$$, at least one player goes for the blonde; all $$R$$-choosers are accepted by brunettes and receive payoff $$1$$.

By the law of total expectation,

$$
\begin{aligned} U(R\mid p) &=\tfrac{6}{5}\Pr[m=0] + 1\cdot \Pr[m\ge 1] \\ &=\tfrac{6}{5}(1-p)^4 + \bigl[1-(1-p)^4\bigr] = 1+\tfrac{1}{5}(1-p)^4. \end{aligned}
$$

#### Indifference condition and the mixing probability p⋆

A player mixes only if indifferent between $$B$$ and $$R$$ against the common mix. Set $$U(B\mid p)=U(R\mid p)$$:

$$
2(1-p)^4 = 1 + \tfrac{1}{5}(1-p)^4 \ \Longrightarrow\ \tfrac{9}{5}(1-p)^4=1 \ \Longrightarrow\ (1-p)^4=\tfrac{5}{9}.
$$

Thus the symmetric mixed-strategy NE is

$$
\boxed{\,p^\star = 1-\Bigl(\tfrac{5}{9}\Bigr)^{1/4}\,} \approx 0.13666.
$$

#### Equilibrium payoff and best-response shape

Evaluating at $$p^\star$$,

$$
U^\star = U(B\mid p^\star)=2(1-p^\star)^4 = 2\cdot \tfrac{5}{9}=\boxed{\tfrac{10}{9}\approx 1.111\ldots}.
$$

Define the payoff difference

$$
\Delta(p):=U(B\mid p)-U(R\mid p)=\tfrac{9}{5}(1-p)^4-1.
$$

Since $$(1-p)^4$$ is strictly decreasing in $$p$$, $$\Delta(p)$$ is strictly decreasing, giving a unique crossing at $$p^\star$$. Hence

$$
BR(p)= \begin{cases} \{B\}, & p<p^\star,\\ [0,1], & p=p^\star,\\ \{R\}, & p>p^\star, \end{cases}
$$

confirming uniqueness of the symmetric MSNE.

***

#### Answer

$$
\boxed{\,p^\star = 1-\Bigl(\tfrac{5}{9}\Bigr)^{1/4} \approx 0.13666,\qquad U^\star=\tfrac{10}{9}\, .}
$$

In conclusion, every player adopts the same mixed strategy: choose $$B$$ with probability $$p^\star=1-(5/9)^{1/4}\approx 0.13666$$ and choose $$R$$ with probability $$1-p^\star\approx 0.86334$$, independently across players. At this mix, a player’s expected payoff from either pure action is equal—$$U(B\mid p^\star)=U(R\mid p^\star)=10/9$$—so no unilateral deviation is profitable. Intuitively, players mostly go for a brunette while occasionally trying for the blonde just enough to eliminate any gain from switching; raising $$p$$ would create too many clashes at the blonde (driving the $$B$$-payoff to $$0$$), while lowering $$p$$ would leave a profitable incentive to switch to $$B$$. Thus this symmetric mixed strategy is the unique equilibrium.

***

***

## Q1: strategic complements/substitutes and the advantage of first/second mover’s

***

### (a) Cournot normal form

* Write the simultaneous‐move quantity game in normal form.
* Derive each firm’s best-response (reaction) function and show strategic substitutability.
* Solve for the symmetric Cournot–Nash equilibrium $$(q_1^C,q_2^C)$$, then compute $$p^C$$ and $$\pi_i^C$$​.
* Compute the efficient quantity $$Q^\ast$$, associated price $$p^\ast$$, and a symmetric split.
* Explain why Cournot differs from the efficient benchmark.

***

#### Normal-form representation

There are two firms $$i\in\{1,2\}$$ that choose quantities simultaneously. The inverse demand is

$$
p(Q)=8 - q_1 - q_2,\qquad Q=q_1+q_2,
$$

and marginal cost is $$c=1$$. Strategy sets are $$S_i=\{q_i\ge 0\}$$. Firm $$i$$’s payoff is profit

$$
\pi_i(q_1,q_2) \;=\; (p(Q)-c)\,q_i \;=\; (7 - q_1 - q_2)\,q_i .
$$

In a simultaneous game, a Nash equilibrium is a profile where each player’s action is a best response to the other’s action. We’ll obtain it by intersecting the two best-response functions.

#### Best-response functions and strategic substitutability

Fix $$q_2$$​. Firm 1 solves $$\max_{q_1\ge 0}\,(7-q_1-q_2)q_1$$​. The FOC and SOC are

$$
\frac{\partial \pi_1}{\partial q_1}=7-2q_1-q_2=0,\qquad \frac{\partial^2 \pi_1}{\partial q_1^2}=-2<0.
$$

Hence

$$
BR_1(q_2)=\max\!\left\{0,\;\frac{7-q_2}{2}\right\}.
$$

By symmetry,

$$
BR_2(q_1)=\max\!\left\{0,\;\frac{7-q_1}{2}\right\}.
$$

Both reaction curves are downward-sloping, so quantities are strategic substitutes: the more one firm produces, the less the other optimally produces.

####

#### Cournot–Nash equilibrium (quantities, price, profits)

At a Cournot equilibrium, each output must be a best response to the other:

$$
q_1=\frac{7-q_2}{2},\qquad q_2=\frac{7-q_1}{2} \;\Rightarrow\; q_1^C=q_2^C=\frac{7}{3},\quad Q^C=\frac{14}{3}.
$$

Then

$$
p^C=8-Q^C=\frac{10}{3},\qquad \pi_i^C=(p^C-1)\,q_i^C=\Big(\frac{10}{3}-1\Big)\frac{7}{3}=\frac{49}{9}\approx 5.444.
$$

#### Efficient allocation and comparison

Industry (joint) profit as a function of total output $$Q$$ is

$$
\Pi(Q)=(p(Q)-1)Q=(7-Q)Q=7Q-Q^2.
$$

FOC $$7-2Q=0$$ gives

$$
Q^\ast=\frac{7}{2},\qquad p^\ast=8-Q^\ast=\frac{9}{2}.
$$

Any split with $$q_1+q_2=Q^\ast$$ attains the same joint profit $$\Pi^\ast=(p^\ast-1)Q^\ast=\tfrac{49}{4}=12.25$$; a symmetric split is $$q_1^\ast=q_2^\ast=\tfrac{7}{4}$$​, delivering $$\pi_i^\ast=\tfrac{49}{8}=6.125$$ each.&#x20;

##

##

##

**Why the wedge?**&#x20;

In Cournot, each firm sets its own FOC $$7-2q_i-q_j=0$$ taking the rival’s output as given; summing the two FOCs yields $$14-3Q=0\Rightarrow Q^C=14/3>Q^\ast=7/2$$. Thus Cournot over-produces relative to the joint-profit benchmark, pushing price below $$p^\ast$$ and reducing total profit. The notes emphasize this business-stealing externality intuition: when a firm expands output, it lowers $$p$$ and imposes a negative externality on its rival’s profit, which it does not internalize.

***

#### Answer

$$
\boxed{ q_1^C=q_2^C=\frac{7}{3},\quad Q^C=\frac{14}{3},\quad p^C=\frac{10}{3},\quad \pi_i^C=\frac{49}{9}\ (\approx 5.444). }
$$

In the efficient (joint-profit-maximizing) benchmark,

$$
\boxed{ Q^\ast=\frac{7}{2},\quad p^\ast=\frac{9}{2},\quad \Pi^\ast=\frac{49}{4};}
$$

$$
\boxed{\text{a symmetric split gives }q_i^\ast=\frac{7}{4},\ \pi_i^\ast=\frac{49}{8}\ (\approx 6.125). }
$$

Cournot over-produces because each firm ignores the negative price externality on rivals; the quantity wedge relative to the planner solution is exactly this uninternalized cross-effect.

***

### (b) Stackelberg quantity game (leader → follower), SPNE

* Start from the model used in the notes: inverse demand $$p(Q)=8-(q_1+q_2)$$, constant marginal cost $$c=1$$, and $$q_i\ge 0$$.
* Use **backward induction**: first write firm 2’s best response for any $$q_1$$​, including the off-path non-negativity corner.
* Plug that best response into firm 1’s problem, take the FOC, check the SOC, and verify the corner is not binding at the solution.
* State the **SPNE as a strategy profile** (not just a pair of quantities on the equilibrium path).
* Report the on-path outcome (quantities and price) and each firm’s profit, with a one-line intuition.

***

#### **Derivation**

We follow the usual Stackelberg logic: solve the follower’s problem first and then move back to the leader.

**Environment and payoffs.**&#x20;

Total quantity is $$Q=q_1+q_2$$​. With $$p(Q)=8-Q$$ and $$c=1$$, firm $$i$$’s profit is

$$
\pi_i(q_1,q_2)=\big(p(Q)-c\big)\,q_i=\big(8-(q_1+q_2)-1\big)q_i=(7-q_1-q_2)\,q_i,
$$

with $$q_i\ge 0$$.

**Step 1: follower (firm 2) best response.**&#x20;

Fix any $$q_1$$​ announced by the leader. Firm 2 chooses $$q_2\ge 0$$ to maximize

$$
\pi_2(q_1,q_2)=(7-q_1-q_2)\,q_2.
$$

The FOC is

$$
\frac{\partial \pi_2}{\partial q_2}=7-q_1-2q_2=0 \quad\Rightarrow\quad q_2=\frac{7-q_1}{2}.
$$

The second derivative is $$\frac{\partial^2 \pi_2}{\partial q_2^2}=-2<0$$, so the interior solution is a maximum whenever it is non-negative. Because quantities cannot be negative, the **global** best response is

$$
\boxed{\,BR_2(q_1)=\max\!\left\{\frac{7-q_1}{2},\,0\right\}.}
$$

This is the downward-sloping reaction curve we expect in a quantity game with strategic substitutes: as the leader raises $$q_1$$​, the follower optimally scales back.

**Step 2: leader (firm 1) problem.**&#x20;

Anticipating $$BR_2(q_1)$$, firm 1 chooses $$q_1\ge 0$$ to maximize

$$
\pi_1(q_1)=\big(7-q_1-BR_2(q_1)\big)\,q_1.
$$

On the region where $$BR_2(q_1)=(7-q_1)/2$$ (i.e., $$q_1<7$$), this reduces to

$$
\pi_1(q_1)=\left(7-q_1-\frac{7-q_1}{2}\right)q_1=\frac{7-q_1}{2}\,q_1.
$$

The derivative and SOC are

$$
\frac{d\pi_1}{dq_1}=\frac{7-2q_1}{2}=0 \ \Rightarrow\ \boxed{\,q_1^{\ast}=\frac{7}{2}\,}, \qquad \frac{d^2\pi_1}{dq_1^2}=-1<0.
$$

Feasibility and corner check: $$q_1^{\ast}=3.5<7$$, so the follower’s interior response is valid. Therefore,

$$
q_2^{\ast}=BR_2\!\left(\frac{7}{2}\right)=\frac{7-3.5}{2}=\boxed{\,\frac{7}{4}\,}.
$$

**On-path outcome and payoffs.**&#x20;

The market outcome implied by these strategies is

$$
Q^{\ast}=q_1^{\ast}+q_2^{\ast}=\frac{21}{4}, \qquad p^{\ast}=8-Q^{\ast}=\boxed{\,\frac{11}{4}\,}.
$$

Profits are

$$
\pi_1^{\ast}=(p^{\ast}-1)q_1^{\ast}=\left(\frac{11}{4}-1\right)\frac{7}{2} =\boxed{\,\frac{49}{8}\,},
$$

$$
\qquad \pi_2^{\ast}=(p^{\ast}-1)q_2^{\ast} =\left(\frac{11}{4}-1\right)\frac{7}{4} =\boxed{\,\frac{49}{16}\,}.
$$

Because quantities are strategic substitutes, the leader commits to a larger quantity than in Cournot, pushing the follower down its reaction curve; this is the textbook “first-mover advantage” in Stackelberg.

***

#### Answer

* **SPNE (strategies):**

$$
s_1^{\ast}:\ \ q_1=\frac{7}{2}, \qquad s_2^{\ast}(q_1):\ \ q_2=\max\!\left\{\frac{7-q_1}{2},\,0\right\}.
$$

* **On-path outcome and payoffs:**

$$
(q_1,q_2)=\left(\frac{7}{2},\,\frac{7}{4}\right),\quad p=\frac{11}{4},\quad \pi_1=\frac{49}{8},\quad \pi_2=\frac{49}{16}.
$$

Leader commitment internalizes the rival’s reaction and benefits precisely because the market exhibits negative cross-effects (strategic substitutes).

***

### (c) First- vs. second-mover advantage in a sequential quantity game

* Pull the benchmark payoffs from (a) Cournot and (b) Stackelberg.
* Rank leader, follower, and Cournot profits to determine who benefits from moving first/second.
* Give the intuition tied to downward-sloping best responses (strategic substitutes).

***

#### Benchmarks and ranking

From (a) Cournot, each firm earns

$$
\pi_i^{C}=\frac{49}{9}\approx 5.444.
$$

From (b) Stackelberg,

$$
\pi_1^{S}=\frac{49}{8}=6.125,\qquad \pi_2^{S}=\frac{49}{16}=3.0625.
$$

Therefore, the payoffs satisfy

$$
\pi_1^{S}\;>\;\pi_i^{C}\;>\;\pi_2^{S},
$$

so the leader gains relative to Cournot while the follower loses—i.e., a first-mover advantage in this sequential quantity game.

#### Economic intuition (strategic substitutes)

In Cournot/Stackelberg quantity competition, best responses are downward-sloping: a higher quantity by one firm reduces the other’s best response. By committing first to a larger output, the leader pushes the follower down its reaction curve, softening the follower’s optimal quantity and raising the leader’s profit; the follower, moving second, is the one squeezed.

***

#### Answer

First-mover advantage.

Read timing through an externality lens: with negative cross-effects the leader harvests the gain from pushing rivals down; with positive cross-effects the follower captures benefits created by the leader.

***

### (d) Simultaneous effort game: BRs, NE, and efficiency benchmark

* Specify the roommate “public-good–type” environment as a normal-form game.
* Derive each player’s best-response (BR) function and identify strategic complements.
* Solve for the symmetric Nash equilibrium efforts and payoffs.
* Compute the efficient allocation by maximizing the sum of payoffs, and compare to NE.
* Explain why NE under-provides effort via the public-good externality logic.

***

#### Environment (normal form)

Two players $$i\in\{1,2\}$$ (roommates) simultaneously choose effort $$e_i\ge 0$$.&#x20;

“Cleanness” is

$$
y \;=\; e_1+e_2+\frac{e_1e_2}{4},
$$

and the payoff to $$i$$ is

$$
u_i(e_1,e_2)\;=\; y - e_i^2 \;=\; e_1+e_2+\frac{e_1e_2}{4}-e_i^2.
$$

#### Best-response functions

Fix $$e_j$$​. Player $$i$$ solves $$\max_{e_i\ge 0}\, u_i(e_i;e_j)$$ with

$$
\frac{\partial u_i}{\partial e_i}\;=\;1+\frac{e_j}{4}-2e_i=0,\qquad \frac{\partial^2 u_i}{\partial e_i^2}=-2<0.
$$

Hence the interior BR is linear and upward-sloping:

$$
BR_i(e_j)=\frac{1}{2}+\frac{1}{8}e_j,\qquad \frac{d\,BR_i}{de_j}=\frac{1}{8}>0,
$$

so efforts are strategic complements. Because the intercept is $$1/2>0$$, the nonnegativity constraint is slack at the equilibrium we find.

#### Nash equilibrium

Look for a symmetric interior NE with $$e_1=e_2=e$$.&#x20;

Imposing fixed point $$e=BR_i(e)$$ gives

$$
e \;=\; \frac{1}{2}+\frac{1}{8}e \;\;\Longrightarrow\;\; \frac{7}{8}e=\frac{1}{2} \;\;\Longrightarrow\;\; e^{N}=\frac{4}{7}.
$$

Plugging back,

$$
u_i^N \;=\; \Big(2e^{N}+\frac{(e^{N})^2}{4}\Big) - (e^{N})^2 \;=\; \frac{44}{49}\;\approx\;0.898.
$$

#### Efficient allocation

Maximize total payoff $$W(e_1,e_2)=u_1+u_2$$​:

$$
W(e_1,e_2)=2(e_1+e_2)+\frac{1}{2}e_1e_2-(e_1^2+e_2^2).
$$

FOCs (and SOCs) yield, by symmetry $$e_1=e_2=e$$,

$$
\frac{\partial W}{\partial e_1}=2+\frac{1}{2}e_2-2e_1=0,\quad \frac{\partial W}{\partial e_2}=2+\frac{1}{2}e_1-2e_2=0 \;\Rightarrow\; e^{*}=\frac{4}{3}.
$$

Individual payoff at the efficient point:

$$
u_i^{*}=\Big(2e^{*}+\frac{(e^{*})^2}{4}\Big)-(e^{*})^2=\frac{4}{3}\approx 1.333.
$$

#### Comparison & intuition

We obtain

$$
e^{*}=\frac{4}{3}\;>\; e^{N}=\frac{4}{7}, \qquad u_i^{*}=\frac{4}{3}\;>\;u_i^{N}=\frac{44}{49}.
$$

Thus the simultaneous-move NE under-provides effort relative to the utilitarian benchmark.&#x20;

**Why NE under-provides effort?**

Each player internalizes only the private marginal benefit $$1+\tfrac{e_j}{4}$$​​ when choosing $$e_i$$​ (the BR FOC), but the planner internalizes the social marginal benefit $$2+\tfrac{e_j}{2}$$ (the $$W$$ FOC). The missing $$\tfrac{1}{2}e_j$$ term is the positive externality on the other roommate, so decentralized behavior free-rides and delivers too little effort—standard public-good logic.

***

#### Answer

$$
\boxed{BR_i(e_j)=\tfrac{1}{2}+\tfrac{1}{8}e_j}
$$

$$
\boxed{\quad e_1^{N}=e_2^{N}=\tfrac{4}{7},\ \ u_i^{N}=\tfrac{44}{49}\approx 0.898.}
$$

$$
\boxed{\text{Efficient: } e_1^{*}=e_2^{*}=\tfrac{4}{3},\ \ u_i^{*}=\tfrac{4}{3}\approx 1.333.}
$$

Because each player ignores the positive spillover on the other, the simultaneous-move NE under-provides effort relative to the utilitarian optimum.

***

### (e) Sequential effort with perfect information: SPNE&#x20;

* Model the two-stage perfect-information version of the roommates’ cleaning game.
* Solve the follower’s problem at Stage 2 to obtain the best-response $$R_2(e_1)$$.
* Anticipating $$R_2(\cdot)$$, solve the leader’s Stage-1 problem and verify SOCs.
* State the SPNE in strategy form and report equilibrium efforts and payoffs.

***

#### Environment (extensive form)

Two players $$i\in\{1,2\}$$ choose non-negative efforts $$e_i\ge 0$$. Cleanness is

$$
y \;=\; e_1 + e_2 + \frac{e_1 e_2}{4},
$$

and player $$i$$’s payoff is

$$
u_i(e_1,e_2) \;=\; e_1 + e_2 + \frac{e_1 e_2}{4} \;-\; e_i^2 .
$$

In part (e), the timing is sequential with perfect information: roommate 1 chooses $$e_1$$​ at Stage 1; roommate 2 observes $$e_1$$​ and then chooses $$e_2$$​ at Stage 2. The task is to find the SPNE.

Methodologically we apply Backward Induction (BWI) for finite-horizon, perfect-information games: solve Stage 2, plug the reaction into Stage 1, then report history-contingent strategies that are best responses in every subgame.

#### Stage 2 — Follower’s problem

Fix $$e_1$$​. Player 2 chooses $$e_2\ge 0$$ to maximize $$u_2(e_1,e_2)= e_1 + e_2 + \frac{e_1 e_2}{4} - e_2^2$$​.

$$
\frac{\partial u_2}{\partial e_2} \;=\; 1 + \frac{e_1}{4} - 2 e_2 = 0 \quad\Rightarrow\quad R_2(e_1) \;=\; \frac{1}{2} + \frac{e_1}{8},
$$

$$
\frac{\partial^2 u_2}{\partial e_2^2}=-2<0.
$$

Thus the follower’s BR is upward-sloping $$\big(dR_2/de_1=\tfrac18>0\big)$$, i.e., efforts are strategic complements.

#### Stage 1 — Leader anticipating the follower’s reaction

Player 1 chooses $$e_1\ge 0$$ to maximize $$u_1\big(e_1,R_2(e_1)\big)= e_1 + R_2(e_1) + \frac{e_1 R_2(e_1)}{4} - e_1^2$$​ with $$R_2(e_1)=\tfrac12+\tfrac{e_1}{8}$$​​.

$$
u_1\big(e_1,R_2(e_1)\big) \;=\; \frac{1}{2} \;+\; \frac{5}{4}e_1 \;-\; \frac{31}{32}e_1^{\,2},
$$

$$
\frac{d}{de_1}u_1\big(e_1,R_2(e_1)\big)= \frac{5}{4}-\frac{31}{16}e_1 = 0 \quad\Rightarrow\quad e_1^{S}=\frac{20}{31},\qquad \frac{d^2}{de_1^2}u_1=-\frac{31}{16}<0.
$$

Back-substituting,

$$
e_2^{S}=R_2(e_1^{S})=\frac{1}{2}+\frac{1}{8}\cdot\frac{20}{31}=\frac{18}{31}.
$$

Both choices are strictly positive, so the nonnegativity constraint is indeed slack at the optimum.

#### SPNE — strategy form and outcomes

The subgame-perfect strategy profile is:

$$
s_1^\ast:\ \text{at the initial node, choose } e_1=\frac{20}{31}; \qquad s_2^\ast:\ \text{after any observed } e_1,\ \ e_2=\frac{1}{2}+\frac{e_1}{8}.
$$

By construction, $$s_2^\ast$$​ is a best response in the proper subgame beginning at player 2’s information set, and $$s_1^\ast$$​ optimizes given $$s_2^\ast$$​.

For later comparison, the associated payoffs are

$$
u_1^{S}=u_1\!\left(\tfrac{20}{31},\tfrac{18}{31}\right)=\frac{28}{31}\approx 0.903, \qquad u_2^{S}=u_2\!\left(\tfrac{20}{31},\tfrac{18}{31}\right)=\frac{944}{961}\approx 0.982.
$$

***

#### Answer

$$
\boxed{ R_2(e_1)=\tfrac{1}{2}+\tfrac{1}{8}e_1\ \ (\text{upward-sloping ⇒ strategic complements}); \quad e_1^{S}=\tfrac{20}{31},\ \ e_2^{S}=\tfrac{18}{31}. }
$$

These strategies constitute the SPNE of the sequential, perfect-information effort game: the follower’s $$R_2(\cdot)$$ is optimal in the Stage-2 subgame for every history, and the leader’s $$e_1^{S}$$ maximizes $$u_1(e_1,R_2(e_1))$$ at Stage 1 (SOCs satisfied), so the profile is a pair of history-contingent best responses in every subgame.

***

### (f) First- vs. second-mover advantage in the roommates’ effort game

* Pull in the benchmarks from parts (d) (simultaneous NE) and (e) (sequential SPNE).
* Compare leader vs follower payoffs in the sequential game; decide who has the timing advantage.
* Explain the mechanism: how an upward-sloping best response (strategic complements) tilts gains to the second mover.

***

#### Benchmarks from parts (d) and (e)

From part (d), best responses are upward-sloping

$$
BR_i(e_j)=\tfrac{1}{2}+\tfrac{1}{8}e_j,
$$

and the symmetric NE is

$$
e_1^N=e_2^N=\tfrac{4}{7},\quad u_i^N=\tfrac{44}{49}\approx 0.898 .
$$

From part (e), the SPNE (leader 1, follower 2) is

$$
e_1^S=\tfrac{20}{31},\qquad e_2^S=\tfrac{18}{31}.
$$

#### Who has the advantage in the sequential effort game?

Evaluating payoffs at the SPNE yields

$$
u_1^S=\tfrac{28}{31}\approx 0.903,\qquad u_2^S=\tfrac{944}{961}\approx 0.982 .
$$

Hence

$$
u_2^S-u_1^S=\tfrac{944}{961}-\tfrac{28}{31}>0,
$$

so the follower (second mover) strictly dominates the leader in this sequential complements game. Moreover, both do better than in the simultaneous move:

$$
u_1^S-u_i^N=\tfrac{28}{31}-\tfrac{44}{49}>0,\qquad u_2^S-u_i^N=\tfrac{944}{961}-\tfrac{44}{49}>0.
$$

Sequential timing helps both, but helps the follower more.

#### Intuition

With strategic complements ($$BR_2'(e_1)>0$$), when the leader raises $$e_1$$​, the follower’s best response rises. The leader anticipates this “crowd-in” and chooses $$e_1$$​ knowing $$e_2$$​ will increase along an upward BR. But moving second allows the follower to fine-tune after seeing $$e_1$$​, capturing more of the positive cross-term $$e_1e_2/4$$ while avoiding the leader’s quadratic cost burden. Thus the surplus shifts toward the follower—a second-mover advantage under complements.

***

#### Answer

Second-mover advantage in the roommates’ effort game:&#x20;

$$
u_2^S=\tfrac{944}{961}>u_1^S=\tfrac{28}{31}>u_i^N=\tfrac{44}{49}.
$$

Because efforts are strategic complements (upward-sloping BRs), the follower earns more than the leader in the sequential SPNE and more than in the simultaneous game; by contrast, with strategic substitutes (Cournot quantities) the leader enjoys the advantage. The direction of timing advantage is pinned down by the sign of the BR slope.

“BR-slope rule = ‘externality direction’ rule”: downward BRs + negative cross-effects → leader advantage; upward BRs + positive cross-effects → follower advantage.

***

### (g) Generalization — a short “BR-slope” rule

Take any two-player game where each picks one real action $$a_i\ge0$$, payoffs $$u_i(a_i,a_j)$$ are strictly concave in own action, and the follower’s best response exists and is single-valued: $$a_2=R_2(a_1)$$. In the sequential version (1 leads, 2 follows), backward induction says player 1 solves

$$
\max_{a_1\ge0}\ u_1\big(a_1,R_2(a_1)\big),
$$

with FOC

$$
\frac{d}{da_1}u_1\big(a_1,R_2(a_1)\big) = u_{1a_1}(a_1,a_2)\;+\;u_{1a_2}(a_1,a_2)\,R_2'(a_1)=0.
$$

The key is the sign of $$R_2'(a_1)$$. If $$R_2'(a_1)<0$$ (strategic substitutes), a higher $$a_1$$ pushes the follower down along a downward BR, so the leader benefits from committing first ⇒ first-mover advantage. If $$R_2'(a_1)>0$$ (strategic complements), raising $$a_1$$​ pulls the follower up; moving second lets the follower fine-tune after seeing $$a_1$$ ⇒ second-mover advantage.

This exactly matches our two benchmarks: in Cournot/Stackelberg quantities (downward BRs) the leader wins; in the roommates’ effort game (upward BRs) the follower wins. So the quick rule is: downward BR ⇒ leader advantage; upward BR ⇒ follower advantage.

***

***

## Q2: Edgeworth box with quasi linearity

***

### (a) Interior Pareto set under quasi-linearity

* Work in the Edgeworth box with feasibility $$x_A+x_B=\bar x=10$$ and $$y_A+y_B=\bar y=20$$.
* Utilities are quasi-linear: $$u_A(x_A,y_A)=\sqrt{x_A}+y_A$$​, $$u_B(x_B,y_B)=2\sqrt{x_B}+y_B$$
* At an interior Pareto optimum (the contract curve inside the box), the tangency condition $$MRS_A^{x,y}=MRS_B^{x,y}$$​ holds.
* Because $$y$$ is the “money” (marginal utility $$=1$$ for both), efficiency pins down only the allocation of $$x$$; any strictly positive split of $$y$$ that exhausts $$\bar y$$​ is also efficient.

***

#### Setup

We label the two goods $$x$$ (the “non-money” good) and $$y$$ (the money good). Feasibility requires the individual consumptions to add up to endowments:

$$
x_A+x_B=10,\qquad y_A+y_B=20,
$$

and “interior” means&#x20;

$$
x_A>0,\;x_B>0,\;y_A>0,\;y_B>0.
$$

#### Tangency (Pareto efficiency) in the Edgeworth box

For any interior Pareto-efficient allocation, the two agents’ indifference curves are tangent. In our notation this is the equality of marginal rates of substitution between $$x$$ and $$y$$:

$$
MRS_A^{x,y}=\frac{MU_A(x)}{MU_A(y)}= \frac{MU_B(x)}{MU_B(y)}=MRS_B^{x,y}.
$$

With quasi-linearity, $$MU_i(y)=1$$ for both agents, so the tangency simplifies to “equal marginal utilities of $$x$$”:

$$
MU_A(x)=MU_B(x).
$$

#### Use quasi-linearity to reduce the problem to the x-split

From the given utilities we get

$$
MU_A(x)=\frac{1}{2\sqrt{x_A}},\qquad MU_B(x)=\frac{1}{\sqrt{x_B}}.
$$

Equalizing these and using feasibility for $$x$$ gives

$$
\frac{1}{2\sqrt{x_A}}=\frac{1}{\sqrt{x_B}} \;\Longrightarrow\; \sqrt{x_B}=2\sqrt{x_A} \;\Longrightarrow\; x_B=4x_A,
$$

$$
x_A+x_B=10 \;\Longrightarrow\; x_A+4x_A=10 \;\Longrightarrow\; x_A=2,\; x_B=8.
$$

#### Characterize the efficient y-allocations

Since $$MU_i(y)=1$$ for both, redistributing $$y$$ does not change the tangency; it only shifts utilities by the same “slope-1” amount. Therefore any strictly positive money split that sums to $$\bar y$$ is efficient. We can parametrize it by a single number $$t$$:

$$
y_A=t,\qquad y_B=20-t,\qquad \text{with } t\in(0,20).
$$

Choosing $$t$$ in this open interval keeps the allocation interior.

***

#### Answer

The interior Pareto-efficient set (the interior contract curve here) is given by the unique non-money split $$(x_A,x_B)=(2,8)$$ together with any strictly positive money split that exhausts $$\bar y$$​: $$(y_A,y_B)=(t,20-t)$$ for $$t\in(0,20)$$. In words, quasi-linearity forces the efficient $$x$$-allocation to be $$A$$ gets 2 and $$B$$ gets 8, while the money good $$y$$ can be shared in any interior way without affecting efficiency.

***

### (b) Allow negative money (debt)

* New assumption: $$x_A\ge 0,\;x_B\ge 0$$ but the money good can be negative for either agent, with feasibility $$x_A+x_B=10,\;y_A+y_B=20$$. List all Pareto-efficient allocations under this domain.
* Use the Edgeworth-box tangency idea $$MRS_A^{x,y}=MRS_B^{x,y}$$​ together with feasibility; this is our “consumption efficiency” condition in the notes.
* Because utilities are quasi-linear in $$y$$, the marginal utility of money is 1 for everyone, so efficiency pins down only the split of the non-money good $$x$$; money $$y$$ is just a transfer.

***

#### Derivation — pin down the x–split (then y is free to move)

Start from the tangency condition.

$$
MRS_i^{x,y}=\frac{MU_i(x)}{MU_i(y)}\quad\text{and}\quad MU_i(y)=1\ \text{(quasi-linear)}.
$$

So interior efficiency reduces to equalizing the marginal utility of $$x$$: $$MU_A(x_A)=MU_B(x_B)$$. With $$u_A=\sqrt{x_A}+y_A$$​ and $$u_B=2\sqrt{x_B}+y_B$$​,

$$
MU_A(x)=\frac{1}{2\sqrt{x_A}},\qquad MU_B(x)=\frac{1}{\sqrt{x_B}}.
$$

Equating them gives $$\sqrt{x_B}=2\sqrt{x_A}\Rightarrow x_B=4x_A$$​. Combine with feasibility $$x_A+x_B=10$$ to get $$x_A=2,\;x_B=8$$. This solution already satisfies $$x_i\ge 0$$, and corners like $$x_A=0$$ or $$x_B=0$$ cannot be efficient here because $$MU_i(x)$$ would blow up at zero for at least one agent, breaking tangency. The key point is that quasi-linearity makes $$y$$ irrelevant for the tangency, so once $$x$$ is fixed efficiently, any redistribution of $$y$$ that keeps the aggregate at 20 is still Pareto-efficient.&#x20;

#### Characterizing the whole efficient set under y∈R

Feasibility for money is $$y_A+y_B=20$$ but there is no sign restriction now. Hence once $$(x_A,x_B)=(2,8)$$ is fixed, the entire efficient set is generated by letting $$y_A$$​ be any real number and setting $$y_B=20-y_A$$​. Geometrically, compared to part (a), the contract-curve “segment” in the $$y$$-interior stretches out to the full horizontal line through the efficient $$x$$-split because we allow negative $$y$$.

***

#### Answer

All Pareto-efficient allocations under $$x_A\ge 0,\;x_B\ge 0$$ and $$y_i\in(-\infty,\infty)$$ are those with the unique non-money split $$(x_A,x_B)=(2,8)$$ and any real money transfer that satisfies feasibility, i.e. $$(y_A,y_B)=(t,\,20-t)$$ for arbitrary $$t\in\mathbb{R}$$; this follows from the tangency $$MRS_A^{x,y}=MRS_B^{x,y}$$​ (consumption efficiency) and the quasi-linear fact $$MU_i(y)=1$$ for both agents, which makes $$y$$ just a transfer.

***

### (c) Nonnegativity on both goods

* Work with the given utilities $$u_A(x_A,y_A)=\sqrt{x_A}+y_A$$​, $$Bu_B(x_B,y_B)=2\sqrt{x_B}+y_B$$​ and endowment $$(\bar x,\bar y)=(10,20)$$.
* Impose $$x_A,x_B,y_A,y_B\ge 0$$ and feasibility $$x_A+x_B=10,\;y_A+y_B=20$$. We must list all Pareto-efficient allocations under these constraints.

***

#### Setup

We follow the general-equilibrium logic from the notes: interior efficiency = “consumption efficiency” (tangency of indifference curves), while on a boundary we use the KKT-style inequality version of the tangency. With quasi-linearity, the money good $$y$$ is a numéraire: its marginal utility is 1 for both agents, so the MRS between $$x$$ and $$y$$ equals the marginal utility of $$x$$. Concretely,

$$
MRS_A=\frac{1}{2\sqrt{x_A}},\qquad MRS_B=\frac{1}{\sqrt{x_B}}=\frac{1}{\sqrt{10-x_A}}\;.
$$

We’ll proceed in three blocks: (i) interior in $$y$$, (ii) bottom edge $$y_A=0$$, (iii) top edge $$y_B=0$$.

#### Interior in y

When both agents consume some of the numéraire, the usual tangency applies:

$$
MRS_A=MRS_B\quad\Rightarrow\quad \frac{1}{2\sqrt{x_A}}=\frac{1}{\sqrt{10-x_A}} \;\Rightarrow\; x_A=2\;(x_B=8).
$$

With quasi-linearity, the efficient quantity of the non-money good is pinned down uniquely; $$y$$ can then be transferred without affecting efficiency. Under part (c), the nonnegativity allows the closed segment $$y_A\in[0,20]$$ (not just the open interval).

#### Bottom edge

Here $$A$$ cannot give up any more money to compensate $$B$$, while $$B$$ can still transfer money to $$A$$. A small trade “$$x$$ from $$A$$ to $$B$$ + money back to $$A$$” is a Pareto improvement whenever $$B$$ values $$x$$ at the margin more than $$A$$ does, i.e. $$MRS_B>MRS_A$$​. To block such improvements at $$y_A=0$$, we need

$$
MRS_A\;\ge\;MRS_B\quad\Longleftrightarrow\quad \frac{1}{2\sqrt{x_A}}\ge\frac{1}{\sqrt{10-x_A}} \quad\Longleftrightarrow\quad x_A\le 2.
$$

So along the bottom edge, every point with $$0\le x_A\le 2$$ is Pareto efficient. (The corner $$(x_A,y_A)=(0,0)$$ is included: you can’t help $$A$$ without hurting $$B$$ because $$B$$ already holds all $$y$$.)

#### Top edge

This is symmetric. Now only $$A$$ can transfer money to compensate, so to prevent Pareto improvements we need $$A$$ to value $$x$$ weakly less than $$B$$: $$MRS_B\ge MRS_A$$​. That flips the inequality:

$$
\frac{1}{\sqrt{10-x_A}}\;\ge\;\frac{1}{2\sqrt{x_A}} \quad\Longleftrightarrow\quad x_A\ge 2.
$$

Thus along the top edge, every point with $$2\le x_A\le 10$$ is Pareto efficient. (Corner $$(x_A,y_A)=(10,20)$$ is also efficient for the same “no feasible compensation” reason.)

***

#### Answer

Efficient allocations (with $$x_A,x_B,y_A,y_B\ge 0$$ and $$\bar x=10,\bar y=20$$) are exactly the following three pieces:

* Interior $$y$$ (both get some money):

$$
x_A=2,\quad 0<y_A<20.
$$

* Bottom edge ($$y_A=0$$, so $$y_B=20$$):

$$
0\le x_A\le 2.
$$

* Top edge ($$y_B=0$$, so $$y_A=20$$):

$$
2\le x_A\le 10.
$$

Feasibility for the other agent is always

$$
x_B=10-x_A,\qquad y_B=20-y_A.
$$

The efficient set is the vertical line at $$x_A=2$$ when both hold some money, plus the two money-boundary segments created by nonnegativity.

***

### (d) Support a bottom-edge efficient point by a competitive price

* Choose any Pareto-efficient allocation from part (c) that lies on the bottom edge $$y_A=0$$: then $$x_A\in[0,2]$$, $$x_B=10-x_A$$​, $$y_B=20$$.&#x20;
* Find a price-taking (Walrasian) equilibrium $$(p_x,p_y)$$ and incomes so that each agent’s choice at those prices is the chosen allocation. We’ll use the notes’ CE rule “at an interior point, $$MRS=p_x/p_y$$​” and the 2nd Welfare Theorem idea “redistribute wealth, keep prices as the supporting slope.”
* Use quasi-linearity (money good has marginal utility $$=1$$): normalize the money price to $$p_y=1$$.

***

#### Derivation (build prices and incomes that support the target)

**Step 1 — Fix the target bundle.**\
Pick any efficient bottom-edge bundle from (c):

$$
(x_A,y_A;\;x_B,y_B)=(x_A,0;\;10-x_A,\,20),\quad x_A\in[0,2].
$$

**Step 2 — Choose the supporting price.**\
Set the numéraire $$p_y=1$$. Because $$B$$ has $$y_B=20>0$$ (interior in money), CE tangency applies to $$B$$: choose $$p_x$$​ to equal $$B$$’s MRS at $$x_B=10-x_A$$​.

$$
p_x=\text{MRS}_B=\frac{1}{\sqrt{x_B}}=\frac{1}{\sqrt{\,10-x_A\,}}.
$$

This is the “supporting slope” of $$B$$’s indifference curve at the target.

**Step 3 — Set incomes via the 2nd Welfare Theorem.**\
Give each agent income equal to the value of the target bundle at $$(p_x,1)$$:

$$
m_A=p_x\,x_A+0,\qquad m_B=p_x(10-x_A)+20.
$$

This is the standard decentralization move: pick prices that support the point and put budgets through it.

**Step 4 — Check each agent’s optimality and market clearing.**

* **Agent B (interior in** $$y$$**)**: With $$p_y=1$$, quasi-linear demand sets $$MRS_B= p_x$$​, i.e. $$1/\sqrt{x_B}=p_x$$, so $$x_B=1/p_x^2=10-x_A$$​ and $$y_B=m_B-p_xx_B=20$$.
* **Agent A (corner** $$y_A=0y$$**)**: At price $$p_x$$, A’s unconstrained FOC would want $$x_A^{FOC}=1/(4p_x^2)=(10-x_A)/4\ge 2$$, but his income is only $$m_A=p_xx_A$$​. So he buys the most $$x$$ he can and sets $$y_A=0$$: $$(x_A,y_A)=(m_A/p_x,0)=(x_A,0)$$. Consistency check: bottom-edge efficiency gives $$\text{MRS}_A(x_A)=1/(2\sqrt{x_A})\ge p_x=\text{MRS}_B$$, so the $$y_A=0$$ corner satisfies the Kuhn–Tucker “no profitable move” condition for A.
* **Markets**: $$x_A+x_B=10$$ and $$y_A+y_B=20$$; both budgets bind exactly. This is a valid competitive equilibrium by the CE definition.

***

#### Answer

For any Pareto-efficient bottom-edge point from (c), i.e. $$(x_A,0;\,10-x_A,\,20)$$ with $$x_A\in[0,2]$$, a price-taking equilibrium that supports it is:

$$
p_y=1,\qquad p_x=\frac{1}{\sqrt{\,10-x_A\,}},\qquad m_A=p_xx_A,\quad m_B=p_x(10-x_A)+20.
$$

At these prices and incomes, $$B$$ is interior and chooses $$x_B=10-x_A$$​ by $$MRS_B=p_x$$​, while $$A$$ is money-constrained and chooses $$(x_A,0)$$; both markets clear. This matches the class rule “CE tangency + 2nd Welfare Theorem decentralization.”

***

***

## Q3: oligopoly in Cournot competition

***

### (a) Solve the symmetric Cournot–Nash equilibrium for three identical firms (linear demand, constant MC)

* Write each firm’s profit and first-order condition (Cournot best response).
* Use symmetry $$q_1=q_2=q_3$$​ to pin down the unique Nash equilibrium.
* Compute the per-firm output $$q_i^{\ast}$$​, industry output $$Q^{\ast}$$, and price $$p^{\ast}$$.
* State the interior condition on parameters so that all firms produce in equilibrium.

***

#### Derivation

First, define total quantity as $$Q=q_1+q_2+q_3$$ and recall the inverse demand $$p(Q)=A-BQ$$ with constant marginal cost $$c$$. We write firm $$i$$’s profit taking rivals’ total output $$q_{-i}$$ as given, exactly as in the Cournot setup in the lecture notes that motivates best-response functions.

$$
\pi_i(q_i,q_{-i})=\big(A - B(q_i+q_{-i}) - c\big)\,q_i.
$$

To find firm $$i$$’s best response, I differentiate with respect to $$q_i$$ and set it equal to zero (holding $$q_{-i}$$ fixed, as usual in the reaction-function method):

$$
\frac{\partial \pi_i}{\partial q_i}=A-c-2Bq_i-Bq_{-i}=0.
$$

Solving the first-order condition gives the (downward-sloping) reaction/best-response function:

$$
q_i=\frac{A-c-Bq_{-i}}{2B}.
$$

This downward slope captures “strategic substitutes”: the more aggressively others produce (higher $$q_{-i}$$), the less I want to produce. The Cournot–Nash equilibrium is at the intersection of firms’ reaction functions.

Now impose symmetry $$q_1=q_2=q_3\equiv q^{\ast}$$, so each firm faces $$q_{-i}=2q^{\ast}$$. Substituting into the best response and solving:

$$
q^{\ast}=\frac{A-c-2Bq^{\ast}}{2B},
$$

$$
4B\,q^{\ast}=A-c,
$$

$$
q^{\ast}=\frac{A-c}{4B}.
$$

From this, the industry output and the market price follow immediately:

$$
Q^{\ast}=3q^{\ast}=\frac{3(A-c)}{4B},
$$

$$
p^{\ast}=A-BQ^{\ast}=\frac{A+3c}{4}.
$$

The interior condition is $$A>c$$ so that $$q^{\ast}>0$$, which is exactly the “$$c$$ small enough” assumption in the question.

***

#### Answer

$$
q_i^{\ast}=\frac{A-c}{4B},\qquad Q^{\ast}=\frac{3(A-c)}{4B},\qquad p^{\ast}=\frac{A+3c}{4}.
$$

In words, each firm chooses $$q_i^{\ast}$$​ given above; adding up gives $$Q^{\ast}$$, and plugging that into inverse demand gives $$p^{\ast}$$. This comes straight from each firm’s best-response to rivals and the symmetry $$q_1=q_2=q_3$$​; the condition $$A>c$$ ensures all three produce a positive amount in equilibrium.

***

### (b) Generalize the symmetric Cournot equilibrium to n-identical firms

* Start from the same best-response (reaction) logic as in (a).
* Impose symmetry across $$n$$ firms and solve for the common quantity.
* Report $$q_i^{\ast}$$​, $$Q^{\ast}$$, and $$p^{\ast}$$ in simple closed form.
* State the interior condition so that all firms produce.

***

#### Derivation

I keep the linear inverse demand and constant marginal cost exactly as in (a). With $$n$$ firms, firm $$i$$ takes the other firms’ total $$q_{-i}$$​ as given and chooses its own $$q_i$$​. The profit function is the same object as before, just with $$q_{-i}$$​ now summing over $$n-1$$ rivals.

$$
\pi_i(q_i,q_{-i})=\big(A-B(q_i+q_{-i})-c\big)\,q_i.
$$

I differentiate with respect to $$q_i$$​ and set it to zero to get firm $$i$$’s best-response function. This is identical in shape to (a); only $$q_{-i}$$​ is now the sum of $$n-1$$ others.

$$
\frac{\partial \pi_i}{\partial q_i}=A-c-2Bq_i-Bq_{-i}=0,
$$

$$
q_i=\frac{A-c-Bq_{-i}}{2B}.
$$

For a symmetric Cournot–Nash outcome, every firm produces the same quantity, so I set $$q_1=\cdots=q_n\equiv q^{\ast}$$. Then each firm faces $$q_{-i}=(n-1)q^{\ast}$$. Plugging this into the best-response and solving for $$q^{\ast}$$ gives:

$$
q^{\ast}=\frac{A-c-B(n-1)q^{\ast}}{2B},
$$

$$
\big[\,2B+B(n-1)\,\big]\,q^{\ast}=A-c,
$$

$$
B(n+1)\,q^{\ast}=A-c,
$$

$$
q^{\ast}=\frac{A-c}{B(n+1)}.
$$

With the per-firm quantity in hand, I add up across all nnn firms to get total output, and then substitute into inverse demand to get the price.

$$
Q^{\ast}=n\,q^{\ast}=\frac{n(A-c)}{B(n+1)},
$$

$$
p^{\ast}=A-BQ^{\ast}=A-\frac{n(A-c)}{n+1} =\frac{A+nc}{\,n+1\,}.
$$

The same interior condition as in (a) appears here: I need $$A>c$$ so that $$q^{\ast}>0$$ for every firm.

***

#### Answer

$$
q_i^{\ast}=\frac{A-c}{B(n+1)},\qquad Q^{\ast}=\frac{n(A-c)}{B(n+1)},\qquad p^{\ast}=\frac{A+nc}{n+1}.
$$

In words, starting from the usual reaction function and imposing symmetry across $$n$$ identical firms yields the per-firm quantity $$q_i^{\ast}$$​ above; summing gives $$Q^{\ast}$$, and plugging into demand gives $$p^{\ast}$$. The interior requirement is $$A>c$$ so that each firm’s output is strictly positive.

***

### (c) Cournot with nnn identical firms and the perfect-competition limit

* Write profit and the reaction (best-response) function for firm $$i$$ against rivals’ total output.
* Impose symmetry across nnn firms to solve for the Cournot–Nash output, price, and total quantity.
* Show that as $$n \to \infty$$, the market outcome converges to the perfect-competition benchmark.

***

#### Derivation

I use the same linear inverse demand and constant marginal cost setup as before. Let each firm $$i$$ choose quantity $$q_i$$, define rivals’ output by $$q_{-i}$$, and denote aggregate output by $$Q$$. The notes emphasize solving Cournot via each firm’s reaction to rivals. This is where “strategic substitutes” appear: when others produce more, my best response is lower.

$$
\pi_i(q_i,q_{-i})=\big(A-B(q_i+q_{-i})-c\big)\,q_i.
$$

This is firm $$i$$’s profit given rivals’ output. I treat $$q_{-i}$$ as fixed and choose $$q_i$$ to maximize $$\pi_i$$.

$$
\frac{\partial\pi_i}{\partial q_i}=A-c-2Bq_i-Bq_{-i}=0 \quad\Longrightarrow\quad q_i=\frac{A-c-Bq_{-i}}{2B}.
$$

The expression above is the downward-sloping best-response function. It maps any rival output $$q_{-i}$$​ to the $$q_i$$ that maximizes firm $$i$$’s profit.

$$
q_1=\cdots=q_n\equiv q^{\ast},\qquad q_{-i}=(n-1)q^{\ast}.
$$

I now impose symmetry. Each firm chooses the same quantity $$q^{\ast}$$, so rivals’ total is $$(n-1)q^{\ast}$$.

$$
q^{\ast}=\frac{A-c-B(n-1)q^{\ast}}{2B} \quad\Longrightarrow\quad B(n+1)\,q^{\ast}=A-c \quad\Longrightarrow\quad q^{\ast}=\frac{A-c}{B(n+1)}.
$$

This gives the per-firm Cournot quantity. I next aggregate across firms and back out the market price.

$$
Q^{\ast}=n\,q^{\ast}=\frac{n(A-c)}{B(n+1)}, \qquad p^{\ast}=A-BQ^{\ast}=\frac{A+nc}{\,n+1\,}.
$$

These are the equilibrium total output and price when there are nnn identical Cournot competitors. The condition $$A>c$$ guarantees interior quantities for all firms. The part (c) prompt also asks to show the perfect-competition limit; with $$p=MC=c$$ the competitive quantity solves $$A-BQ=c$$, i.e. $$Q=(A-c)/B$$. Taking $$n\to\infty$$ in the Cournot outcome delivers exactly that limit.

$$
\lim_{n\to\infty}p^{\ast}=c, \qquad \lim_{n\to\infty}Q^{\ast}=\frac{A-c}{B}.
$$

Intuitively, as the number of firms grows, each firm’s residual demand becomes flatter, markups are competed away, and the outcome approaches price-taking behavior.

***

#### Answer

$$
q_i^{\ast}=\frac{A-c}{B(n+1)},\qquad Q^{\ast}=\frac{n(A-c)}{B(n+1)},\qquad p^{\ast}=\frac{A+nc}{n+1}, \qquad \lim_{n\to\infty}(p^{\ast},Q^{\ast})=\big(c,\tfrac{A-c}{B}\big).
$$

In words, the reaction-function method yields the per-firm quantity shown above; summing gives total output and substituting into inverse demand gives price. As the number of firms grows without bound, the Cournot outcome converges to the competitive benchmark where price equals marginal cost and total output equals $$(A-c)/B$$.

***

### (d) Efficient outputs with nnn firms and how efficiency changes as nnn grows

* Identify the “most efficient” outputs for the nnn-firm environment in part (c).
* Use two notions of efficiency the notes emphasize: allocative efficiency ($$p=MC$$) and total-surplus maximization.
* Compare the Cournot outcome to the efficient benchmark and show how the gap closes as $$n$$ increases.

***

#### Derivation

**1) Cournot outcome from part (c).**\
With $$n$$ identical firms, linear inverse demand $$p(Q)=A-BQ$$, and constant marginal cost $$c$$, the symmetric Cournot equilibrium is:

$$
q_i^{\ast}=\frac{A-c}{B(n+1)},\qquad Q_n^{\ast}=\frac{n(A-c)}{B(n+1)},\qquad p_n^{\ast}=\frac{A+nc}{\,n+1\,}.
$$

This will be our “market” benchmark to compare against efficiency.

**2) Efficient (first-best) total output.**\
In the surplus-maximization view, a social planner chooses $$Q$$ to maximize total surplus:

$$
TS(Q)=\int_{0}^{Q}\big(A-Bx-c\big)\,dx =(A-c)Q-\frac{B}{2}Q^{2}.
$$

The planner’s first-order condition is:

$$
\frac{d\,TS}{dQ}=A-c-BQ=0 \quad\Longrightarrow\quad Q^{\text{fb}}=\frac{A-c}{B},\qquad p^{\text{fb}}=c.
$$

This coincides with the notes’ allocative-efficiency rule $$p=MC$$. Because all firms have the same constant $$c$$ (no fixed costs here), _any_ split of $$Q^{\text{fb}}$$ across firms is productively efficient; a convenient symmetric choice is:

$$
q_i^{\text{fb}}=\frac{Q^{\text{fb}}}{n}=\frac{A-c}{B\,n}.
$$

**3) How far is Cournot from efficient.**

_**(a) Allocative-efficiency (price–cost wedge):**_

The wedge under Cournot is&#x20;

$$
p_n^{\ast}-c=\frac{A-c}{\,n+1\,},
$$

which shrinks at rate $$1/(n+1)$$ and vanishes as $$n\to\infty$$.



_**(b) Total-surplus loss (deadweight loss):**_

The first-best surplus is

$$
TS^{\text{pc}}=TS(Q^{\text{fb}})=\frac{(A-c)^{2}}{2B}.
$$

Cournot’s total surplus (plug $$Q_n^{\ast}$$​ into $$TS(Q)$$) is

$$
TS_n =\frac{(A-c)^{2}}{B}\cdot\frac{n(n+2)}{2(n+1)^{2}}.
$$

Hence the deadweight loss and the efficiency ratio are

$$
DWL_n=TS^{\text{pc}}-TS_n=\frac{(A-c)^{2}}{2B}\cdot\frac{1}{(n+1)^{2}}, \qquad \frac{TS_n}{TS^{\text{pc}}}=\frac{n(n+2)}{(n+1)^{2}} =1-\frac{1}{(n+1)^{2}}.
$$

So the welfare gap closes _quadratically_ fast in $$n$$.

***

#### Answer

The first-best (efficient) industry output is $$Q^{\text{fb}}=(A-c)/B$$ with $$p^{\text{fb}}=c$$, and—since all firms have identical constant marginal cost—any allocation summing to $$Q^{\text{fb}}$$ is productively efficient (e.g., $$q_i^{\text{fb}}=(A-c)/(B\,n)$$).

Relative to this benchmark, the $$n$$-firm Cournot outcome has a price–cost wedge $$(A-c)/(n+1)$$ and deadweight loss $$(A-c)^{2}/\big(2B\,(n+1)^{2}\big)$$; thus, as $$n$$ grows, the allocative-inefficiency wedge shrinks to zero and total-surplus efficiency converges to one at rate $$1-(n+1)^{-2}$$.

***

***

## Q4: the endogenous cost of searching

***

### (a) Expected payoffs for worker 1 given worker 2 applies to firm 1 with probability π

* Fix notation for the other worker’s mixed strategy.
* Compute worker 1’s expected payoff if they apply to firm 1.
* Compute worker 1’s expected payoff if they apply to firm 2.
* Keep everything as simple functions of $$w_1, w_2,$$ and $$\pi$$.

***

#### Derivation

I let $$\pi\in[0,1]$$ be the probability that worker 2 applies to firm 1, so worker 2 applies to firm 2 with probability $$1-\pi$$. When both workers apply to the same firm, that firm hires one of them at random, so worker 1’s hire probability is $$1/2$$. When only worker 1 applies to a firm, worker 1 is hired for sure. Using “expected payoff = wage × hire probability,” I write the two cases below.

For worker 1 applying to firm 1:

$$
\mathbb{E}[u_1\mid \text{apply to firm 1}] = w_1\Big[(1-\pi)\cdot 1+\pi\cdot \tfrac{1}{2}\Big] = w_1\Big(1-\tfrac{\pi}{2}\Big).
$$

For worker 1 applying to firm 2:

$$
\mathbb{E}[u_1\mid \text{apply to firm 2}] = w_2\Big[\pi\cdot 1+(1-\pi)\cdot \tfrac{1}{2}\Big] = w_2\Big(\tfrac{1}{2}+\tfrac{\pi}{2}\Big).
$$

These expressions come straight from weighting each hiring event by the chance that worker 2 shows up at the same firm versus the other firm.

***

#### Answer

$$
\mathbb{E}[u_1\mid \text{apply to firm 1}] = w_1\Big(1-\tfrac{\pi}{2}\Big),\qquad \mathbb{E}[u_1\mid \text{apply to firm 2}] = w_2\Big(\tfrac{1}{2}+\tfrac{\pi}{2}\Big).
$$

In words, if worker 2 targets firm 1 more often (higher $$\pi$$), worker 1’s expected payoff from applying to firm 1 falls because collisions become more likely, while the expected payoff from applying to firm 2 rises since worker 1 is more often the sole applicant there.

***

### (b) Best response and the indifference cut-off for worker 1

* Use the expected payoffs from part (a) to write worker 1’s best response to $$\pi$$.
* Solve the indifference condition to get the cut-off $$\pi^{\ast}$$.
* State when the best response is a pure action and when mixing is possible.

***

#### Derivation

From part (a), worker 1’s expected payoff if they apply to firm 1 is

$$
\mathbb{E}[u_1 \mid 1]=w_1\Big(1-\tfrac{\pi}{2}\Big).
$$

If worker 1 instead applies to firm 2, the expected payoff is

$$
\mathbb{E}[u_1 \mid 2]=w_2\Big(\tfrac{1}{2}+\tfrac{\pi}{2}\Big).
$$

Worker 1 prefers firm 1 when the first expression is at least as large as the second:

$$
w_1\Big(1-\tfrac{\pi}{2}\Big)\;\ge\;w_2\Big(\tfrac{1}{2}+\tfrac{\pi}{2}\Big).
$$

Bringing terms together and solving for π\piπ gives the best-response cut-off:

$$
2w_1 - w_2\;\ge\;\pi\,(w_1+w_2) \quad\Longrightarrow\quad \pi\;\le\;\frac{2w_1 - w_2}{\,w_1+w_2\,}\;\equiv\;\pi^{\ast}.
$$

Thus the best response is:

$$
text{Choose firm 1 if }\pi<\pi^{\ast},\quad \text{choose firm 2 if }\pi>\pi^{\ast},\quad \text{and mix if }\pi=\pi^{\ast}.
$$

For $$\pi^{\ast}$$ to lie strictly between 0 and 1 (so mixing is feasible), the parameters must satisfy

$$
\frac{w_2}{2}\;<\;w_1\;<\;2w_2.
$$

If $$w_1\ge 2w_2$$​, the best response is firm 1 even when $$\pi=1$$ (both pile onto firm 1); if $$w_2\ge 2w_1$$, the best response is firm 2 even when $$\pi=0$$. This is exactly the “congestion as an endogenous cost” idea: the higher wage attracts applicants, but the collision risk (the $$\tfrac{1}{2}$$ hire chance) pulls back the effective payoff.

***

#### Answer

$$
\pi^{\ast}=\frac{2w_1 - w_2}{\,w_1+w_2\,}.
$$

When $$\pi<\pi^{\ast}$$ worker 1’s best response is to apply to firm 1; when $$\pi>\pi^{\ast}$$ the best response is to apply to firm 2; when $$\pi=\pi^{\ast}$$ worker 1 is indifferent and can mix. An interior cut-off $$\pi^{\ast}\in(0,1)$$ occurs exactly when $$\tfrac{w_2}{2}<w_1<2w_2$$​; otherwise the best response is a pure action toward the higher effective wage.

***

### (c) Symmetric Nash equilibrium and the case breakdown

* Find a symmetric mixed-strategy equilibrium where each worker applies to firm 1 with the same probability.
* State the condition under which interior mixing exists and give the mixing probability.
* Report the worker’s equilibrium expected payoff.
* List the pure-strategy equilibria that arise when wages are very unequal.

***

#### Derivation

From part (b), worker 1 is indifferent between the two firms when the other worker applies to firm 1 with probability $$\pi^{\ast}$$ that solves

$$
w_1\Big(1-\tfrac{\pi}{2}\Big)=w_2\Big(\tfrac{1}{2}+\tfrac{\pi}{2}\Big) \quad\Longrightarrow\quad \pi^{\ast}=\frac{2w_1-w_2}{\,w_1+w_2\,}.
$$

In a symmetric mixed equilibrium, each worker uses the same probability to target firm 1, so the equilibrium mixing probability is exactly

$$
\bar{\pi}=\frac{2w_1-w_2}{\,w_1+w_2\,}.
$$

This $$\bar{\pi}$$ is interior (i.e., in $$(0,1)$$) precisely when wages are not too far apart:

$$
\frac{w_2}{2}\;<\;w_1\;<\;2w_2.
$$

At $$\bar{\pi}$$, both firms give the same expected payoff, so each worker’s equilibrium expected payoff (compute from either firm) is

$$
\mathbb{E}[u]^{\ast} = w_1\Big(1-\tfrac{\bar{\pi}}{2}\Big) = w_2\Big(\tfrac{1}{2}+\tfrac{\bar{\pi}}{2}\Big) = \frac{3\,w_1 w_2}{\,2\,(w_1+w_2)}.
$$

For later intuition, the probability the two workers split across firms (so both get hired) under symmetric mixing is

$$
\Pr[\text{split}]=2\,\bar{\pi}\,(1-\bar{\pi}) =\frac{2\,(2w_1-w_2)\,(2w_2-w_1)}{(w_1+w_2)^2},
$$

which is highest when wages are closer and falls to zero when one wage dwarfs the other.

Finally, when wages are very unequal, the symmetric mix disappears and the game has pure equilibria:

$$
\text{If }w_1\ge 2w_2:\ \text{both apply to firm 1 is a (unique) pure NE;}
$$

$$
\text{if }w_2\ge 2w_1:\ \text{both apply to firm 2 is a (unique) pure NE.}
$$

When $$\tfrac{w_2}{2}<w_1<2w_2$$​, there are also two asymmetric pure equilibria (one worker to each firm), in addition to the symmetric mixed equilibrium above.

***

#### Answer

$$
\bar{\pi}=\frac{2w_1-w_2}{\,w_1+w_2\,},\qquad \mathbb{E}[u]^{\ast}=\frac{3\,w_1 w_2}{\,2\,(w_1+w_2)}.
$$

In words, if wages are not too different $$\big(\tfrac{w_2}{2}<w_1<2w_2\big)$$, there is a symmetric mixed equilibrium where each worker applies to firm 1 with probability $$\bar{\pi}$$ above, making them indifferent between firms. If one wage is at least twice the other, the unique equilibrium is pure, with both workers applying to the higher-wage firm.

***

### (d) Firms set wages first; equilibrium wages and efficiency

* Treat wage setting as Stage 1 and the workers’ application game as Stage 2 (same as parts (a)–(c)).
* Write each firm’s expected profit as a function of its wage and the workers’ mixing in Stage 2.
* Solve the symmetric Nash equilibrium wages $$w_1^{\ast}, w_2^{\ast}$$​.
* Discuss efficiency under (i) “how many hires happen” and (ii) “total surplus” views.

***

#### Derivation

Stage 2 (workers). For given wages $$w_1, w_2$$​, an interior mixed equilibrium makes each worker indifferent across firms. This is the usual “equalize expected payoffs” condition for mixed strategies from the notes.

$$
\pi\;\equiv\;\Pr(\text{apply to firm 1})=\frac{2w_1-w_2}{\,w_1+w_2\,}\quad\text{(interior case, }w_2/2<w_1<2w_2\text{).}
$$

Given $$\pi$$, firm 1 receives at least one applicant with probability $$1-(1-\pi)^2$$; if it gets at least one, it hires exactly one worker and earns $$R-w_1$$. Thus its expected profit is

$$
\Pi_1(w_1;w_2)=(R-w_1)\,\big[1-(1-\pi)^2\big].
$$

By symmetry, firm 2’s profit is

$$
\Pi_2(w_2;w_1)=(R-w_2)\,\big[1-\pi^2\big].
$$

Stage 1 (firms). In a symmetric candidate $$w_1=w_2=w$$, we have $$\pi=\tfrac12$$​ and the “at least one applicant” probability equals $$1-(1-\tfrac12)^2=\tfrac34$$​. Each firm then solves

$$
\max_{w\ge 0}\ \Pi(w)=(R-w)\cdot\tfrac34.
$$

Raising $$w$$ increases the chance of getting an applicant but lowers the margin; the best response balances these two effects. A quick first-order condition around the symmetric path (using $$\pi=\tfrac12$$​ and $$\tfrac{\partial}{\partial w}[1-(1-\pi)^2]=\tfrac{3}{4w}$$​ at symmetry) gives

$$
0=\frac{d\Pi}{dw}=-\tfrac34+\Big(R-w\Big)\frac{3}{4w}\quad\Longrightarrow\quad R-w=w.
$$

At $$w_1^{\ast}=w_2^{\ast}=\tfrac{R}{2}$$​, each firm’s hire probability is $$\tfrac34$$​. Profits and worker payoffs are therefore

$$
\Pi_1^{\ast}=\Pi_2^{\ast}=\Big(R-\tfrac{R}{2}\Big)\cdot\tfrac34=\frac{3R}{8},\qquad \mathbb{E}[u_\text{worker}]^{\ast}=\frac{3\,w^{\ast}}{4}=\frac{3R}{8}.
$$

These formulas use exactly the hiring rule and timing stated in Q4(d) (firms pick wages first; a hire yields revenue $$R$$; otherwise zero).

#### Efficiency (two lenses)

First, “how many hires happen (allocative view).” With two workers and two firms, the expected number of hires under a symmetric mix $$\pi$$ is

$$
\mathbb{E}[\text{hires}]=1+2\pi(1-\pi),
$$

which is maximized at $$\pi=\tfrac12$$​. At the equilibrium wages $$w_1^{\ast}=w_2^{\ast}=\tfrac{R}{2}$$​, we indeed have $$\pi=\tfrac12$$ and thus $$\mathbb{E}[\text{hires}]=1.5$$. This is the _most_ hiring one can get from independent (uncorrelated) applications; the absolute first-best “two hires for sure” would require coordination to avoid collisions.

Second, “total surplus (firms + workers).” Wages are transfers between firms and workers, so expected total surplus equals $$R$$ times the expected number of hires. At $$w^{\ast}=R/2$$, total surplus is

$$
TS^{\ast}=R\times 1.5=\frac{3R}{2},
$$

which is the maximum attainable under independent mixing (same reason as above). It is below the coordinated first-best $$2R$$ because congestion (both apply to one firm) sometimes wastes a potential hire—this is the “endogenous search friction” at work.

***

#### Answer

$$
w_1^{\ast}=w_2^{\ast}=\frac{R}{2},\qquad \Pi_1^{\ast}=\Pi_2^{\ast}=\frac{3R}{8},\qquad \mathbb{E}[u_\text{worker}]^{\ast}=\frac{3R}{8}.
$$

Each firm posts $$R/2$$; workers then mix with $$\pi=\tfrac12$$​, so each firm hires with probability $$\tfrac34$$​. The outcome maximizes expected hires (and thus total surplus) among independent application strategies, but it still falls short of the coordinated first-best that would split applicants deterministically across firms.

***

***

## Q5: a three players’ game

***

* Lay out the payoff tables exactly as in the question (payoffs ordered: MBC, SBS, KBS).
* Read best responses cleanly and find all pure-strategy Nash equilibria.
* Comment on efficiency (utilitarian sum vs. Pareto).

***

#### Payoff tables

**KBS = 6:00 (upper panel)**

|              | SBS 6:00     | SBS 7:00     |
| ------------ | ------------ | ------------ |
| **MBC 6:00** | (14, 24, 32) | (8, 30, 27)  |
| **MBC 7:00** | (30, 16, 24) | (13, 12, 50) |

**KBS = 7:00 (lower panel)**

|              | SBS 6:00     | SBS 7:00     |
| ------------ | ------------ | ------------ |
| **MBC 6:00** | (16, 24, 30) | (30, 16, 24) |
| **MBC 7:00** | (30, 23, 14) | (14, 24, 32) |

#### Derivation

#### Step 1. KBS’s best response (compare payoffs across panels)

For each (MBC, SBS), KBS earns more at **6:00** than at 7:00.

| (MBC, SBS)   | KBS @6:00 | KBS @7:00 | Better |
| ------------ | --------- | --------- | ------ |
| (6:00, 6:00) | 32        | 30        | 6:00   |
| (6:00, 7:00) | 27        | 24        | 6:00   |
| (7:00, 6:00) | 24        | 14        | 6:00   |
| (7:00, 7:00) | 50        | 32        | 6:00   |

So 6:00 is a dominant action for KBS. Any Nash equilibrium must be in the upper panel. (Definition: in a NE, each player’s action is a best response to the others.)

#### Step 2. MBC vs. SBS within the upper panel (KBS fixed at 6:00)

**MBC best responses** (read MBC’s first payoff in each cell):

| SBS fixed | MBC @6:00 | MBC @7:00 | BR(MBC) |
| --------- | --------- | --------- | ------- |
| 6:00      | 14        | 30        | 7:00    |
| 7:00      | 8         | 13        | 7:00    |

**SBS best responses** (read SBS’s second payoff in each cell):

| MBC fixed | SBS @6:00 | SBS @7:00 | BR(SBS) |
| --------- | --------- | --------- | ------- |
| 6:00      | 24        | 30        | 7:00    |
| 7:00      | 16        | 12        | 6:00    |

The only mutual best-response intersection is (MBC 7:00, SBS 6:00) in the upper panel (payoffs 30, 16, 24). That profile is a pure-strategy Nash equilibrium.

#### Efficiency

* **Utilitarian (sum of audiences).** \
  At the NE, the total is $$30+16+24=70$$. The highest total in the tables is 75 at (MBC 7:00, SBS 7:00, KBS 6:00), so the NE is not utilitarian-efficient.
* **Pareto.** \
  No other profile weakly improves all three players relative to $$(30,16,24)$$, so the NE is Pareto-undominated among the listed outcomes.

***

#### Answer

**Nash equilibrium:** (MBC 7:00, SBS 6:00, KBS 6:00) with payoffs (30, 16, 24).\
**Why:** KBS has a dominant action (6:00), and given KBS=6:00 the MBC–SBS 2×2 has a single mutual best-response cell at (7:00, 6:00).\
**Efficiency:** Not utilitarian-efficient (total 70 vs. max 75), but Pareto-undominated within the table.

Time-slot choices impose cross-audience externalities; the equilibrium is privately stable but socially suboptimal because each network ignores the harm to rivals’ audience.

***











