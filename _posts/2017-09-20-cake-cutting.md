---
layout: mathpost
title:  "How to cut your cake and eat it too"
date:   2017-09-20
categories: game-theory
tags: cake cutting fair division rationality
---
A classic challenge goes as follows: in the absence of precise measurements, how would you divide a cake between two diners so that both agree they got a fair share? The cake, naturally, is a metaphor: it can stand for any bundle of goods that should be divided between parties.

In the case of two diners, the classic solution is [I cut, you choose](https://en.wikipedia.org/wiki/Divide_and_choose). If I let you inspect and choose between the two pieces, I can't easily cheat you: if the pieces are uneven, you'll go for the best one. Knowing this, I have an incentive to make the most equal cut that I can manage. We'll each end up with about half the cake: I'll lose no more than my own measurement error when cutting; likewise, you'll lose no more than your own measurement error when inspecting. Seems fair.

Now, in real life, who would you rather be: the cutter or the chooser? I think the chooser is better off. The cutter has to do all the work of being precise, and in the end will probably end up with a slightly smaller piece. The chooser, on the other hand, can always choose the best piece. It that's too difficult, they can just choose randomly, and still be guaranteed half the cake on average.

We've been deliberately vague about the nature of the problem: rather than stating it in mathematical terms, we used our intuition regarding cakes and knives. This got me thinking: is there any setting where it's better to be the cutter instead of the chooser?

# First attempt

The first idea that comes to mind is deception: maybe I can cut the cake so that the smaller piece *looks* bigger. However, if the cut looks fishy, a distrustful chooser has the easy defense of choosing randomly, say by tossing a coin. If the cake is homogeneous, this always works.

# Second attempt

In our quest to make the cutter win, let's look at a fancier cake: this one has 10 berries and 10 cherries on top. I love berries but don't care much about cherries. Meanwhile, you adore cherries but couldn't care less about berries. Knowing your tastes, how about I cut the cake so that one piece has all 10 berries but only 4 cherries? Then you'll prefer the other piece, with 6 cherries. While that's an ok deal for you, I'm the clear winner since I keep everything that's valuable to me.

If you're rational according to the classical definition used by economists and game theorists, it appears you have no recourse. However, an "irrational" chooser can punish me by taking the 10-berries piece. This spiteful strategy carries a cost for you, but it's less than the damage done to me. You still get 4 cherries (instead of 6), while I'm effectively empty-handed.

Spite seems like an expensive strategy. However, the implied threat of punishment might deter me cutting greedily, so that you'll rarely pay the price in practice. If I believe that you would take revenge if wronged, then I'll take care to cut in a fair manner.

# Wait, really?

Classical game theory doesn't predict spite; one may argue this to be a flaw in the theory itself. Sure, we can invent workarounds: for instance, by employing fancy social contracts or threats that are costly to lie about. However, I feel that the framework of Updateless Decision Theory offers a cleaner abstraction to explain such behavior. Perhaps I'll write about UDT, or about the power of good abstractions more generally, in a future post.

For readers who are unacquainted with applied math research, the takeaway is that one's assumptions, whether stated or implied, can affect the outcome. We haven't formally defined what fairness means, nor how the diners behave. Unless we clarify our assumptions, it's impossible to narrow down to one right answer: the chooser may be classically rational, or they may be spiteful. If you happen to have the math background, I leave it as an exercise to formalize, and then generalize, the arguments in this post!

# Last attempt

Ok, so I still can't win against a spiteful chooser. It appears I'm doomed whenever our utilities are additive. Additive utility, here, is just a fancy way of saying we enjoy a piece of cake exactly as much as the sum of its parts, not caring about special combinations.

But now suppose the "cake" is actually a basket of different items, some combinations of which form recipes that I enjoy, while other combinations form recipes that you enjoy. To construct a very simple example, let's say the cake contains not only berries and cherries, but also chocolate chips and vanilla chips. I enjoy berries only when they're mixed with chocolate, and I enjoy cherries only when mixed with vanilla. For you it's the reverse: berries require vanilla and cherries require chocolate.

Now as the cutter, I can cut the cake so that one piece contains mostly berries and chocolate, while the other contains mostly cherries and vanilla. No matter which you choose, you'll be unhappy and I'll be happy. If I were more considerate, I could make us both happy by splitting everything equally. However, if the cake had just one (indivisible) topping of each type, then only the cutter can win. Sweet victory!

![Cake](http://oboi-dlja-stola.ru/file/1725/760x0/16:9/%D0%9A%D0%B5%D0%BA%D1%81-%D1%81-%D1%8F%D0%B3%D0%BE%D0%B4%D0%B0%D0%BC%D0%B8.jpg)
