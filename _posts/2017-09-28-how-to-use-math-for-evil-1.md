---
layout: post
title:  "How to use math for evil I: Statistics"
date:   2017-09-28 12:50:45 +0100
categories: data
---

*This is an expanded version of the general audience talk I'm giving at the Science on Tap--formerly known as Drunk on Science, which is much cooler but probably less professional--in Pune, the brainchild of the illustrious Anoop Mahajan, with craft beer sponsored by Great State Ale Works! See [Part 1](2017-09-28-how-to-use-math-for-evil-1), [Part 2](2017-09-30-how-to-use-math-for-evil-2), [Part 3](2017-10-03-how-to-use-math-for-evil-3), [Part 4]()*

Okay. So let's talk about numbers. They're everywhere around us; from the statistics that are served to us, to the many algorithms that mediate our technological lives, more and more they influence our lives without our knowing. Of course, numbers by themselves seem innocent enough. Especially as a pure mathematician, I can readily say that mathematicians like to think—wrongly, of course—that the mathematics they pursue is a about beauty and truth, and has little bearing on society. In this series of posts, we'll look at various ways this rosy view of mathematics is patently false, that instead the pursuit of mathematics pure and applied is deeply entangled in worldly affairs.

More to the point, we'll talk about how numbers can be used for evil. Numbers are used to represent, rather the way photographs are. Now, the first obvious misuse is when the numbers are doctored, like how a photograph might be edited and distorted by Photoshop; or secondly, and less obvious, is when the numbers are accurate but don't capture the whole picture, as it could literally happen with photographs. In each case, the representation is used to advance a predetermined agenda, at the expense of truth.

> 'There are three kinds of lies: Lies, damned lies, and statistics.' -- Source unknown

In this first post, we'll warm up by starting before the age of the personal computer, and talk about statistics. Most of this will be taken from the classic text *How to lie with statistics* by Darrell Huff.

#### 1. Sampling bias

The first in line can be a rather devious way of skewing statistical results, it is also pitfall that one might encounter if not careful enough. [Sampling bias](https://en.wikipedia.org/wiki/Sampling_bias) describes how statistical results can be affected by the sample that is chosen for study, leading to inaccurate results. In this case, the sample is not chosen at random. For example, we might intentionally choose to poll people whose opinions support the conclusion that we would like to draw.

This can also be done by cherry-picking data, or discarding unfavorable data. We call this [post-hoc](https://en.wikipedia.org/wiki/Post_hoc_analysis) alteration of data.

On the other hand, kind of like the Heisenberg uncertainty principle in particle physics, it can be that the sample that being studied can be affected by the fact that they are being studied, which is related to the well-known placebo effect, for example. Also, loaded questions can prime a interviewee to respond in a certain way.

#### 2. The well-chosen average

This one is a pretty straightforward trick, and you've probably learned this once before in primary school. It's essentially the difference between mean, median or mode, each of which might be considered an '[average](https://en.wikipedia.org/wiki/Average)' value. Here's a quick refresher: Suppose you have a string of 10 numbers:

1, 1, 2, 5, 6, 7, 8, 8, 8, 9

The *mean* is the sum total, divided by the number of term; in this case, 5.5. This is *usually* what one means by the word 'average', for example, what is meant by miles per hour, or kilogram per dollar, and so on; a simple addition and division.

The *mode* is the number that appears the most often in this set, in this case, 8.

The *median* is the value that appears in the 'middle', in the sense that we've observed the values 1, 2, 5, 6, 7, 8, and 9, so the middle value is 6.

One can make a case for each of these to be a numerical 'average', and the idea of the well-chosen average is simply that you could choose to report any of the three possibilities as the 'average', depending on which best suits your purpose.

#### 3. The confidence interval

This next one is probably the trickiest, but really it's behind many of the (pseudo)tests we take, and the statistics that we read about. The long and short of it is this: it is almost impossible to poll the entire population sample that you are trying to measure; for example, you'll be hard pressed to poll every single person in your town on which presidential candidate is the better one, or at least, the lesser of two evils. What you do is go out and take survey a sample of the population (which had better be properly random or you'll end up back in Problem 1 above). The larger your sample size, the better chances you have of getting polls that reflect your town's population.

This is quantified as a [confidence interval](https://en.wikipedia.org/wiki/Confidence_interval), or standard error. Now take care: it's not an error in the sense of a mistake, but rather a feature of statistical methods for the reason I just told you. By right, these are the pluses and minuses you should see next to percentages, and error bars on bar charts. These are also just the kind of numbers you don't usually see in statistical reporting. And that's the trouble. With numbers like your [IQ](https://en.wikipedia.org/wiki/IQ) or [BMI](https://en.wikipedia.org/wiki/Body_mass_index), the exact values don't matter so much as the ranges. 

You should probably just watch this cute animation explaining the [Central Limit Theorem](http://www.nytimes.com/2013/09/24/science/as-normal-as-rabbits-weights-and-dragons-wings.html) using rabbits and dragons! The central limit theorem and other mathematically rigorous tools can help us to build confidence intervals.

#### 4. Misleading graphics

This one is somewhat self-explanatory, and is more of an advertising issue rather than a true statistical fallacy: presenting data with misleading graphics. This can take the form of improper scaling, truncated graphs, not having a scale, changing measurements. See for example, the Wikipedia page on [misleading graphs](https://en.wikipedia.org/wiki/Misleading_graph).

A toy example is when a single candy bar's nutrition facts describes itself as having say, 100 calories per serving. You might, as the manufacturer would like you to, only see this number and feel good about eating a 100 calorie candy bar, while in fact you are eating *four* servings, so 400 calories!

#### 5. Causation and correlation

This last one is pretty well-known, so I'll just point to a few fun examples: An entertaining collection of graphs showing [Spurious Correlations](http://www.tylervigen.com/spurious-correlations), an [xkcd comic](https://xkcd.com/552/), and an actually published paper on ['The Effect of Country Music on Suicide'](http://comp.uark.edu/~ches/CountryMusic_Suicide.pdf) (Sack and Gundlach, 1992), that suicide rates among white people increased with the amount of airtime dedicated to country music. The reported (but not interpreted) correlation was a whopping r = 0.54.

#### Last thoughts

Finally, as a handy guide to readers, Huff gives us some pointers on `how to talk back to a statistic', with a set of five questions, when faced with a statistic: 

- Who says so?
- How do they know?
- Did they change the subject?
- Does it make sense? 

So we've seen what sort of trickery can be done even without the use of very much technology. Next we'll take a look at what happens when you throw in computers and the internet into the mix. On to Part 2!