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
$E[X] = \sum{}

