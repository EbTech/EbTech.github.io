---
layout: mathpost
title:  "Is probability real? (Part 1)"
date:   2020-11-22
categories: probability
tags: probability
---
Today, I want to address an issue with statements involving chance. To demonstrate, let's first consider a statement that doesn't involve chance:

"*A cubic die tossed onto a flat surface will come to rest on one of its six sides.*"

This claim can be empirically tested, with various dice and surfaces. If any one of our experiments results in the die spinning endlessly on a corner, we will have disproven the claim. We may have to refine the claim's conditions; for instance, by requiring the presence of gravity. Nonetheless, it's fairly clear what it means for the statement to be true or false. Now let's try to make a claim involving probability:

"*If a pair of standard dice are thrown, the probability of their face-up sides summing to nine will be one in nine (about 0.11 or 11%).*"

What does it mean for this statement to be true? Unlike the first statement, this one doesn't specify which result we'll actually see. How can we possibly hope to test it, or to make use of its information?

# The mathematician's multiverse

Within the realm of abstract mathematics, we're free to model probability in a way that fits our intuitions. Imagine a multiverse containing an infinity of possible worlds, whose total *measure* is 100%. Define the probability of an *event*, such as that of rolling a nine, to be the measure assigned to the subset of worlds in which the event actually occurs.

In the abstract formalism, we're allowed to assign the measure however we like, subject to Kolmogorov's axioms: the measure must be non-negative, countably additive, and total to 100%. By respecting the symmetry of an idealized die,[^1] we might argue that only one such assignment makes sense; from it, we can calculate the probability of any event involving dice rolls.

There are two shortcomings to this approach. Firstly, we won't always deal with nicely symmetrical objects for which direct a priori arguments are possible. Thus, we still need a means of testing probabilistic claims using real-life observations. Secondly, we should question what sense it makes to measure a subset of an imaginary multiverse, when in reality we only experience and report observations from *one* world! A realist might ask: what sense does it make to talk about the *chances* of something happening? Either it happens or it doesn't!

# The economist's wager

You might be more trusting of someone who puts their money where their mouth is. To back up a definite claim, not involving chance, I can simply agree to pay a penalty if it turns out I'm wrong.

This idea can be extended to probabilistic claims in the following manner: consider a lottery that pays an $80 jackpot if the next roll of a pair of dice yields a nine. If the maximum that I'm willing to pay to play is $10, this indicates that I believe a not-nine roll is eight times more likely than a nine roll.

If another gambler's view conflicts with mine, you may aggregate our beliefs by creating a market on which we can buy and sell predictions. The prices at which these predictions trade provide what economists call the *risk-neutral probability measure*; in the absence of market frictions and arbitrage, it satisfies Kolmogorov's axioms. This approach is very appealing because, after all, the *raison d'être* of probability theory is to explain the decision-making of individuals facing uncertainty!

In using this interpretation, we effectively assume that the probability assigned to any set of worlds is proportional to the market value of a dollar there: to say an outcome is twice as "likely" as another, just means we'd bet double odds on it.

Taking this as the definition of probability yields some strange results. Firstly, it depends on which currency is used: as an extreme example, we wouldn't buy a dollar-denominated wager that only pays out if the dollar collapses, no matter how likely we imagine the collapse to be. Secondly, this measure is sensitive to (non-diversifiable) risk: if our dice were magic so that a nine would result in a catastrophic famine, the market would value this outcome a lot more, because everyone wants to buy insurance against such a catastrophe. Thirdly, markets can be misinformed. And finally, liquid markets are hard to set up.

For these reasons, we abandon this approach, and seek a definition that looks at actual outcomes instead of human bets. Nonetheless, since human bets are what inspired the creation of probability theory, we should remember to revisit the matter once we've found an appealing probability concept. Ultimately, we must be able to explain *how* individuals and markets behave with respect to our concept, and answer *why* they should care about it at all.

These questions are incredibly subtle: the theory of evolution by natural selection tells us that individuals are wired to use strategies that enabled their ancestors' survival; however, the nature of probabilistic beliefs is that a wide range of outcomes are plausible. Indeed, while a coin will always land heads or tails, it's considered unwise to bet your life savings on either heads or tails. Intuitively speaking, the big issue is that you're almost certain to lose *eventually*, if you keep playing this way. This idea of repeated trials inspires our next interpretation, which happens to be the most popular among scientists.

# The statistician's frequentism

According to the frequentist school of thought, a probabilistic statement is not literally about a single event; rather, it's a shorthand way of talking about a very large collection of similar events. Imagine rolling the dice over and over. The probabilistic claim that we started with is converted into the following:

"*If a pair of standard dice are thrown repeatedly, then in the limit as the number of throws goes to infinity, the proportion of nines converges to one in nine (about 0.11 or 11%).*"

The short-run probability is replaced by a long-run proportion. Given an infinite sequence of rolls, this statement unambiguously reveals itself to be true or false. In light of the frequentist interpretation, we can even make more sense of our earlier interpretations. While we only experience one world, repeating an experiment under similar conditions is like observing the experiment in a parallel universe: whether we count trials or worlds, the math is virtually identical. In the limit of infinitely many bets, we can make some unambiguous conclusions about the quality of a gambler's strategy, too: this is how casinos ensure that the house always wins!

Testing our claim is a simple matter: we roll the dice, over and over, and over and over... infinity times! Oops. Of course, there is no such thing as an experiment with infinity trials. Our arms will get tired, the dice will wear out, the Sun will explode, and all the free energy in the universe will be consumed. At best, we can do a very large number of trials. Let's say we roll dice 9,000 times; one in nine of these would be 1,000. Perhaps we won't roll exactly 1,000 nines, so let's interpret our claim with a suitable margin of error, called a *confidence interval*:

"*If a pair of standard dice are thrown 9,000 times, then the face-up sides will sum to nine for between 920 and 1,080 of the throws.*"

The probability of obtaining between 920 and 1,080 nines can be calculated to be 99.3%.[^2] So, we've turned a probabilitic statement into a much more certain but still probabilistic statement. If we observe 1,100 nines, we should be able to dismiss the probabilistic claim as false. And yet, if every household on Earth were to independently perform this 9,000-throw experiment, we should expect that *some* of their results would lie outside the confidence interval. They would disagree on the truth of our statement!

There's no getting around it: despite its intuitive appeal, the frequentist definition of probability is circular, reducing probability claims to probability claims.[^3] To end the cycle, the frequentist chooses a threshold (say, 99.99%) beyond which to treat events as objective truths. This grants the claim an empirically observable meaning. And yet, the frequentist must take care not to consider too many such events, for otherwise they may find that the union of the complements also exceeds the threshold of certainty: a logical contradiction.

Things only work out nicely in the infinite limit. Statisticians mainly deal with experiments which can be repeated so many times that, for practical purposes, their conclusions can be treated as definite. Non-philosophers are usually happy to ignore a 0.7% chance of error; and if that's not good enough, make it 0.0001%! Confidence can be increased by gathering more data, i.e., increasing the sample size.

This approach turns out to be very powerful. Using more advanced scientific methodologies, even some phenomena that aren't easily repeated can be statistically analyzed. Weather forecasts arguably fall under this category. Nonetheless, there are limits. When political analysts try to predict nation-level democratic elections, or even when you try to predict which colleges will admit you (or your child), or which investments you should buy, there's no statistical method powerful enough to sweep the circularity of frequentism under the rug. One may argue that no conclusions in these cases would hold up to a scientific standard; nonetheless, if we seek a theory of decision-making under uncertainty, there's no denying the importance and prevalence of such cases.

# Throw in the towel?

Fundamentally, questions involving probability are ill-posed: it's impossible to deduce anything about worlds unconnected to our experience, let alone assign measures to them! Even if we imagine the multiverse of probability theory to be real (whatever that means!), then each world would be just as real as any other, potentially with its own inhabitants asking the same questions. Unlike physical quantities such as volume, a probability measure has no observable consequences!

So, why does probability hold such a salient intuitive significance to us? What is it about so-called "unlikely" events that make us feel surprised? Recall that evolution by natural selection is a numbers game: you can afford some mistakes, but it's important to be right more often than wrong, and to plan accordingly. On the occasions where we're wrong, we sense a bit of shock as we adjust our plans and our expectations for the future. This lines up with the frequentist interpretation: "likely" events are those which occur more frequently, across a large sample of similar scenarios.

But what about rare scenarios? What does it mean to say it's likely (or not) that extraterrestrials exist? What would it mean to live in an unlikely universe, say, one in which dice rolls land on double-sixes much more often than they should, consistently for as long as dice have existed? Technically, nothing that we know about our own world's physics forbids this: we could just get "lucky" to an enormous degree. But what would the inhabitants of this universe think? I imagine they wouldn't consider their world unlikely at all: they would just add a new law to their description of physics: all dice, as if by divine intervention, are deemed to exhibit this strange behaviour. While it's a rather awkward addition that complicates physics, including it definitely yields a better theory in terms of predictive accuracy. We might also expect their religions to grant a spiritual significance to dice.

Science can withstand a single oddity involving dice. However, if the universe were arbitrarily messy, complicated, irregular, its randomness devoid of any patterns; then, it would feel as if all events were decided by divine intervention. In such a world, there would be no role for science. The ancients believed in a mystical world where everything from weather to animal physiology were subject to the daily whims of the Gods. Nevertheless, even the ancients believed in some basic patterns, which they could use to cook, hunt, navigate, build shelter, and otherwise live their lives. Without patterns to exploit, there would be no reason for intelligent life to emerge. The simplicity of the universe is one of its prime defining characteristics.

# The philosopher's razor

Let's see if we can develop this vague connection between probability and simplicity into a concrete idea. Our biggest clue is a question raised by the frequentist school of thought: where does the hypothesis come from in the first-place?

If we don't know which hypothesis we should test, we might begin by considering every hypothesis that comes to mind: potentially thousands, millions, or infinitely many. In the dice experiment, we might consider some strange hypotheses, such as having the chances of rolling doubles depend on which celebrity's credit card number was spelled by the last few rolls. If, for each hypothesis, we design a test that will fail (according to the idealized dice model) with 99% probability, then on average, one out of every hundred hypotheses will pass the test.

What makes the "true" hypothesis stand out from the many fakes? Well, the fakes would be unlikely to stand up to additional testing. The more data we collect, the more contrived the hypotheses that we'll have to resort to; nonetheless, it will always remain possible to fit an incorrect hypothesis to all of the data seen so far. This is such a serious problem in science that it has a name: *overfitting*.

Somehow, we must narrow down our hypotheses. Maybe you think that's easy: only a few hypotheses describe plausible dice behavior; the rest are patently absurd! But now you're relying on intuitive judgment, not a rigorous methodology. If you try to sort out the source of your intuitive knowledge about how dice ought to behave, you'll find it to be rooted in your prior knowledge about how the world works, which itself must be tested against various hypotheses. If you have good prior knowledge and take it on faith, then this works fine in practice. However, it seriously begs the question: how do we manage to obtain *any* knowledge about the world in which we live?

There is a solution to this dilemma. For most of history, nobody knew how to state it in precise mathematical terms; hence, it was confined within the realm of philosophy. The solution is the law of parsimony, **Occam's razor**:

"*Given competing theories that can explain our observations, always prefer the simplest.*"

If we take "simple" to mean that it must be described by a short English sentence, then there are only a limited number of such sentences. Among the simple hypotheses, we can eliminate all the bad ones within a finite number of trials.

Thus, we see that frequentist methodology requires the use of prior knowledge, and ultimately a principle such as Occam's razor. Could we take this idea to its extreme, in the hopes of mitigating the other issues with frequentism? The advent of computer science gave us a theoretical framework in which to do so. With it, we'll build a theory of inference built solely on Occam's razor.

# The computer scientist's electric razor

English sentences can be a bit ambiguous so, for precision's sake, we'll express our hypotheses as computer programs, and encode our observations as computer data. Nonetheless, if you're not a programmer, rest assured that it's mostly kosher to replace the programs in our discussion with instructions written in your mother tongue.[^4] In the computer science framework, we restate Occam's razor as follows:

"*Given competing programs whose outputs match our observations, always prefer the shortest.*"

Let's see just how powerful this definition is. Firstly, there's no need to design hypotheses or tests, as both are built-in: all computer programs are hypotheses, with preference given to shorter ones. Testing a program amounts to verifying that its output exactly matches our observation record.

At first blush, the requirement to use deterministic programs appears to be a limitation. Luckily, randomized programs can be made deterministic by supplying the results of "coin flips" as an extra string of ones and zeros. This string makes the program longer, so Occam's razor will prefer explanations that don't depend on too much randomness, if one exists.

Given a string \\(x\\), perhaps representing a very long sequence of observations, the minimum length of a program that outputs \\(x\\) is called its **Kolmogorov complexity** \\(K(x)\\). In case you're wondering why we don't consider alternative ways to prioritize hypotheses, it turns out that the Kolmogorov complexity dominates all enumerable alternatives, to within a constant margin. For an excellent reference, please see the footnote[^5]. We won't go deeply into the theory here, but merely highlight how it helps us interpret and infer probabilistic statements.

Classical information theory studies the optimal rate at which random objects can be compressed. If the objects are drawn from a known probability distribution \\(\mathcal P\\), then *on average*, the number of bits needed to compress one object is equal to a quantity known as the **entropy** \\(H(\mathcal P)\\). No compression algorithm can beat this on average. In general, it's questionable whether we should care about the average, as opposed to the median, mode, maximum, or some other statistic.

But now suppose we independently sample a very large number \\(N\\) of objects from \\(\mathcal P\\). The Law of Large Numbers pushes toward the average: almost certainly, the total encoding length of the entire sequence of objects will be very close to \\(NH(\mathcal P)\\). The sequence's Kolmogorov complexity will not be much more than this: a suitable program consists of a description of \\(\mathcal P\\), along with the classical encoding (optimized for \\(\mathcal P\\)) of each object in the sequence, for a total complexity of approximately \\(K(\mathcal P) + NH(\mathcal P)\\).

If there's no program that's significantly shorter and generates the same sequence, then the above program is a good explanation for the sequence: it is approximately the simplest. That is, we can now look at an individual string, with no prior concept of it being random, and conclude that it looks like a sequence of random draws from \\(\mathcal P\\)! For example, consider the following sequence:

\\(3,1,4,1,5,9,2,6,5,3,5,8,9,7,9,3,2,3,8,4,6,2,6,4,3,3,8,3,2,7,9,5,0,2,8,8,4,1,9,7\\)

This will *not* pass as a random sequence of rolls from a pair of fair dice whose sides are numbered 0 to 5. Why? To interpret it as such, we must include an encoding for each element. While this is a bit shorter than writing the sequence literally, it's much longer than the phrase: "first forty digits of pi".

If it were possible to algorithmically compute the shortest program that outputs any given \\(x\\), we would have a very powerful inference engine that can answer some of our deepest scientific questions for us! Naturally, such a thing is too good to be true. For fundamental reasons related to the theory of proofs and computation, the Kolmogorov complexity is not computable.[^6] Thus, we can only try our best to discover the most parsimonious explanations we can, not knowing how close we are to the best possible. Occam's razor can distinguish good and bad hypotheses and, unlike pure frequentism, resists abuse by a barrage of bad hypotheses. Nonetheless, we still need some ingenuity to find a good hypothesis.

In a sense, that's exactly what the pursuit of scientific theories is about. The ancients would be astounded to learn that so much of the world (perhaps all of it!), with its vast richness, can be described by a few simple laws. Over the centuries, we've found more and more patterns, making our theories ever more parsimonious. The scientific method only works because the rules of the universe happen to be simple, while the set of observations it offers is vast. Kolmogorov complexity captures this defining characteristic of our reality.

# Next time...

In the next blog post, we'll see that in pretty much any world where inference is possible, the Kolmogorov complexity approach applies. Thus, we'll come to understand the limits of knowledge. Analogous issues will crop up in the Kolmogorov complexity methodology, via an ambiguity in the definition that we have overlooked until now: namely, the choice of computer programming language. Nonetheless, we'll find that it's possible to mostly mitigate the issues we found with frequentism. Finally, we'll see what this means for probabilistic claims in practice.

[^1]: The argument feels more convincing if we use chaos to ensure ergodicity, but this still requires an initial source of randomness...

[^2]: Hypothesis testing requires that, before running the experiment, we specify not only a hypothesis but also a test. You might wonder why we choose an interval \\([920,1080]\\) that's centered at the expected result. Typically, it's because we expect that if our hypothesis were wrong, the most realistic alternative would be that our dice produce nines at a much different frequency than we expected. If we're certain that the frequency isn't lower, but it may be higher, then a one-sided interval \\([0,1074]\\) with the same confidence is more likely to rule that out. Since the chances of obtaining exactly 1,000 nines are about 1%, another perfectly valid 99%-confidence test would be to check that the number of nines is *anything except* 1,000! Would this test ever make practical sense? It would if we're suspiscious that the dice, rather than being random, are rigged to produce exactly 1,000 nines. Since every fixed number of rolls can be tested against in this way, *every* conceivable result will fail *some* test!

[^3]: The competing Bayesian school of thought, while more intuitively appealing when sample sizes are small, is circular in an even more obvious way. The circularity can be resolved using something called a *universal prior*; the result turns out to be equivalent to the Kolmogorov complexity approach that we describe later.

[^4]: That said, we can start to appreciate why a basic education in computational thinking is fundamental to understanding nature, just as math and science courses are.

[^5]: Ming Li and Paul Vitanyi. 2019. An Introduction to Kolmogorov Complexity and Its Applications (4th. ed.). Springer Publishing Company, Incorporated.

[^6]: The uncomputability of \\(K(x)\\) has to do with the fact that it's hard to distinguish a program that takes absurdly long to run, from one that never finishes. Since an absurdly slow program is fairly useless, we might prefer to rephrase Occam's razor using a resource-bounded complexity measure (see Chapter 7 of the preceding reference). For instance, while quantum mechanics should theoretically describe all of life's processes, a supercomputer would struggle to simulate even one atom this way. To make useful inferences, we also need the theories of chemistry, biology, and the social sciences. Technically, a resource-bounded complexity measure is computable by simply trying every possible program until the output matches. However, the number of possible programs to search through would be astronomical!
