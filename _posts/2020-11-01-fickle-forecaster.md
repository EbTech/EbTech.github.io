---
layout: mathpost
title:  "How fickle should a forecaster be?"
date:   2020-11-01
categories: economics
tags: prediction martingales
---
Suppose one day, I say to you that there's a 20% chance of rain next weekend. Or that there's a 20% chance of Donald Trump being elected for another term as President of the United States. Upon reading about some scandal the next day, I revise my prediction to 85%. By nighttime the matter settles, so I announce my updated prediction of 5%. In the end, it doesn't rain (or Joe Biden defeats the incumbent).

After following a bunch of my forecasts, you might criticize me for being too fickle, my predictions swinging wildly as if I can't make up my mind. Or you might think the opposite: that I play it too safe, only shifting my opinion to one side when the evidence becomes overwhelming.

What's the right amount of variation? Is it a thing that can be measured?

Yes it is! In this blog post, I propose the sum of squared changes as such a measure.

First, a formal derivation. If you're not into the technicalities of probability theory, the next section can be skipped. We'll understand its implications afterward.

# A formal interlude

Let \\(X_t\\) be a bounded martingale adapted to the filtration \\(\mathcal F_t\\),[^1] and let \\(0 = T_0 \le T_1 \le \ldots \le T_N\\) be stopping times. Then,

$$
\begin{aligned}
\mathbb E\Big( \sum_{n=1}^N (X_{T_n} - X_{T_{n-1}})^2 \mid \mathcal F_0\Big)
&= \mathbb E\Big(X_{T_N}^2 - X_{0}^2 + 2 \sum_{n=1}^N  X_{T_{n-1}} (X_{T_{n-1}} - X_{T_n}) \mid \mathcal F_0\Big)
\\&= \mathbb E(X_{T_N}^2 \mid \mathcal F_0) - X_{0}^2 + 2 \sum_{n=1}^N  \mathbb E\Big(X_{T_{n-1}} (X_{T_{n-1}} - X_{T_n}) \mid \mathcal F_0\Big)
\\&= \mathbb E(X_{T_N}^2 \mid \mathcal F_0) - X_{0}^2 + 2 \sum_{n=1}^N  \mathbb E\Big(X_{T_{n-1}} \underbrace{\mathbb E(X_{T_{n-1}} - X_{T_n} \mid \mathcal F_{T_{n-1}})}_{=0} \mid \mathcal F_0\Big)
\\&= \mathbb E(X_{T_N}^2 \mid \mathcal F_0) - X_{0}^2
\end{aligned}
$$

Let \\(X_t\\) be the \\(\mathcal F_t\\)-conditioned probability of some event whose outcome is determined by time \\(T_N\\). This is a martingale for which \\(X_{T_N}\\) is \\(1\\) with probability \\(X_0\\), and \\(0\\) otherwise. Hence, \\(\mathbb E(X_{T_N}^2 \mid \mathcal F_0) = X_0\\).

# And we're back!

So what have we shown? In essence, the martingale \\(X_t\\) represents the prediction at time \\(t\\). The role of the *stopping times* is to grant the forecaster some flexibility: they don't have to announce predictions at *every* time \\(t\\), nor even at pre-specified intervals. All that matters is that the decision on whether or not to announce a prediction at time \\(t\\) be made by time \\(t\\); deciding to withhold a prediction based on information from the future would be cheating! As long as this rule is satisfied, we can just add up the squared changes in the forecaster's predictions to get a measure of their fickleness. If the forecaster reports genuine conditional probabilities, the first of which was \\(X_0\\), then on average this sum should equal \\(X_0 - X_0^2\\).

Using the example we started with, \\(X_0 = 0.2\\), so \\(X_0 - X_0^2 = 0.16\\). Our prediction series was \\((0.2,\, 0.85,\, 0.05,\, 0)\\), so the sum of squared changes is

$$ (0.2 - 0.85)^2 + (0.85 - 0.05)^2 + (0.05 - 0)^2 = 1.065$$

This is a lot more than the expected \\(0.16\\). Is the gap statistically significant enough to support your critique that my predictions are too fickle? The ratio between a positive random variable and its expectation is known by statisticians as an *e-value*. In this case, it is \\(1.065 / 0.16 \approx 6.66\\). E-values between \\(4\\) and \\(10\\) are considered *substantial* evidence, while e-values above \\(10\\) are *strong* evidence. As an exercise, you can calculate the e-value for a prediction series from a well-known forecaster, such as FiveThirtyEight!

# Trading on volatility

Aside from professional forecasters such as FiveThirtyEight or your local weather channel, another source of prediction series are public markets, such as PredictIt. There, you can purchase any number of contracts which pay out \$1 each, if the corresponding event comes to pass. If "Donald Trump wins the presidency" contracts sell for 40 cents apiece, one may say that the market of buyers and sellers have collectively estimated his chances at 40%.[^2] Assuming no interest, transaction fees, or other frictions in the market, "Donald Trump doesn't win the presidency" contracts must then sell for 60 cents apiece, ensuring that the two opposing contracts precisely cancel out.

Now, let's say you don't know which event will come to pass, but you're confident that the prediction market is more volatile than a true martingale, meaning that its sum of squared deviations will exceed the expected \\(X_0 - X_0^2\\). Is it possible to bet on this outcome, making a profit if it comes to pass?

Again, the answer is yes. The general strategy is to ensure that, at every point in time, we hold contracts on the side that's deemed *less* likely to win. The number of contracts we hold should be in proportion to the difference between the two sides. For example, if we buy one contract for 40 cents, then we should sell it when its price rises to 50 cents. If it then shoots up to 80 cents, we should buy three of the *opposite* contract, for 20 cents apiece, and so on. Can you prove that this method works?

In fact, every e-value can be interpreted as a betting strategy.[^3] The intuitive idea is that if you do not believe my probabilistic forecasts, you can propose a bet that I should be willing to accept if I believe my own forecasts. If you end up much richer, that serves as strong evidence against my forecasts.

[^1]: *Filtration* is a very technical term, but you can think of \\(\mathcal F_t\\) as all of the information known at time \\(t\\).

[^2]: More precisely, 40% would be what economists call the *risk-neutral measure* of such an event.

[^3]: Aaditya Ramdas, Peter Grünwald, Vladimir Vovk, and Glenn Shafer, 2023. Game-theoretic statistics and safe anytime-valid inference. Statistical Science, 38(4), pp.576-601. The connection to e-values was added to this blog post in 2024.
