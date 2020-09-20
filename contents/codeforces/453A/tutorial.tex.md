## Tutorial CF 453A
This tutorial explains the solution for [codeforces problem 435A](https://codeforces.com/problemset/problem/453/A)

### Problem in Brief

Given a dice with ```m``` faces, where face ```i``` has ```i``` dots and each face appears with probability ```1/m```, Calculate the expected maximum number of dots one could get after tossing the dice ```n``` times.

### Problem explanation

We have ```m``` faced dice, where face 1 has 1 dot, face 2 has 2 dots... face m has m dots.
When dice is tossed, every face can appear with probability 1/m.
So if dice is tossed once, probability of getting any of 1, 2, ... m is 1/m
Problems asks that if this dice is tossed n times (we could get any of the m faces in each toss) what is the expected maximum dots that will be recorded out of all the n times.

For example, if dice is tossed 3 times, and the results are 4, 1, 7, then maximum value recorded is 7.

### Solution
There is a very [brief tutorial on codeforces](https://codeforces.com/blog/entry/13190), but one might not be able to undestand what is being said, hence this tutorial.

Recall that the expected value of a random variable $X$ is given by
$E[X] = \sum c_i*Pr(X = c_i)$

For our case we assume a random variable X that denotes the maximum value of dots rolled in any of the ```n``` rolls of the dice.

Hence, expected value

$E[X] = \sum_{i=1}^{i=m} i * Pr(X = i) $ ....... (A)

To calculate the above expected value, notice that we need the probability of getting maximum value of dots = 1 or 2 or ... m in n rolls of the dice.

To calculate the probability of getting maximum value of dots = 1 in n rolls, we need

$Pr(X = 1) = \frac{ Number of possible outcomes with maximum dots 1}{Total possible outcomes}$

Number of possible outcomes with maximum dots 1 is only 1 case where in all the n rolls we get 1 as the outcome

roll 1 outcome = 1
roll 2 outcome = 1 ...
..
roll n outcome = 1

Total possible outcomes for n roll of the dice = $m^n$

Therefore,

$Pr(X = 1) = 1/m^n$

Now to calculate the number of possible outcomes with maximum dots 2 in n rolls, we can get it by calculating the possible outcomes where each outcome is atmost 2 and subtract from it the number of possible outcomes where each outcome is atmost 1, which equals

$2^n - 1$

(Number of possible outcomes where each outcome is atmost 2 = $2^n$ since for each outcome we have 2 choices, either it can be 1 or 2)

Hence,

$Pr(X = 2) = (2^n - 1)/m^n$

Similarily to calculate the number of possible outcomes with maximum dots 3 in n rolls, we can get it by calculating the possible outcomes where each outcome is atmost 3 and subtract from it the number of possible outcomes where each outcome is atmost 2, which equals

$3^n - 2^n$

Hence,

$Pr(X = 3) = (3^n - 2^n)/m^n$

And so on.

Substituting these values in equation (A), we get

$E[X] = \sum_{i=1}^{i=m} i * (i^n - (i - 1)^n)/m^n$

which is the same formulae given in the tutorial.

### Code

Just for completion sake, [here is the complete code](https://github.com/saucam/code/blob/master/codeforces/practice/453A/pony.cpp) though you are highly encouraged to only read this tutorial and get the solution accepted.