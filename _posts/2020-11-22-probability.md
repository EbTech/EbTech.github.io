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

"*If a pair of standard dice are thrown, the probability of their upward-facing sides summing to nine will be one in nine (about 0.11 or 11%).*"

What does it mean for this statement to be true? Unlike the first statement, this one doesn't specify which result we'll actually see. How can we possibly hope to test it, or to make use of its information?

# The mathematician's multiverse

Within the realm of abstract mathematics, we're free to model probability in a way that fits our intuitions. Imagine a multiverse containing an infinity of possible worlds, whose total **measure** is 100%. Define the probability of an **event**, such as that of rolling a nine, to be the measure assigned to the subset of worlds in which the event actually occurs.

In the abstract formalism, we're allowed to assign the measure however we like, subject to Kolmogorov's axioms: the measure must be non-negative, countably additive, and sum up to 100%. Using the symmetry of an idealized die, we might argue that only one such assignment makes sense[^1]; from it, we can calculate the probability of any event involving dice rolls.

There are two shortcomings to this approach. Firstly, it doesn't generalize well to asymmetrical objects and events. Secondly, while a priori deductions are neat, we'd still like some means of *testing* probabilistic claims using real-life observations. Empirical testing presents a serious challenge: how can we hope to infer the measure on a hypothetical multiverse, when we only ever experience *one* world? Indeed, a realist might question if it makes any sense to discuss the *probability* of an event happening: either it happens or it doesn't!

# The economist's wager

You might be more trusting of someone who puts their money where their mouth is. To back up a definite claim, not involving chance, I can sign a contract, agreeing to pay a hefty fine if it turns out that I'm wrong.

This idea can be extended to probabilistic claims in the following manner: consider a lottery that pays a $90 jackpot if the next roll of a pair of dice yields a nine. If the maximum that I'm willing to pay to play is $10, this indicates that I believe I have a one in nine chance of winning. This approach is appealing because, after all, the *raison d'être* of probability theory is to explain the decision-making of individuals facing uncertainty.

If another gambler's view conflicts with mine, we may aggregate our beliefs by creating a market on which we buy and sell predictions. Consider a contract that pays $100 (plus interest) when a specified event occurs. Then, its price on the market can be interpreted as the percentage probability of that event. Thus, to say an event is twice as "likely" as another, simply means its contract's market price is twice that of the other.

Compared to the lone gambler, a frictionless market offers the advantage of transparent, near-identical buy and sell prices. As a result, any violations of Kolmogorov's axioms become money-making arbitrage opportunities. Arbitrage activity acts as an enforcer of the axioms, giving rise to what economists call the **risk-neutral probability measure**.

In real markets, however, this probability measure exhibits several inconsistenties. Firstly, it depends on which currency is used: as an extreme example, we'd never buy a dollar-denominated contract that only pays out if the dollar collapses, no matter how likely we imagine the collapse to be. Secondly, this measure is sensitive to non-diversifiable risk: if a widely-believed prophecy held that rolling a nine would induce a catastrophic famine, the market would value this outcome a lot more, because everyone would want to buy insurance against such a catastrophe. Thirdly, frictionless markets can be hard to set up in practice. And finally, markets can be misinformed: indeed, a common motivation for participating in a market is to try to beat it!

# Interlude: a hybrid approach?

The preceding approaches represent two extremes on a spectrum: the "objective" probability measure over some imagined multiverse, for which no empirical test exists; and the "subjective" gambling probabilities, which can be elicited by imposing suitable stakes. Can we get the best of both worlds? That is, does nature have any empirically meaningful notion of probability, consistent with our mathematical concept's objectivity (e.g., being independent of market idiosyncrasies)?

Every gambler alive today owes their existence to an intensive optimization process: Darwinian natural selection. As such, it makes sense to ask how an idealized Darwinian agent would act when faced with uncertainty. In general, this is a complex question (see for example, our earlier discussion of risk). To start easy, let's imagine that an agent, or a species, is faced with repeated instances of some scenario involving uncertainty. If the environment is sufficiently competitive, a necessary condition for survival is to attain the best cumulative outcome over a large number of trials. Thus, while a coin will always land either heads or tails, it's considered unwise to wager your life on either outcome. Intuitively speaking, the rationale is that you're almost certain to lose *eventually*, if you keep playing this way. This idea of repeated trials inspires our next interpretation, which is currently the most popular among scientists.

# The statistician's frequentism

According to the frequentist school of thought, a probabilistic statement is not to be taken literally as regarding one isolated event, but rather, as shorthand for a claim involving a very large collection of similar events. Thus, they bear a resemblance to *universally quantified* claims such as:

"*All swans are white.*"

The statement has an empirical meaning: we consider it to be true if it's impossible to find a counterexample, e.g., a black swan. Inferring it in practice is a bit trickier, of course: while a single black swan suffices to **falsify** the statement, we can never really **prove** it, short of checking every swan. If we see lots of swans in lots of different locations, and find that they're all white, then we may be inclined to believe the claim. Nonetheless, our observations cannot distinguish it from such alternatives as:

"*All swans that we saw by* [today's date] *are white, while all other swans are black.*"

If we're indifferent between the \\(2^S\\) assignments of black or white to a global population of \\(S\\) swans, then both hypotheses are equally good. Prior knowledge may lead us to prefer the first hypothesis, but this simply regresses the problem, since prior knowledge should itself be learned from data.

To avoid the baggage of common knowledge about swans, let's instead consider the sequence \\(2, 3, 5, 7, 11,\ldots,\\) whose elements are observed one at a time. Three hypotheses consistent with these starting terms are:

"*The sequence of prime integers in ascending order.*"

"*The sequence that starts at 2, adding 1 on the next term, adding 2 on each of the next 2 terms, and so on, doubling both the increment and the number of terms each time*."

"*The sequence whose n'th term is \\(\frac{1}{8}n^4 - \frac{17}{12}n^3 + \frac{47}{8}n^2 - \frac{103}{12}n + 6\\).*"

Depending on whether the next term is 13, 15, or 22, we'll be able to eliminate two of the hypotheses; nonetheless, no matter how many terms we see, there will always remain infinitely many possible extensions to the sequence. The **scientific method** demands that we collect fresh test data *after* selecting our hypothesis. So for example, if we choose the prime numbers hypothesis, and then observe the terms \\(13,17,19,23,29\\), we'll be justified in believing it.

The scientific method only works if we have a means of identifying good hypotheses. If we choose arbitrarily from a large collection of strange hypotheses (e.g., high-degree polynomials) that fit the first 5 terms, we'll be much more likely to match our test data by chance, than to get the right answer. In general, inductive learning is impossible without some sort of prior bias; this is known as the [No Free Lunch Theorem](https://en.wikipedia.org/wiki/No_free_lunch_theorem).

Now that we've seen how universally quantified claims run into empirical problems, let's complicate matters further by reintroducing probabilities. Returning to the probabilistic claim that began this article, its frequentist interpretation is as follows:

"*If a pair of standard dice are thrown repeatedly, then in the limit as the number of throws goes to infinity, the proportion of nines converges to one in nine (about 0.11 or 11%).*"

The one-roll probability is replaced by a long-run proportion. Given an infinite sequence of rolls, this statement unambiguously reveals itself to be either true or false. In light of the frequentist interpretation, we can even make more sense of our earlier interpretations. While we only experience one world, repeating an experiment under similar conditions is like observing the experiment in a parallel universe: whether we count trials or worlds, the math is virtually identical. Likewise, in the limit of infinitely many bets, we can make some unambiguous conclusions about the long-term success of a gambler's strategy: this is how casinos ensure that the house always wins!

Testing our claim is a simple matter: we roll the dice, over and over, and over and over... infinity times. Oops. Of course, there is no such thing as an experiment with infinity trials. Our arms will get tired, the dice will wear out, the Sun will explode, and all the free energy in the universe will be consumed. At best, we can do a very large number of trials. Let's say we roll the dice 9,000 times; one in nine of these would amount to 1,000. Perhaps we won't roll exactly 1,000 nines, so let's interpret our claim with a suitable margin of error, essentially an inverted **confidence interval**:

"*If a pair of standard dice are thrown 9,000 times, then the upward-facing sides will sum to nine between 920 and 1,080 times.*"

Skipping some calculations, it turns out the probability of obtaining between 920 and 1,080 nines is 99.3%. Thus, we've turned our probabilitic statement into a much more certain (but still probabilistic!) prediction. We would hope that observing 1,100 nines would falsify our claim, but things are no longer as clear-cut as our black swan example. Indeed, if every household on Earth were to independently perform this 9,000-throw experiment, probability theory predicts that a great many (about 0.7%) of their results would falsify our claim, *even if it's true*!

There's no getting around it: despite its intuitive appeal, the frequentist definition of probability is circular, reducing probability claims to probability claims. To close the cycle, the frequentist chooses a threshold (say, 99%) beyond which to treat likely predictions as definitive. If we count a number of nines that's outside the interval \\([920,1080]\\), we simply declare our probabilistic claim to be false. In practice, it seems fine to ignore sufficiently small chances of error: if 1% is not good enough, make it 0.0001%! Confidence can be increased by gathering more data, i.e., increasing the sample size.

This approach turns out to be very powerful. Even some phenomena which are not precisely repeatable, due to a dependence on uncontrollable parameters, can be statistically analyzed: we design more sophisticated hypotheses, or models, that generalize over those parameters. For example, weather forecasts are based on well-tested models that take measured input parameters such as temperature, pressure, humidity, and wind. The prediction probabilities coming out of such a model will vary as a function of its inputs.

Let's consider domains even more irregular than weather. Statistical models of sports games, democratic elections, or stock markets are hard to test: the interactions are very complex and there are too few outcomes from which to extrapolate. Similarly, in your own life, when you try to predict which colleges will admit you, which of your friends will start a business, whether you're being lied to, or whether extraterrestrial life eixsts, you don't base your conclusions on repeated trials of the same situation. Is it a stretch to view these as statistical inference problems? Perhaps, but there's no denying their importance and prevalence in ordinary decision-making. Let's push the frequentist methodology to its limits here, by proposing an even more general kind of hypothesis: it consists of a model of the world, perhaps encoded in some part of your brain, that makes probabilistic predictions in arbitrary scenarios. Presumably, this model won't be perfect. Since it can make a lifetime supply of predictions, one can design all sorts of tests to falsify it. But then, having falsified one model, how do we find a better candidate?

The last example is a bit extreme, going far beyond the capabilities of modern AI technology, let alone routine statistical analysis. Nonetheless, it exemplifies both the strengths and the weaknesses of the frequentist methodology. On one hand, we see how the methodology extends beyond the basic setting of independent, identically distributed trials. On the other hand, its use depends upon prior knowledge[^3]: before collecting observations, we must commit to a limited number of hypotheses and testable predictions. If we make too many predictions, it may happen that while each is 99% likely, their intersection is less than 1% likely. This stands in contrast with the universally quantified setting, in which we were free to test any number of predictions.

Since our testing "budget" is limited, we should design our tests to fail in the event that some plausible alternative hypothesis is true. In the brain example, our model certainly has many flaws, and even more potential fixes, but we must be judicious in choosing which fixes to consider. In the simpler dice example, you might have wondered why we chose the expectation-centered interval \\([920,1080]\\) as our prediction, rather than some other 99%-probability region. It's because we expected that, if our hypothesis were wrong, the most realistic alternative would be that our rolls are still independent and identically distributed, but with a modified frequency of nines. If we're certain that the frequency isn't lower, but suspect it may be higher, then the one-sided 99%-probability interval \\([0,1074]\\) is more likely to detect that: by specializing our alternative hypothesis, we increased the test's [power](https://en.wikipedia.org/wiki/Power_of_a_test).

Since the chances of obtaining exactly 1,000 nines are about 1%, another perfectly valid prediction region would be the set of all integers *except* 1,000! Does such a test ever make practical sense? Yes, if our suspicion (i.e., alternative hypothesis) is that the dice, rather than being random, are rigged to produce exactly 1,000 nines. Since every fixed number of rolls can be tested against in this way, *every* conceivable result will fail *some* test. The point is that the frequentist methodology derives its power by making a prior commitment to as few hypotheses as possible; as such, it cannot generate, nor universally compare, hypotheses.

To summarize, we now have a circular definition of probabilistic statements in terms of empirical predictions, which themselves have a probability of failure. To keep misprediction probabilities small, human judgment is invoked to ensure a curated selection of hypotheses and predictions. A priori, it's unclear whether any selection can be considered more valid than any other.

# The philosopher's razor

Suppose the universe were arbitrarily messy, complicated and irregular, its randomness devoid of any patterns; then, it would seem as if all events were decided by divine intervention. In such a world, there would be no role for science. The ancients believed in a magical world where everything, from weather to animal morphology, was subject to the daily whims of the Gods. Nevertheless, even the ancients believed in some basic patterns, which they could use to cook, hunt, navigate, build shelter, and otherwise live their lives. Without patterns to exploit, there would be no advantage for intelligent life, no reason for it to emerge. That there's a simple order underlying our universe, is one of its most remarkable characteristics. Let's take advantage of it.

If we don't know which hypothesis to test, we might begin by considering every hypothesis that comes to mind: potentially thousands, millions, or infinitely many. In the dice experiment, we might consider some strange hypotheses, such as ones where the chances of rolling doubles depend on which celebrity's credit card number was spelled out by the most recent rolls. Since no finite test is perfect, we would expect some fraction of these hypotheses to spuriously pass.

What makes the "true" hypothesis stand out from the many fakes? Well, the fakes are unlikely to stand up to additional testing. The more data we collect, the more contrived the hypotheses that we'll have to resort to; nonetheless, it will always remain possible to fit an incorrect hypothesis to all of the data seen so far. This is such a serious problem in science that it has a name: **overfitting**.

Somehow, we must narrow down our hypotheses. Maybe you think that's easy: only a few hypotheses describe plausible dice behavior; the rest are patently absurd! But now you're relying on intuitive judgment, not a rigorous methodology. If you try to sort out the source of your intuitive knowledge about how dice ought to behave, you'll find it to be rooted in your prior knowledge about how the world works, which itself must be tested against various hypotheses. If you have good prior knowledge and take it on faith, then this works fine in practice. However, it seriously begs the question: how do we manage to obtain *any* knowledge about the world in which we live?

There is a solution to this dilemma. For most of history, nobody knew how to state it in precise mathematical terms; hence, it was confined to the realm of philosophy. The solution to overfitting is the law of parsimony, **Occam's razor**:

"*Given competing theories that can explain our observations, always prefer the simplest.*"

If we take "simple" to mean that it must be described by a short English sentence, then there are only a limited number of such sentences. By restricting ourselves to this limited number, it becomes possible to eliminate all the bad hypotheses with a finite amount of data.

Thus, we see that Occam's razor provides the prior bias that traditional frequentist theories lacked. In order to complete this idea, we must make it precise, and justify its univeral applicability to hypothesis selection. The advent of computer science gave us a theoretical framework in which to do so. With it comes not only a cleaner interpretation of probability, but also a general theory of inference with Occam's razor at its front and center.

# The computer scientist's electric razor

English sentences can be a bit ambiguous so, for precision's sake, we'll express our hypotheses as computer programs, and encode our observations as computer data. If you're not a programmer, rest assured that it's mostly kosher to replace the programs in our discussion with instructions written in your mother tongue.[^4] In the computer science framework, we restate Occam's razor as follows:

"*Given competing programs whose outputs match our observations, always prefer the shortest.*"

Let's see just how powerful this definition is. Right away, we see there's no longer a need to carefully select hypotheses or tests, as both are built-in: all computer programs are hypotheses, with preference given to shorter ones. Testing a program amounts to verifying that its output exactly matches our observation record.

At first blush, the requirement to use deterministic programs appears to be a limitation. Luckily, randomized programs can be made deterministic by supplying the results of "coin flips" as an extra string of ones and zeros. This string makes the program longer, so Occam's razor will prefer explanations that don't depend on too much randomness, if one exists.

Given a string \\(x\\), perhaps representing a very long sequence of observations, the length of the shortest program that outputs \\(x\\) is called its **Kolmogorov complexity** \\(K(x)\\). By prioritizing programs by their length, we ensure that each incumbent theory only competes against finitely many rival hypotheses. While one might imagine prioritizing programs by other criteria, it turns out that any computable criterion can be turned into a description language for \\(x\\), and is therefore dominated by the Kolmogorov complexity. See the footnotes for an excellent technical reference,[^5], as well as a more accessible overview.[^6] We won't go deeply into the theory here, but merely highlight how it helps us interpret and infer probabilistic statements.

Classical information theory studies the optimal rate at which random objects can be compressed. If the objects are drawn from a known probability distribution \\(\mathcal P\\), then *on average*, the number of bits needed to compress one object is equal to a quantity known as the **entropy** \\(H(\mathcal P)\\). No compression algorithm can beat this on average. In general, it's unclear whether we should care about the average, as opposed to the median, mode, maximum, or some other statistic.

But now, suppose we independently sample a very large number \\(N\\) of objects from \\(\mathcal P\\). The Law of Large Numbers tends to make totals proportional to averages: almost certainly, the total encoding length of the entire sequence of objects will be very close to \\(N\cdot H(\mathcal P)\\). The sequence's Kolmogorov complexity will not be much greater: a suitable program consists of a description of \\(\mathcal P\\), along with the classical encoding (optimized for \\(\mathcal P\\)) of each object in the sequence, for a total complexity of approximately \\(K(\mathcal P) + N\cdot H(\mathcal P)\\).

If there's no significantly shorter program that generates the same sequence, then the above program meets our defintion of a good theory to explain the sequence: it is approximately the simplest. That is, we can now look at an *individual* string \\(x\\), and determine whether or not it looks like a sequence of random draws from \\(\mathcal P\\). For example, consider the following sequence:

\\(3,1,4,1,5,9,2,6,5,3,5,8,9,7,9,3,2,3,8,4,6,2,6,4,3,3,8,3,2,7,9,5,0,2,8,8,4,1,9,7\\)

This will *not* pass as a random sequence of rolls from a pair of fair dice (with sides numbered 0 to 5, to ensure all digits are representable). Why? To interpret it as such, we must include an encoding for each digit. This might be slightly shorter than writing the sequence literally, but it's much longer than the phrase: "*first forty digits of pi*".

If it were possible to algorithmically compute the shortest program that outputs any given \\(x\\), we would have a ridiculously powerful inference engine. For instance, we could feed it a bunch of data from physics experiments, and out comes a fully-formed scientific theory, better than any we know today. Naturally, such a thing is too good to be true. For fundamental reasons related to the theory of proofs and computation, the Kolmogorov complexity is not computable.[^7] Thus, we can only try our best to discover the most parsimonious explanations we can, never knowing how close we are to the best possible. Occam's razor can distinguish good and bad hypotheses and, unlike pure frequentism, resists abuse by a barrage of ridiculous hypotheses. Nonetheless, it takes some ingenuity, or luck, to discover a good hypothesis.

In a sense, that's exactly what the pursuit of scientific theories is about. The ancients would be astounded to learn that so much of the world (perhaps all of it!), with its vast richness, can be described by a few simple laws. Over the centuries, we've found more and more patterns, making our theories ever more parsimonious. The scientific method only works because the rules of the universe happen to be simple, while the set of observations it offers is vast. Kolmogorov complexity captures this defining characteristic of our reality.

# Next time...

In the sequel, we'll see that in pretty much any world where inference is possible, the Kolmogorov complexity approach applies. Thus, we'll come to understand the limits of knowledge. Analogous issues will crop up in the Kolmogorov complexity methodology, via an ambiguity in the definition that we've overlooked until now: namely, the choice of computer programming language. Nonetheless, we'll find that it's possible to mostly mitigate the issues we found with frequentism. Finally, we'll see what this means in practice, for probabilistic claims and their inference.

[^1]: A more convincing argument might also use the roll's chaos and ergodicity. However, this requires an initial source of randomness, putting us back where we started.

[^3]: Ironically, supporters of frequentism have been known to apply precisely this critique to the rival Bayesian school of thought, denouncing it for relying upon unjustified prior knowledge. In the sequel to this article, we'll see how the **universal prior** completes both the frequentist and the Bayesian interpretations.

[^4]: That said, we can start to appreciate why a basic education in computational thinking is fundamental to understanding nature, just as math and science courses are.

[^5]: Ming Li and Paul Vitanyi. 2019. An Introduction to Kolmogorov Complexity and Its Applications (4th. ed.). Springer Publishing Company, Incorporated.

[^6]: Rathmanner, S., & Hutter, M. (2011). A philosophical treatise of universal induction. Entropy, 13(6), 1076-1136.

[^7]: The uncomputability of \\(K(x)\\) has to do with the fact that it's hard to distinguish a program that takes absurdly long to run, from one that never finishes. Since an absurdly slow program is fairly useless, we might decide to include resource bounds in our complexity measure (see Chapter 7 from Li & Viyanyi). For instance, while the Standard Model of particle physics might in principle describe all of life's processes, a supercomputer would struggle to simulate even one atom this way. To make useful inferences, we also need the theories of chemistry, biology, and the social sciences. Unlike \\(K(x)\\), resource-bounded measures can be computed by trying every possible program until the resource bounds are exhausted. Of course, this still isn't very practical, as the number of programs to try would be astronomical.
