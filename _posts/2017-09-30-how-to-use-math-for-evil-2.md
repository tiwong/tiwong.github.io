---
layout: post
title:  "How to use math for evil 2: Algorithms"
date:   2017-09-30 12:50:45 +0100
categories: data
---

*This is an expanded version of the general audience talk I gave at the Science on Tap--formerly known as Drunk on Science, which is much cooler but probably less professional--in Pune, with craft beer sponsored by Great State Ale Works!* 

So last time we looked at how statistics can be used and misused to advance certain agendas. That's ancient history. This time we'll turn our focus to the age of the smart phone: algorithms, and the murky waters of Big Data that they now swim in. 

#### Models and machines

What is an algorithm? At the most basic level, an algorithm is really just a set of instructions that a computer can follow. The bottomline of an algorithm is a bunch of computer code, but the algorithm describes a model, and the model is where it all begins. To emphasise the matter, there is a growing push towards [model-based design](https://www.theatlantic.com/technology/archive/2017/09/saving-the-world-from-code/540393/) as an improvement of current programming practices, where focus is shifted from writing code that works to producing better models.

Let's back track a little, and talk about what a model is. Suppose you want to quantify a certain process, say what are the chances someone surfing the web might click on a particular ad. You'd start with a person X, on a webpage like Facebook. Then based on certain traits measured by say, their web activity and personal information, you'd figure out which kinds of ads they would respond to the best. For example, if you happened to like a lot of pictures with dogs in it, then you might get served more dog ads.

But even this innocuous scenario raises some points about technology that we will look deeper into later: Your user profile and activity are commodities, and are sold as such with Facebook, Google, and Amazon topping the list of data brokers. Of course, as person X, your data is supposedly anonymized so as to protect your privacy, but a general principle in mathematics is that if you know enough properties of an unidentified object, you might in fact be able identify said object uniquely. For example, just knowing one's zip code, birthdate, and sex is enough to identify 87 percent of US citizens ([link](https://arstechnica.com/tech-policy/2009/09/your-secrets-live-online-in-databases-of-ruin/)). But more on this later.

A second point touched on is the ability of a computer to recognise dogs. This is machine learning. It's the idea behind self-driving cars and AI-composed music, which is that given enough historical data, you can teach a computer to generate its own new data. This is what's important with breakthroughs and the buzzword *deep learning*. Getting a computer to [master Go](https://www.scientificamerican.com/article/how-the-computer-beat-the-go-master/) is more sensational than chess is because a computer can easily store all possible chess moves, but there's way too many possibilities in Go, so the computer has to be able to adapt to its opponents specific plays, not having a list of all possible scenarios in hand. Kind of like teaching a car to drive.

Of course, this has led to certain faux pas like Google's recognition software tagging [black people as gorillas](http://www.wnyc.org/story/deep-problem-deep-learning/) and Microsoft's chatbot [turning Nazi](https://www.theverge.com/2016/3/24/11297050/tay-microsoft-chatbot-racist) by learning from Twitter in a day. These are slightly offensive and slightly funny scenarios, but the basic fact is that AI learns from human behaviour (in the form of data), and in the process it learns our biases and bigotries. Interestingly, this is sort of like an automated form of discourse analysis as in Edward Said's conclusion of orientalism of various Western literary works; one could learn to be racist with Twitter as a textbook.

#### Big data in black boxes

Now let's scale up a little, and look at certain algorithms that Cathy O'Neill calls Weapons of Math Destruction, or WMDs for short. This comes from her book *Weapons of Math Destruction: How Big Data Increases Inequality and Threatens Democracy*. In it, she defines a WMD to be an algorithm that has: (1) opacity, (2) scale, and (3) damage. Let's break these down a little.

An algorithm is opaque when its processes or its inner logic, i.e., the model that it operates on, is invisible to the people it is being applied to. For example, most of us don't know how ad services work exactly, though we might have a few guesses. We call this a black box. It's a term in used in computer science and mathematics, to describe a tool which you don't know exactly why or how it works, but you use it anyway, taking for granted that it does because someone else vetted it. Most algorithms that operate in the background of our lives are opaque, under some kind of patent or corporate lock. Importantly, the point is not that everyone can understand it, but if a third party want to audit the code for say, certain biases, they would have access to do so. 

Scale is a simple enough feature: the algorithm must be rolled out at a large scale, so that it is affecting many people, and hence has many potential victims. Which is the third point: damage. The algorithm must be affecting people negatively, and in a way that discriminates against people with particular traits, like race and income. When these three come together, O'Neill calls the algorithm a Weapon of Math Destruction. It has other features, like so-called 'pernicious feedback loops'. That is, the algorithm's success is measured by the results that it gets, and if its results reinforce an inequality, that reproduces more bad data like the kind that went into the model that it was built on in the first place.

Of course, the algorithm's black box is precisely what gives it the impression of impartiality and veracity: it is a machine, so it should be less prone to emotional judgments and prejudices than a human (although the machine itself learned from humans), and that its results are God's truth, since we can't see through the black box, and even if we could we probably wouldn't understand that model or the mathematics behind it all anyway. As they say, the numbers don't lie. Or do they?

#### Some WMDs in the wild

Here's a quick and dirty run through of most of the examples covered in the book:

0. **College rankings**. In 1983, a group of journalists at the US News & World Report came up with a list of measurable criteria, i.e., a  model, for what makes a college or university the 'best'. This set of an arms race among schools to boost performance in these criteria as the rankings became the national standard. One inherent problem is that this measuring stick is not a one-size-fits-all standard: what's best for you is not necessarily what's best for me. Just as this is true in terms of nutrition, so it is in education. At the same time, this sets up a system that can be gamed. For example, certain law schools boosting post-graduation employment rates by giving their own graduates temp jobs.

   The second problem is a simple pernicious feedback-loop: How do the modellers know that their model is accurate? In this case, the rankings would be more credible if they reflect the pre-existing hierarchy. Elite schools, i.e., schools in which children of the elite enrolled, like Harvard and Princeton had to top the list to validate the model. In other words, the rankings perpetuate the existing inequalities and reinforce class lines. Importantly, an important factor that is left out of the rankings is the tuition price. This effectively gives schools permission to raise tuition to generate more revenue to boost performance in the ranking's metrics (which has happened nationwide). 

   Of course, the victims here end up being folks who cannot afford the sticker price on the one hand, being  led into debt, and on the other hand, cannot afford tutors and counsellors who will coach students through the admissions process. Each college has an admissions model tailored to the maximise the college's own rankings, and are mini WMDs in themselves, driving the race for SAT scores and extraordinary extracurriculars. 

1. Recidivism risk. The convict answers a questionnaire that determines the one's risk of committing a crime again. The problem is that the questions collect historical data that is already biased, and is a proxy for racially profiling. Questions like: do you know anyone who has been convicted of a crime, or 

2. Financial crisis: risk, mortgage-backed securities, sub-prime mortgage loans (probability, Black-Scholes) /risk

3. Predatory advertising (pain points, Bayesian stats, big data, machine learning e.g. Siri and language, payday loans, lead generators)

4. Predictive policing (Policing areas leads to negative feedback loops, Broken Windows/zero-tolerance, segregation $\Rightarrow$ geography = proxy for race)

5. Operations research (Kronos, resume screening, Starbucks revenue/employee hour, scheduling software, Value-added school teacher performance measure, logistics)

6. Consumer profiles (Data brokers, credit scores vs e-scores, proxies for job offer/promotions, zipcode profiling, 'buckets', insurance/actuarial science, behavioral data)

7. Voter profiles (A/B testing, Facebook 'I voted!', targeted marketing, swing voters/purchase brand, behavioural/consumer buckets, )

As a silver lining, O'Neill ends with a few examples of good models, models that are being used for good in the world: algorithm audit, slavery model Made in a Free World, homeless recidivism, predictive model for households of child abuse Florida.

> Big Data processes codify the past. They do not invent the future. Doing that requires moral imagination, and that's something only humans can provide. We have to explicitly embed better values into our algorithms, creating Big Data models that follow our ethical lead. Sometimes that will mean putting fairness ahead of profit. -- Cathy O'Neill

#### Mining and spying

Now, the advent of Big Data has not been precipitated so much by the computer or even the internet, but rather the smart phone. The algorithms like the ones described above are contingent upon having troves of data, 

Let's come back to where Big Data comes from. 

[data mining to oil drilling](https://www.theguardian.com/world/2017/aug/23/silicon-valley-big-data-extraction-amazon-whole-foods-facebook)

Algorithms don't kill people; people kill people.

