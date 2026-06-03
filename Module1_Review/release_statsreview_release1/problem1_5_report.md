# Problem 1.5 Written Report

## 1. How to Read the Ioannidis Paper

The paper is John P. A. Ioannidis, “Why Most Published Research Findings Are False,” published in *PLOS Medicine* in 2005. The article is not mainly an empirical paper; it is a conceptual and probabilistic model of when a published “positive” research finding is likely to be true.

I would read it in four passes:

1. First read the abstract and identify the main claim: a published statistically significant result is not automatically likely to be true. Its truth probability depends on pre-study odds, statistical power, significance level, bias, and repeated testing by many teams.
2. Then read the section “Modeling the Framework for False Positive Findings.” This is the mathematical core. Track the meanings of \(R\), \(\alpha\), \(\beta\), power \(1-\beta\), and PPV.
3. Next read the bias and multiple-team sections. These explain why selective reporting, flexible analysis, and many independent teams chasing significance can reduce the probability that a claimed finding is true.
4. Finally read the corollaries critically. They are the interpretation layer: smaller studies, smaller effects, low prior probability, flexible analysis, conflicts of interest, and “hot” fields all tend to lower PPV.

The core idea is Bayesian in spirit: a p-value controls long-run error under a null model, but it does not by itself tell us the probability that a finding is true. A finding is credible only when the pre-study odds \(R\), power, error rates, and research process are all favorable.

## 2. Answers to Problem 1.5

### Part (1)

Let

\[
R=\frac{\text{number of true relationships}}{\text{number of no relationships}}.
\]

If the number of no relationships is \(N\), then the number of true relationships is \(RN\), and the total number of relationships tested is \(RN+N=(R+1)N\). Therefore the pre-study probability that a tested relationship is true is

\[
\boxed{\frac{R}{R+1}}.
\]

### Part (2)

Field A has the higher \(R\). Field A has stronger background knowledge and a smaller, more focused research community, so the hypotheses tested are more pre-selected and more likely to correspond to true relationships. Field B is exploratory and tests many possible genetic relationships, so the ratio of true to non-true relationships is lower.

### Discussion (3)

The positive predictive value, PPV, is the probability that a claimed research finding is actually true:

\[
\mathrm{PPV}
=P(\text{relationship exists}\mid \text{claim relationship}).
\]

Using Bayes' rule,

\[
\mathrm{PPV}
=\frac{P(\text{relationship exists})P(\text{claim}\mid \text{relationship exists})}
{P(\text{relationship exists})P(\text{claim}\mid \text{relationship exists})+
P(\text{no relationship})P(\text{claim}\mid \text{no relationship})}.
\]

Here

\[
P(\text{relationship exists})=\frac{R}{R+1},\quad
P(\text{no relationship})=\frac{1}{R+1},
\]

\[
P(\text{claim}\mid \text{relationship exists})=1-\beta,\quad
P(\text{claim}\mid \text{no relationship})=\alpha.
\]

So

\[
\mathrm{PPV}
=\frac{\frac{R}{R+1}(1-\beta)}
{\frac{R}{R+1}(1-\beta)+\frac{1}{R+1}\alpha}
=\boxed{\frac{R(1-\beta)}{R(1-\beta)+\alpha}}.
\]

### Part (4)

Field A's publications have a higher chance of being true. From

\[
\mathrm{PPV}=\frac{R(1-\beta)}{R(1-\beta)+\alpha},
\]

if \(\alpha\) and power \(1-\beta\) are comparable across the two fields, PPV increases with \(R\). Since Field A has higher \(R\), its significant findings should have higher PPV.

### Part (5)

The problem gives \(\alpha=0.05\), power \(1-\beta=0.7\), and says 20% of proposed relationships are true:

\[
\frac{R}{R+1}=0.20.
\]

Solving gives

\[
R=\frac{0.20}{0.80}=0.25.
\]

The ratio in the problem is

\[
\rho=\frac{R(1-\beta)}{R+\alpha}.
\]

Therefore

\[
\rho=\frac{0.25\cdot 0.7}{0.25+0.05}
=\frac{0.175}{0.30}
=\boxed{0.583}.
\]

Since \(0.583>0.20\), statistical testing helps in this scenario. The test increases the fraction of retained claims that are true, although it still discards some true relationships.

### Part (6)

In this scenario all proposed relationships are true, so the pre-study probability is 1. There are no false relationships to filter out. A statistical test with power 0.7 keeps only 70% of the true relationships and incorrectly discards the remaining 30%. Therefore

\[
\boxed{\rho=0.700}.
\]

Testing does not help them, because they already start from a perfect set of true hypotheses. The test can only remove true relationships.

### Discussion (7): Bias Formula

Let \(u\) be the fraction of tested relationships that are reported as positive because of bias, regardless of what the statistical test would have concluded. The PPV with bias is

\[
\mathrm{PPV}_{bias}
=
\frac{uR+(1-u)R(1-\beta)}
{u(1+R)+(1-u)R(1-\beta)+(1-u)\alpha}.
\]

This formula shows why bias is dangerous: it increases reported positive findings even when the evidence is not genuinely significant. This inflates the denominator of claimed findings and lowers the proportion of those claims that are true.

### Part (8)

If \(n\) independent teams test the same hypothesis and the community pays attention when at least one team obtains significance, then

\[
P(\text{at least one significant}\mid \text{true})
=1-\beta^n,
\]

and

\[
P(\text{at least one significant}\mid \text{no relationship})
=1-(1-\alpha)^n.
\]

Thus

\[
\mathrm{PPV}_{any}
=
\boxed{
\frac{R(1-\beta^n)}
{R(1-\beta^n)+1-(1-\alpha)^n}
}.
\]

As \(n\) increases, the probability of at least one false positive grows. When scientific attention goes to the first significant result, repeated testing by many teams can make a claim less reliable, because isolated positive results become easier to obtain by chance.

### Part (9)

Treat bias and repeated teams separately. Bias does not decrease PPV only in the unusual case where the test has power no larger than the Type I error rate:

\[
1-\beta\le \alpha.
\]

With the conventional \(\alpha=0.05\), this means power would have to be at most 0.05, which is essentially an uninformative test. Similarly, increasing the number of teams testing the same hypothesis does not decrease PPV only when

\[
1-\beta\le \alpha.
\]

In ordinary research, power is supposed to be much larger than \(\alpha\), so both bias and many independent teams chasing a single significant result tend to reduce PPV.

### Part (10)

The critique of Table 3 is that science often requires replication. If \(n\) independent teams test the same hypothesis and the community accepts the claim only when all \(n\) teams find significance, then

\[
P(\text{all significant}\mid \text{true})=(1-\beta)^n,
\]

and

\[
P(\text{all significant}\mid \text{no relationship})=\alpha^n.
\]

Therefore the PPV under unanimous replication is

\[
\boxed{
\mathrm{PPV}_{all}
=
\frac{R(1-\beta)^n}
{R(1-\beta)^n+\alpha^n}
}.
\]

This model is much more favorable to truth than the “at least one team significant” model. If power is much larger than \(\alpha\), then \(\alpha^n\) shrinks far faster than \((1-\beta)^n\), so requiring replication sharply reduces false positives.

### Part (11)

Even with no bias and no teams racing for the same test, publications can still be more likely false than true. The key condition is

\[
\mathrm{PPV}>0.5
\quad\Longleftrightarrow\quad
R(1-\beta)>\alpha.
\]

Thus there is no universal answer. In confirmatory fields with high \(R\), strong power, and a strict \(\alpha\), published significant findings can be more likely true. But in exploratory fields where many random relationships are tested, \(R\) may be extremely small. Then even honest, unbiased studies can produce mostly false positive published claims, because the base rate of true relationships is too low.

### Part (12)

Making scientific claims based mainly on p-values affects \(\alpha\), the probability of declaring a relationship when no true relationship exists. If researchers use a fixed \(p<0.05\) threshold, then \(\alpha=0.05\) for a single clean test. But if they probe many random relationships, try many analyses, or report only significant results, the effective \(\alpha\) becomes much larger.

If scientists probe random relationships, then \(R\) is also very small. In the PPV formula

\[
\mathrm{PPV}
=\frac{R(1-\beta)}{R(1-\beta)+\alpha},
\]

small \(R\) and inflated \(\alpha\) both reduce PPV. Therefore a p-value should not be treated as a certificate of truth. It is evidence only within a testing procedure, and it must be interpreted together with prior plausibility, power, multiple testing, and bias.

## 3. Short Summary of the Paper's Core Thought

Ioannidis argues that many published findings are false not because every scientist is dishonest, but because the research system often combines low prior probabilities, low power, flexible analysis, selective reporting, conflicts of interest, and competition for significant results. The mathematical lesson is simple: a significant p-value is filtered through a noisy research process. If most tested hypotheses are false to begin with, or if researchers repeatedly search until something is significant, the positive results that survive publication can still have low PPV.

The paper's practical message is to prefer well-powered studies, pre-specified hypotheses, replication, transparent reporting, and interpretation based on the totality of evidence rather than isolated p-values.

## Reference

Ioannidis, J. P. A. (2005). *Why Most Published Research Findings Are False*. PLOS Medicine, 2(8), e124. https://doi.org/10.1371/journal.pmed.0020124

