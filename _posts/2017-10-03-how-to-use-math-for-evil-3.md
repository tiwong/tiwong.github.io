---
layout: post
title:  "How to use math for evil III: Cryptosystems"
date:   2017-10-03 12:50:45 +0100
categories: data
---

*This is an expanded version of the general audience talk I'm giving at the Science on Tap--formerly known as Drunk on Science, which is much cooler but probably less professional--in Pune, the brainchild of the illustrious Anoop Mahajan, with craft beer sponsored by Great State Ale Works! See [Part 1](https://tiwong.github.io/data/2017/09/28/how-to-use-math-for-evil-1.html), [Part 2](https://tiwong.github.io/data/2017/09/30/how-to-use-math-for-evil-2.html), [Part 3](https://tiwong.github.io/data/2017/10/03/how-to-use-math-for-evil-3.html), [Part 4](https://tiwong.github.io/data/2017/10/06/how-to-use-math-for-evil-4.html)*

Last time we entered into world of Big Data, and saw how complicated algorithms extend into our daily lives. We ended on the fact that Big Data is contingent upon data mining, which drills deeper and deeper into our lives. This time, we'll talk about surveillance and cryptosystems, that are intertwined with this process.

#### Death by algorithm

Before we get started, let's note that mathematics has been used in warfare from ages past. Trigonometry and calculus have helped to calculate trajectories of rockets and bullets, a study known as [ballistics](https://en.wikipedia.org/wiki/Ballistics). If you watch shows like CSI, this is also involved in forensics, like with blood-splatter analysis. 

And in keeping with the theme from Part 2, Obama's so-called presidential kill list, formally known as the [Disposition Matrix](https://en.wikipedia.org/wiki/Disposition_Matrix), that governs drone strikes in the Middle East and Africa in fact involves complicated algorithms like the NSA's [Skynet program](https://en.wikipedia.org/wiki/SKYNET_(surveillance_program)) (not the the one in Terminator!) applies machine learning to communications data, in order to identify possible terror suspects. A terror suspect is then assigned certain scores like a player on a baseball card, and this ranks them in the kill list, which in turn determines drone strikes. [In the words](https://www.theguardian.com/commentisfree/2016/feb/21/death-from-above-nia-csa-skynet-algorithm-drones-pakistan) of former CIA and NSA director General Michael Hayden himself, 

> "We kill people based on metadata."

For one, The person targeted by the drone strike is merely a *suspect*, and we know this to be faulty knowledge at times from various reports over the years. Secondly, any civilian casualties, of which there are many, gets written off as collateral damage.

He later qualified his statement that the US government only kills foreigners, not US citizens this way. But even if you were a US citizen, you certainly have reason to worry. As mentioned in the last post, US warfare tactics abroad do find their way back home. Good examples are the counterinsurgency measures used at police-brutality protests like [in Ferguson and Baltimore](https://gizmodo.com/welcome-to-the-new-age-of-counterinsurgency-policing-1702621152),  and counterterrorism tactics used at the [Dakota Access Pipeline protest](https://theintercept.com/2017/05/27/leaked-documents-reveal-security-firms-counterterrorism-tactics-at-standing-rock-to-defeat-pipeline-insurgencies/) at Standing Rock. Not to mention the fact that the militarisation of US police force is a direct outcome of government policy like the 1997 [1033 program](https://en.wikipedia.org/wiki/1033_program) and [more recent presidential orders](https://www.theguardian.com/us-news/2017/aug/28/donald-trump-news-police-military-style-weapons-vehicles), giving surplus military equipment to civilian law enforcement services.

#### Public-key cryptography 

The advent of quantum mechanics, what one might think of as [blue-sky research](https://en.wikipedia.org/wiki/Blue_skies_research), that is, research with no immediate 'real-world' applications, also came hand in hand in nuclear fission, as with the infamous [Manhattan Project](https://en.wikipedia.org/wiki/Manhattan_Project). The same has happened for number theory, which the famous mathematician Gauss called the Queen of Mathematics. Number theory is the study of prime numbers, the building blocks of integers. It is also the foundation for modern cryptosystems, or encryption methods. They do good things, like protect your credit card purchase on Amazon from being hacked and keep your bank accounts secure, but they also are at the epicentre of issues surrounding surveillance, security, and privacy.

The basic idea of encryption is simple: Alice wants to tell Bob a secret, and if Eve gets a hold of the message, the message would read like gibberish. To do this, Ann must encrypt the message in a way that only Bob can decipher. Here's how it goes: Alice starts with an algorithm that enciphers the message into numbers, say the way you might have done as a school girl:
```
I C E C R E A M ---> 9 3 5 3 18 5 1 13
```
Now the trick is to use a cipher key, which let's say is 'multiply by 3', so that you get 
`27 9 15 9 54 15 3 39`, and then Bob, who also has the key can 'unlock' the encrypted message. The trouble with this system is that Eve can intercept this, and if she figures out the key, learns the secret. In this method the keys have to constantly be changed, and it's a complicated process for Alice to tell Bob the new key, because if she uses the old key and Eve knows the old key, then Eve also gets the new key. But this was the way things worked for a long time like the [Enigma Machine](https://en.wikipedia.org/wiki/Enigma_machine) in World War II, and being able to crack secrets was highly in demand during times of war.

Then in 1976 came the [Diffie-Hellman key exchange](https://en.wikipedia.org/wiki/Diffie–Hellman_key_exchange), one of the first public-key protocols. This introduced the asymmetric cipher, where the encrypting and decrypting keys are different, so Alice and Bob can now share a secret even if Eve is listening, since Alice does not have to communicate any key to Bob.

The [RSA encryption scheme](https://en.wikipedia.org/wiki/RSA_(algorithm)), invented the next year, put this into practice. And this is where number theory comes in: the fact that the procedure works is guaranteed by [Fermat's Little Theorem](https://en.wikipedia.org/wiki/Fermat%27s_little_theorem). Here's a rundown of how it works: 

1. Alice picks two prime numbers, let say `p` and `q`. Their product `N = pq` is the public key.
2. Alice picks a number `e` relatively prime to `p-1` and `q-1`. This is also made public.
3. Bob wants to tell Alice a message `M`, so he encrypts it as `C = M^e (mod N)` and sends this.
4. Alice solves for a number `d` such that `ed = 1 (mod (p-1)(q-1))`.
5. Alice decodes by calculating `C^d (mod N)`, and the answer is equal to `M`.

Here, `mod` stands for modulo, as in [modular arithmetic](https://en.wikipedia.org/wiki/Modular_arithmetic) or 'clock' arithmetic. It works like a clock: let's start at 9 o'clock. Then any multiple of 12 hours, say 36, later is still 9 o'clock. That is, `45 = 9 (mod 12)`. In our example, to reduce `C^d (mod N)`, simply take out as many multiples of `N` from `C^d`, and what's left over is your answer, which by some mathematics turns out to be `M`.

In real life, the primes are much larger, on the order of hundreds of digits long, so that factoring `N` would be practically impossible unless you were Alice or Bob. This is necessary since the decryption key requires knowing the values `p-1` and `q-1`. Also, in practice, public-key takes a huge amount of computer time, so what really happens when you tell Amazon your credit card number is a hybrid of public *and* private key cryptography.

As you can see, public-key cryptography depends on certain mathematical operations (like factoring!) being hard. More sophisticated methods have been developed, balancing security  and efficiency as one often comes at the cost of the other. An important example comes from the world of number theory, called [Elliptic Curve Crytography](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography), or ECC. It uses a certain multiplicative rule on an elliptic curve that looks like `y^3 = x^3 + ax + b`. There are even recommended elliptic curves, i.e., parameters `a` and `b` for government use. 

#### Big brother and big data

Now what's important to the NSA is that such recommended cryptosystems have backdoors, which are basically cheat codes in this secret sharing game that allow the messages to be intercepted and decrypted at will. That is to say, your data may be secure to most people, but to the professionals, shall we call it, your data is not. The cold, hard logic behind this is always under the banner of national security. 

And it is for this reason that your data, that is being mined by large corporations for profit, is also open access to the state, at least if said corporations are US firms. Indeed, among Edward Snowden's leaks is that tech companies like Microsoft, Google, Facebook, and Apple have [tapped their own servers](https://www.theatlantic.com/technology/archive/2014/07/the-details-about-the-cias-deal-with-amazon/374632/) for the intelligence agencies such as the NSA and FBI, while Amazon Web Services is a [CIA contractor](https://www.theatlantic.com/technology/archive/2014/07/the-details-about-the-cias-deal-with-amazon/374632/).

Perhaps most baffling of all is Signal, the go-to encrypted chat app used by US journalists and activists, endorsed even by Snowden. It is also adopted into Facebook's Whatsapp. The irony is that Signal's parent company [Open Whispers Systems](https://en.wikipedia.org/wiki/Open_Whisper_Systems) has received almost 3 million in US government funding to date via Radio Free Asia. There are reasons for this, discussed along with a more secure chat app, Telegram, and its Russian inventor and dissident Pavel Durov in [this exposée](https://thebaffler.com/salvos/the-crypto-keepers-levine). Certainly the CIA has taken much more indirect routes, as with abstract expressionism being used as a [Cold War weapon](http://www.bbc.com/culture/story/20161004-was-modern-art-a-weapon-of-the-cia).

This makes the deeper data mining of companies more unsettling: the increasing amounts of surveillance performed by tech giants for profit, can easily be obtained—whether by direct requests or third-party hacking—by US intelligence agencies for security. The recent requirement of the Department of Homeland Security, or DHS, to [collect social media information](https://www.nytimes.com/2017/09/28/us/politics/immigrants-social-media-trump.html) on immigrants to the USA is one such frontier. The trouble with 'security' is that it is not possible to define or set fixed boundaries for, and we see its full power in more totalitarian regimes where there is no façade of democracy. Also, a recent [journal article](http://openscholarship.wustl.edu/cgi/viewcontent.cgi?article=6265&context=law_lawreview) makes the case that surveillance and data collection burdens poor people 'many times over,' consistent with the topic of Part 2.

Before, Michel Foucault's [Panopticon](https://en.wikipedia.org/wiki/Panopticism) as a symbol of the surveillance used to discipline society's members by making each person the 'principle of his own subjection' has now grown into words like 'dataveillance' and 'information panopticon.' But the difference now, with the advent of Big Data, is that we can be sure we are being watched. The slow march towards complete surveillance removes the need for a Panopticon. 