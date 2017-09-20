---
layout: mathpost
title:  "How to cut your cake and eat it too"
date:   2017-09-20
categories: game-theory
tags: cake cutting fair division rationality
---
A classic challenge goes as follows: in the absence of precise measurements, how would you fairly divide a cake between two diners? The cake, naturally, is a metaphor: it can stand for any basket of goods that should be divided between parties.

In the case of two diners, the classic solution is [I cut, you choose](https://en.wikipedia.org/wiki/Divide_and_choose). If I let you inspect the pieces and choose, I can't easily screw you over. Knowing this, I have an incentive to make the most equal cut that I can manage. We'll each end up with about half the cake: I may lose only to the extent of my own measurement error when cutting; likewise, you may lose only to the extent of your measurement error when inspecting.

Now, in real life, who would you rather be: the cutter or the chooser? The chooser seems better off. The cutter has to do all the work of being precise, and in the end will probably end up with a slightly smaller piece. The chooser, on the other hand, can always choose the best piece. It that's too much work, they can just choose randomly, and still be guaranteed half the cake on average.

We've been deliberately imprecise about the nature of the problem: rather than stating it in mathematical terms, we used our intuition regarding cakes and knives. This got me thinking: are there any cases where it's better to be the cutter instead of the chooser?

The first approach that comes to mind is deception: maybe I cut the cake so that the smaller piece *looks* bigger. However, if the cut looks fishy, a distrustful chooser has the easy defense of choosing randomly, say by tossing a coin. If the cake is homogeneous, this always works.

In our quest to make the cutter win, let's try a fancier cake with 10 berries and 10 cherries on top. I love berries but don't care much about cherries. Meanwhile, you adore cherries but couldn't care less about berries. What if I cut the cake so that one slice has all 10 berries but only 4 cherries? Then you'll prefer the other piece, with 6 cherries. That's an ok deal for you, but I'm the clear winner since I keep everything that's valuable to me.

If you're rational according to the classical definition used by economists and game theorists, it appears you have no recourse. However, an "irrational" chooser can punish me by taking the 10-berries slice. This spiteful strategy carries a cost for you, but it's less than the damage done me. In this case, you still get 4 cherries while I effectively have nothing.

Spite seems like an expensive strategy. However, in practice, the implied threat of punishment should be enough to prevent me from getting greedy. If I think that you would take revenge, I'll take care to cut in a fair manner. 

Classical game theory doesn't predict spite; one can argue this to be a flaw in the theory itself. Sure, we can invent workarounds, for instance by employing fancy social contracts or threats that are costly to lie about. However, a clearer abstraction that explains such behavior is given in the framework of Updateless Decision Theory. Perhaps I'll write about UDT, or the power of good abstractions more generally, in a future post.

Ok, so I still can't win against a spiteful chooser. It appears I'm doomed whenever the utility function is additive. Additive, here, is just a fancy way of saying that I enjoy each small piece of cake in isolation, without caring about special combinations.

But now suppose the "cake" is actually a basket of different items, some combinations of which form recipes that I enjoy, while other combinations form recipes that you enjoy. To construct a very simple example, let's say the cake contains not only berries and cherries, but also chocolate chips and vanilla chips. I enjoy berries only when they're mixed with chocolate, and I enjoy cherries only when mixed with vanilla. For you it's the reverse: berries must have vanilla and cherries must have chocolate.

Now as the cutter, I can cut the cake so that one piece contains mostly berries and chocolate, while the other contains mostly cherries and vanilla. No matter what you choose, I'll be happy and you'll be unhappy. If I wanted to be nice, I could just split everything equally. However, if cake only had one (indivisible) topping of each type, then only the cutter can win. A sweet victory!

![Cake](http://oboi-dlja-stola.ru/file/1725/760x0/16:9/%D0%9A%D0%B5%D0%BA%D1%81-%D1%81-%D1%8F%D0%B3%D0%BE%D0%B4%D0%B0%D0%BC%D0%B8.jpg)

[^1]: Note, however, that grey is effectively a darker white, and brown is a darker orange. Our perception makes relative comparisons that take context, light sources and shadows into account. Optical illusions take advantage of this. By necessity, this exposition contains simplifications.
