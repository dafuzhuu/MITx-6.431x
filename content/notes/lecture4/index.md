+++
title = 'Lec. 4: Counting'
date = 2024-09-24T19:59:01+08:00
draft = false
math = true
+++

{{< youtube poeHeiiiLKI >}}

## Coin tossing

Use the second method in the preceding segment to find the probability that the 6th toss out of a total of 10 tosses is Heads, given that there are exactly 2 Heads out of the 10 tosses. As in the preceding segment, continue to assume that all coin tosses are independent and that each coin toss has the same fixed probability of Heads. (In this and subsequent questions, your answer should be a number. Do not enter ‘!' or combinations in your answer.) 

**Step 1: Total possible outcomes**

First, let's consider the total number of possible ways to have exactly 2 Heads out of 10 tosses. This is given by:

`$$
\binom{10}{2} = \frac{10!}{2!(10-2)!} = \frac{10 \times 9}{2 \times 1} = 45
$$`

So there are 45 possible ways to get exactly 2 Heads out of 10 tosses.

**Step 2: Favorable outcomes**

Next, we want to calculate how many of these outcomes have the 6th toss as a Head. If the 6th toss is fixed as a Head, we now need to place 1 additional Head among the remaining 9 tosses. The number of ways to do this is:

`$$
\binom{9}{1} = \frac{9!}{1!(9-1)!} = 9
$$`

So there are 9 favorable outcomes where the 6th toss is a Head and exactly 2 Heads in total.

**Step 3: Calculate the probability**

The conditional probability that the 6th toss is a Head, given that there are exactly 2 Heads in 10 tosses, is the ratio of favorable outcomes to total outcomes. This is:

`$$
P(\text{6th toss is Head | exactly 2 Heads}) = \frac{\text{favorable outcomes}}{\text{total outcomes}} = \frac{9}{45} = \frac{1}{5}
$$`

The probability is `$ \frac{1}{5} $` or 0.2.

## Counting committees

We start with a pool of `$ n $` people. A chaired committee consists of `$ k \geq 1 $` members, out of whom one member is designated as the chairperson. The expression `$ k \binom{n}{k} $` can be interpreted as the number of possible chaired committees with `$ k $` members. This is because we have `$ \binom{n}{k} $` choices for the `$ k $` members, and once the members are chosen, there are then `$ k $` choices for the chairperson. Thus,

`$$
c = \sum_{k=1}^{n} k \binom{n}{k}
$$`

is the total number of possible chaired committees of any size.

Find the value of `$ c $` (as a function of `$ n $`) by thinking about a different way of forming a chaired committee: first choose the chairperson, then choose the other members of the committee. The answer is of the form

`$$
c = (\alpha + n^\beta) 2^{\gamma n + \delta}.
$$`

What are the values of `$ \alpha $`, `$ \beta $`, `$ \gamma $`, and `$ \delta $`? 

---

We are given the sum

`$$
c = \sum_{k=1}^{n} k \binom{n}{k}
$$`

representing the total number of possible chaired committees of any size. Our goal is to express `$ c $` in the form:

`$$
c = (\alpha + n^\beta) 2^{\gamma n + \delta}
$$`

To solve this, we need to think of the process of forming a chaired committee in two steps:

1. Choose a chairperson from `$ n $` people. This gives us `$ n $` possible choices for the chairperson.
2. After choosing the chairperson, choose a **subset of the remaining** `$ n-1 $` people (possibly empty) to form the rest of the committee.

Thus, for each choice of a chairperson, the number of ways to choose the remaining committee members is the number of subsets of the remaining `$ n-1 $` people, which is `$ 2^{n-1} $`.

Hence, the total number of chaired committees is:

`$$
c = n \cdot 2^{n-1}
$$`

Now, we need to express this in the form:

`$$
c = (\alpha + n^\beta) 2^{\gamma n + \delta}
$$`

We can rewrite `$ c = n \cdot 2^{n-1} $` as:

`$$
c = n \cdot 2^{n} \cdot 2^{-1}
$$`

This gives us:

`$$
c = \frac{n}{2} \cdot 2^n
$$`

Comparing this with the desired form `$ c = (\alpha + n^\beta) 2^{\gamma n + \delta} $`, we can deduce the following values for the constants:

- `$ \alpha = 0 $`
- `$ \beta = 1 $`
- `$ \gamma = 1 $`
- `$ \delta = -1 $`

The values of the constants are:

`$$
\alpha = 0, \quad \beta = 1, \quad \gamma = 1, \quad \delta = -1
$$`

## Hat in a box

Each one of n persons, indexed by 1,2,...,n, has a clean hat and throws it into a box. The persons then pick hats from the box, at random. Every assignment of the hats to the persons is equally likely. In an equivalent model, each person picks a hat, one at a time, in the order of their index, with each one of the remaining hats being equally likely to be picked. Find the probability of :

Each one of persons 1,...,m gets back a hat belonging to one of the last m persons

To find the probability that each of the first `$ m $` persons gets back a hat belonging to one of the last `$ m $` persons, we can analyze the situation step-by-step.

Let the set of `$ n $` persons be denoted as `$ P_1, P_2, \ldots, P_n $`, with hats `$ H_1, H_2, \ldots, H_n $` corresponding to each person. We are particularly interested in the first `$ m $` persons (denote them as `$ P_1, P_2, \ldots, P_m $`) and the last `$ m $` persons (denote them as `$ P_{n-m+1}, P_{n-m+2}, \ldots, P_n $`).

### Total Outcomes

1. The total number of ways to assign hats to `$ n $` persons is `$ n! $`.

### Favorable Outcomes

2. We need to count the favorable outcomes where `$ P_1, P_2, \ldots, P_m $` receive hats only from the set `$ \{H_{n-m+1}, H_{n-m+2}, \ldots, H_n\} $`.

   - The hats available for `$ P_1, P_2, \ldots, P_m $` are exactly `$ H_{n-m+1}, H_{n-m+2}, \ldots, H_n $`. Each of these `$ m $` persons must choose one of the `$ m $` hats.

   - The number of ways to assign these `$ m $` hats to `$ m $` persons is `$ m! $`.

3. The remaining `$ n - m $` persons can receive hats from any of the `$ n - m $` remaining hats (the hats belonging to `$ P_1, P_2, \ldots, P_m $`). The number of ways to assign these hats is `$ (n-m)! $`.

### Combining Outcomes

4. Therefore, the total number of favorable outcomes where `$ P_1, P_2, \ldots, P_m $` get hats from `$ H_{n-m+1}, H_{n-m+2}, \ldots, H_n $` is:
   `$$
   m! \times (n-m)!
   $$`

### Probability Calculation

5. The probability `$ P $` that each of the first `$ m $` persons gets back a hat belonging to one of the last `$ m $` persons is given by the ratio of favorable outcomes to total outcomes:
   `$$
   P = \frac{m! \times (n-m)!}{n!}
   $$`

6. We can simplify this expression:
   `$$
   P = \frac{m! \times (n-m)!}{n \times (n-1) \times (n-2) \times \ldots \times (m+1) \times m!} = \frac{(n-m)!}{n \times (n-1) \times (n-2) \times \ldots \times (m+1)}
   $$`

Thus, the final probability is:
`$$
P = \frac{m! \times (n-m)!}{n!} = \frac{\displaystyle{1}}{\displaystyle{n \choose m}}
$$`
