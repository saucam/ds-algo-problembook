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

Recall that the [expected value of a random variable](https://en.wikipedia.org/wiki/Expected_value) <img src="/contents/codeforces/453A/tex/cbfb1b2a33b28eab8a3e59464768e810.svg?invert_in_darkmode&sanitize=true" align=middle width=14.908688849999992pt height=22.465723500000017pt/> is given by

<img src="/contents/codeforces/453A/tex/f850926f1eb658f5afa30f085a8dc6ae.svg?invert_in_darkmode&sanitize=true" align=middle width=190.15185914999998pt height=24.657735299999988pt/>

Here,

<img src="/contents/codeforces/453A/tex/3bc6fc8b86b6c61889f4e572c7546b8e.svg?invert_in_darkmode&sanitize=true" align=middle width=11.76470294999999pt height=14.15524440000002pt/> is the possible outcome values for the random variable X
and <img src="/contents/codeforces/453A/tex/15a7517df86006453f43e6f70f06556e.svg?invert_in_darkmode&sanitize=true" align=middle width=82.90805819999999pt height=24.65753399999998pt/> is the probability of the outcome <img src="/contents/codeforces/453A/tex/3bc6fc8b86b6c61889f4e572c7546b8e.svg?invert_in_darkmode&sanitize=true" align=middle width=11.76470294999999pt height=14.15524440000002pt/> 

For our case we assume a random variable X that denotes the maximum value of dots rolled in any of the ```n``` rolls of the dice.

Hence, expected value

<img src="/contents/codeforces/453A/tex/b18eda6cfaa6abbc8716e852cfb6cb14.svg?invert_in_darkmode&sanitize=true" align=middle width=203.5341231pt height=31.75825949999999pt/> ....... (A)

To calculate the above expected value, notice that we need the probability of getting maximum value of dots = 1 or 2 or ... m in n rolls of the dice.

To calculate the probability of getting maximum value of dots = 1 in n rolls, we need

<img src="/contents/codeforces/453A/tex/6c17642a778f29b8e0b4568b038cfbde.svg?invert_in_darkmode&sanitize=true" align=middle width=388.62864809999996pt height=30.648287999999997pt/>

Number of possible outcomes with maximum dots 1 is only 1 case where, in all the n rolls we get 1 as the outcome

roll 1 outcome = 1

roll 2 outcome = 1 ...

..

roll n outcome = 1

Total possible outcomes for n roll of the dice = <img src="/contents/codeforces/453A/tex/b9a75e2202835f4e29abfe4b445fcbe8.svg?invert_in_darkmode&sanitize=true" align=middle width=22.559123399999994pt height=21.839370299999988pt/>

Therefore,

<img src="/contents/codeforces/453A/tex/89adced63b7799245e1fb145aead9414.svg?invert_in_darkmode&sanitize=true" align=middle width=139.45584014999997pt height=24.65753399999998pt/>

Now to calculate the number of possible outcomes with maximum dots 2 in n rolls, we can get it by calculating the possible outcomes where each outcome is atmost 2 and subtract from it the number of possible outcomes where each outcome is atmost 1, which equals

<img src="/contents/codeforces/453A/tex/0e813182f6c3822900fbaa532431d793.svg?invert_in_darkmode&sanitize=true" align=middle width=45.47754749999999pt height=21.839370299999988pt/>

(Number of possible outcomes where each outcome is atmost 2 = <img src="/contents/codeforces/453A/tex/f8f25e4580c418a51dc556db0d8d2b93.svg?invert_in_darkmode&sanitize=true" align=middle width=16.34523329999999pt height=21.839370299999988pt/> since for each outcome we have 2 choices, either it can be 1 or 2)

Hence,

<img src="/contents/codeforces/453A/tex/79a7792bee590e5331cb6aca6e6e9574.svg?invert_in_darkmode&sanitize=true" align=middle width=189.49961249999998pt height=24.65753399999998pt/>

Similarily to calculate the number of possible outcomes with maximum dots 3 in n rolls, we can get it by calculating the possible outcomes where each outcome is atmost 3 and subtract from it the number of possible outcomes where each outcome is atmost 2, which equals

<img src="/contents/codeforces/453A/tex/517e80807af6ddf3220404e8a0157e33.svg?invert_in_darkmode&sanitize=true" align=middle width=53.60357144999999pt height=21.839370299999988pt/>

Hence,

<img src="/contents/codeforces/453A/tex/8d6d20248b92e2162e818dabc1e9f7a6.svg?invert_in_darkmode&sanitize=true" align=middle width=198.4475493pt height=24.65753399999998pt/>

And so on.

Substituting these values in equation (A), we get

<img src="/contents/codeforces/453A/tex/6f5dfad70a619b1a798c534bc106d6fb.svg?invert_in_darkmode&sanitize=true" align=middle width=261.52255799999995pt height=31.75825949999999pt/>

which is the same formulae given in the tutorial.

### Code

Just for completion sake, [here is the complete code](https://github.com/saucam/code/blob/master/codeforces/practice/453A/pony.cpp) though you are highly encouraged to only read this tutorial and get the solution accepted.