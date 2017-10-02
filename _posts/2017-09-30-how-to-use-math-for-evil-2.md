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

> Models are opinions embedded in mathematics. -- O'Neil  

Let's back track a little, and talk about what a model is. Suppose you want to quantify a certain process, say what are the chances someone surfing the web might click on a particular ad. You'd start with a person, 'X', on a webpage like Facebook. Then based on certain traits measured by say, their web activity and personal information, you'd figure out which kinds of ads they would respond to the best. For example, if you happened to like a lot of pictures with dogs in it, then you might get served more dog ads.

But even this innocuous scenario raises some points about technology that we will look deeper into later: Your user profile and activity are commodities, and are sold as such with Facebook, Google, and Amazon topping the list of data brokers. Of course, as person X, your data is supposedly anonymised so as to protect your privacy, but a general principle in mathematics is that if you know enough properties of an unidentified object, you might in fact be able identify said object uniquely. For example, just knowing one's zip code, birthdate, and sex is enough to identify 87 percent of US citizens ([link](https://arstechnica.com/tech-policy/2009/09/your-secrets-live-online-in-databases-of-ruin/)). But more on this later. 

A second point touched on is the ability of a computer to recognise dogs. This is machine learning. It's the idea behind self-driving cars and AI-composed music, which is that given enough historical data, you can teach a computer to generate its own new data. This is what's important with breakthroughs and the buzzword *deep learning*. Getting a computer to [master Go](https://www.scientificamerican.com/article/how-the-computer-beat-the-go-master/) is more sensational than chess is because a computer can easily store all possible chess moves, but there's way too many possibilities in Go, so the computer has to be able to adapt to its opponents specific plays, not having a list of all possible scenarios in hand. Kind of like teaching a car to drive.

Of course, this has led to certain faux pas like Google's recognition software tagging [black people as gorillas](http://www.wnyc.org/story/deep-problem-deep-learning/) and Microsoft's chatbot [turning Nazi](https://www.theverge.com/2016/3/24/11297050/tay-microsoft-chatbot-racist) by learning from Twitter in a day. These are slightly offensive and slightly funny scenarios, but the basic fact is that AI learns from human behaviour (in the form of data), and in the process it learns our biases and bigotries. Interestingly, this is sort of like an automated form of discourse analysis as in Edward Said's conclusion of orientalism of various Western literary works; one could learn to be racist with Twitter as a textbook.

#### Big data in black boxes

Now let's scale up a little, and look at certain algorithms that Cathy O'Neil calls Weapons of Math Destruction, or WMDs for short. This comes from her book *Weapons of Math Destruction: How Big Data Increases Inequality and Threatens Democracy*. In it, she defines a WMD to be an algorithm that has: (1) opacity, (2) scale, and (3) damage. Let's break these down a little.

An algorithm is opaque when its processes or its inner logic, i.e., the model that it operates on, is invisible to the people it is being applied to. For example, most of us don't know how ad services work exactly, though we might have a few guesses. We call this a black box. It's a term in used in computer science and mathematics, to describe a tool which you don't know exactly why or how it works, but you use it anyway, taking for granted that it does because someone else vetted it. Most algorithms that operate in the background of our lives are opaque, under some kind of patent or corporate lock. Importantly, the point is not that everyone can understand it, but if a third party want to audit the code for say, certain biases, they would have access to do so. 

Scale is a simple enough feature: the algorithm must be rolled out at a large scale, so that it is affecting many people, and hence has many potential victims. Which is the third point: damage. The algorithm must be affecting people negatively, and in a way that discriminates against people with particular traits, like race and income. When these three come together, O'Neil calls the algorithm a Weapon of Math Destruction. It has other features, like so-called 'pernicious feedback loops'. That is, the algorithm's success is measured by the results that it gets, and if its results reinforce an inequality, that reproduces more bad data like the kind that went into the model that it was built on in the first place.

Of course, the algorithm's black box is precisely what gives it the impression of impartiality and veracity: it is a machine, so it should be less prone to emotional judgments and prejudices than a human (although the machine itself learned from humans), and that its results are God's truth, since we can't see through the black box, and even if we could we probably wouldn't understand that model or the mathematics behind it all anyway. As they say, the numbers don't lie. Or do they?

#### Some WMDs in the wild

Here's a quick and dirty run through of most of the examples covered in the book. The book is written by a US author for a US audience, so the case studies will be very much focused on US society and politics.

1. **College rankings**. In 1983, a group of journalists at the US News & World Report came up with a list of measurable criteria, i.e., a  model, for what makes a college or university the 'best'. This set of an arms race among schools to boost performance in these criteria as the rankings became the national standard. One inherent problem is that this measuring stick is not a one-size-fits-all standard: what's best for you is not necessarily what's best for me. Just as this is true in terms of nutrition, so it is in education. At the same time, this sets up a system that can be gamed. For example, certain law schools boosting post-graduation employment rates by giving their own graduates temp jobs.

   The second problem is a simple pernicious feedback-loop: How do the modellers know that their model is accurate? In this case, the rankings would be more credible if they reflect the pre-existing hierarchy. Elite schools, i.e., schools in which children of the elite enrolled, like Harvard and Princeton had to top the list to validate the model. In other words, the rankings perpetuate the existing inequalities and reinforce class lines. Importantly, an important factor that is left out of the rankings is the tuition price. This effectively gives schools permission to raise tuition to generate more revenue to boost performance in the ranking's metrics (which has happened nationwide). 

> If you look at this development from the perspective of a university president, it’s actually quite sad. Most of these people no doubt cherished their own college experience—that’s part of what motivated them to climb the academic ladder. Yet here they were at the summit of their careers dedicating enormous energy toward boosting performance in fifteen areas defined by a group of journalists at a second-tier newsmagazine. They were almost like students again, angling for good grades from a taskmaster. In fact, they were trapped by a rigid model, a WMD. -- O'Neil

   Of course, the victims here end up being folks who cannot afford the sticker price on the one hand, being  led into debt, and on the other hand, cannot afford tutors and counsellors who will coach students through the admissions process. Each college has an admissions model tailored to the maximise the college's own rankings, and are mini WMDs in themselves, driving the race for SAT scores and extraordinary extracurriculars.

2. *Recidivism risk.* Models like LSI-R (Level of Service Inventory—Revised) are tools used by judges to determine the severity of sentences handed out to convicts. Using certain information including a questionnaire that the convict fills out, it determines the risk of the convict committing a crime again. This makes sense at first, taking the possible moods or biases of the judge out of the equation. But the questions collect historical data that is already biased. Questions like: How many previous convictions have you had, when was the first time you were involved with the police, and Do you know anyone who has been convicted of a crime, are questions whose answers depend more on living in neighbourhoods that are poor and coloured. While not legally allowed to ask one's race, and seemingly innocent information like one's zip code, as discussed above, become proxies for race and class. Indeed, recidivism risk combines with the next model as a part of a big negative feedback loop:

*Predictive policing.* Very often, algorithms are meant to optimise a certain process, given limited resources. In this case, the optimisation problem involved is how to distribute police patrolling in areas that where crime is more likely to occur. In New York City, for example, this is carried out on the ground in the form of policies like Broken Windows and, more recently, Stop and Frisk. But this is also implemented through algorithms like PredPol and Compstat, which predict neighbourhoods that are hot spots for criminal activity. In this case, it's quite easy to see how the pernicious feedback loop is generated: more policing leads to more arrests, and more arrests lead to more policing.   It's important to note that zero-tolerance policies like Broken Windows causes police to not distinguish between so-called Part 1 crimes (homicide, assault, etc.) and Part 2 crimes (aggressive panhandling, selling or consuming small quantities of drugs, etc.). Part 1 crimes are crimes that should be prevented without question, while Part 2 crimes are often situational; think of soft drugs being used on a college campus versus a 'bad' neighbourhood. 

And of course, this model only picks up 'blue-collar' crimes: acts such as fraud, embezzlement, and economic catastrophes like the 2009 financial crisis slip by silently. As such, increased police activity on the ground makes living in certain zip codes more of a liability, and you can imagine how that goes into a recidivism risk calculation. Also worth mentioning is the fact that counter-terrorism and counter-insurgency practices of the US army abroad (which we'll cover in the next post!) are slowly brought home to roost. In this case, as a look into the future, facial recognition software is being tested to identify not just wanted persons, but also potential criminals. Fortunately, this was turned down by the San Diego police department in favour privacy. Small victory.

3. *Human Resources*. We'll look first at getting a job, and then what happens on the job. As you can imagine, getting a job with the deck stacked against you like before is easier for some more than others. When you put in a job application, your application or interview might include questions that are basically a psychological profile or personality test, like those developed by Kronos, a workforce management company. This sounds innocuous, but choosing between "It is difficult to be cheerful when there are many problems to take care of" or "Sometimes, I need a push to get started on my work" might be the difference between being identified as "conscientiousness" versus "low ambition and drive". This profiling says nothing certain about a candidate's ability to perform their job, but now becomes a deciding factor on getting a job. And, as you can guess, those with any mild personality disorders or mental disabilities get the short end of the stick.

Algorithms like these are mostly used by large companies to streamline their hiring process. Even with a smaller company, your resume might be read by a computer that sorts through thousands of others, and it's your job to know the keywords and phrases that will make sure your resume survives this initial culling process. And knowing what a winning resume looks like, again takes resources more readily available to the more privileged. Of course, hiring practices have been discriminatory long before the help of automation; it's simply that the biases get built into the algorithms, and become opaque. Also, the use of these systems is not uniform: it gets used less and less as you go up the ladder, and most on those entry level, low-wage jobs. It's quite likely that such models not only propagates the existing power structure, they elaborate upon it, streamline it.

*Operations research*. Let's suppose that after all that, you managed to land a job. As a worker bee, you've in fact entered as worker 'X' into the world of operations research, or OR. It is properly a branch of applied mathematics, meant to optimise efficiency in growing crops and moving goods. This was also used in 1945, World War II, to minimize the number of mine-laying aircraft for each Japanese merchant ship delivering supplies to Japanese shores. In the 1960s, Japan developed a manufacturing system called Just in Time that minimises the time that parts in delivery remained idle, increasing efficiency and saving cost across the supply chain.

OR is now much more sophisticated, micromanaging the worker down to the minute. For example, companies like Starbucks use scheduling software that analyses customer traffic to schedule its employees. Unoptimised, this analysis is quite harmless, and makes simple recommendations; but when optimised to be sensitive to mercurial variables such as weather and Twitter volume, the employee's work hours are held hostage by a machine. 

> "The trouble, from the employees’ perspective, is an oversupply of low-wage labor. People are hungry for work, which is why so many of them cling to jobs that pay barely eight dollars per hour. This oversupply, along with the scarcity of effective unions, leaves workers with practically no bargaining power. This means the big retailers and restaurants can twist the workers’ lives to ever-more-absurd schedules without suffering from excessive churn. They make more money while their workers’ lives grow hellish. And because these optimization programs are everywhere, the workers know all too well that changing jobs isn’t likely to improve their lot. Taken together, these dynamics provide corporations with something close to a captive workforce."

Another instance of OR is the so-called value-added school teacher performance measure.


2. Financial crisis: risk, mortgage-backed securities, sub-prime mortgage loans (probability, Black-Scholes) /risk

3. Predatory advertising (pain points, Bayesian stats, big data, machine learning e.g. Siri and language, payday loans, lead generators)


6. Consumer profiles (Data brokers, credit scores vs e-scores, proxies for job offer/promotions, zipcode profiling, 'buckets', insurance/actuarial science, behavioral data)

7. Voter profiles (A/B testing, Facebook 'I voted!', targeted marketing, swing voters/purchase brand, behavioural/consumer buckets, )

As a silver lining, O'Neil ends with a few examples of good models, models that are being used for good in the world: algorithm audit, slavery model Made in a Free World, homeless recidivism, predictive model for households of child abuse Florida.

> Big Data processes codify the past. They do not invent the future. Doing that requires moral imagination, and that's something only humans can provide. We have to explicitly embed better values into our algorithms, creating Big Data models that follow our ethical lead. Sometimes that will mean putting fairness ahead of profit. -- O'Neil

#### Mining and spying

Now, the advent of Big Data has not been precipitated so much by the computer or even the internet, but rather the smart phone. The algorithms like the ones described above are contingent upon having troves of data, 

Let's come back to where Big Data comes from. 

[data mining to oil drilling](https://www.theguardian.com/world/2017/aug/23/silicon-valley-big-data-extraction-amazon-whole-foods-facebook)

Algorithms don't kill people; people kill people.

