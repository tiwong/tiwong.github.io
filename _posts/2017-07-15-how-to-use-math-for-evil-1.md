---
layout: post
title:  "How to use math for evil, Part 1: Statistics"
date:   2017-07-15 12:50:45 +0100
categories: data
---

*This is an expanded version of the general audience talk I gave at the Science on Tap--formerly known as Drunk on Science, which is much cooler but probably less professional--in Pune, with craft beer sponsored by Great State Ale Works!*

Okay. So let's talk about numbers. They're everywhere around us; from the statistics that are served to us, to the many algorithms that mediate our technological lives, more and more they influence our lives without our knowing. Of course, numbers by themselves seem innocent enough. Especially as a pure mathematician, I can readily say that mathematicians like to think—wrongly, of course—that the mathematics they pursue is a about beauty and truth, and has little bearing on society. In this series of posts, we'll look at various ways this rosy view of mathematics is patently false, that instead the pursuit of mathematics pure and applied is deeply entangled in worldly affairs.

More to the point, we'll talk about how numbers can be used for evil. Numbers are used to represent, rather the way photographs are. Now, the first obvious misuse is when the numbers are doctored, like how a photograph might be edited and distorted by Photoshop; or secondly, and less obvious, is when the numbers are accurate but don't capture the whole picture, as it could literally happen with photographs. In each case, the representation is used to advance a predetermined agenda, at the expense of truth.

> 'There are three kinds of lies: Lies, damned lies, and statistics.'

In this first post, we'll warm up by starting before the age of the personal computer, and talk about statistics. Most of this will be taken from the classic text 'How to lie with statistics' by Darrell Huff.

#### 1. Sampling Bias

The first in line can be a rather devious way of skewing statistical results, it is also pitfall that one might encounter if not careful enough. Sampling bias describes how statistical results can be affected by the sample that is chosen for study, leading to inaccurate results. The key instance of this we will consider is *sampling bias*: In this case, the sample is not chosen at random. For example, we might intentionally choose to poll people whose opinions support the conclusion that we would like to draw.

This can also be done by cherry-picking data, or discarding unfavorable data. We call this post-hoc alteration of data.

On the other hand, kind of like the Heisenberg uncertainty principle in particle physics, it can be that the sample that being studied can be affected by the fact that they are being studied, which is related to the well-known placebo effect, for example. Also, loaded questions can prime a interviewee to respond in a certain way.

#### 2. The Well-Chosen Average

This one is a pretty straightforward trick, and you've probably learned this once before in primary school. It's essentially the difference between mean, median or mode, each of which might be considered an 'average' value. Here's a quick refresher: Suppose you have a string of 10 numbers:

1, 1, 2, 5, 6, 7, 8, 8, 8, 9

The *mean* is the sum total, divided by the number of term; in this case, 5.5. This is *usually* what one means by the word 'average', for example, what is meant by miles per hour, or kilogram per dollar, and so on; a simple addition and division.

The *mode* is the number that appears the most often in this set, in this case, 8.

The *median* is the value that appears in the 'middle', in the sense that we've observed the values 1, 2, 5, 6, 7, 8, and 9, so the middle value is 6.

One can argue for each of these to be a numerical 'average', and the idea of the well-chosen average is simply that you could choose to report any of the three possibilities as the 'average', depending on which best suits your purpose.

#### 3. Errors

Much Ado about Practically Nothing: probable error and standard error

Central Limit Theorem (http://www.nytimes.com/2013/09/24/science/as-normal-as-rabbits-weights-and-dragons-wings.html)

#### 4. Misleading graphics

Improper scaling, truncated graph, no scale, axis change

#### 5. The Semiattached Figure: false representation

#### 6. Causation and correlation

This last one is pretty well-known, so I'll just point to a few fun examples: An entertaining collection of graphs showing [Spurious Correlations](http://www.tylervigen.com/spurious-correlations), an [xkcd comic](https://xkcd.com/552/), and an actually published paper on ['The Effect of Country Music on Suicide'](http://comp.uark.edu/~ches/CountryMusic_Suicide.pdf) (Sack and Gundlach, 1992), that suicide rates among white people increased with the amount of airtime dedicated to country music. The reported (but not interpreted) correlation was a whopping r = 0.54.

#### Last thoughts

How to Statisticulate: percent, percentage points, percentile. decimal numbers

Finally, as a handy guide to readers, Huff gives us some pointers on `how to talk back to a statistic', with a set of five questions, when faced with a statistic: 

- Who says so?
- How do they know?
- Did they change the subject?
- Does it make sense? 

So we've seen what sort of trickery can be done even without the use of very much technology. Next we'll take a look at what happens when you throw in computers and the internet into the mix. On to Part 2!