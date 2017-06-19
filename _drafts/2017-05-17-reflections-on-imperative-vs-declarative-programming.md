---
layout: mathpost
title:  "Reflections on Imperative vs Declarative Programming"
date:   2017-06-17
categories: rust programming
---
Woo finally, time to launch a blog!

$$a^2 + b^2 = c^2$$

To preface with a warning: this blog will often broach subjects I'm wholly unqualified to talk about. I may be wrong about a lot of things, in which case you should correct me to prevent the spread of bad ideas! The subject of programming languages is ripe with deep theory, real-world controversy, and divergent schools of thought. With that said, I approach this subject not as a mere intellectual curiosity, but as a stakeholder. You, the reader, are a stakeholder too. As users of computing devices, we hope the systems on which we base our lives function reliably and safely. As developers, our power to subvert the laws of physics to our bidding depends on our ability to express the desired transformations, incantations, via a code. While there are many technologies needed for this to work, none interface between the minds of a human and machine as intimately as the programming language. A good language frees us from unnecessary mental burdens, prevents errors, and allows us to focus our full attention on solving the problem at hand.

The idea is more general than programming. Our civilization's collective understanding of the world improves over the years. As it does, we refactor deep ideas, learning to express them in simpler terms. Once upon a time, nobody but Einstein could make sense of special relativity. Nowadays, we teach it to kids through [video games](http://www.testtubegames.com/velocityraptor.html). See [Judea Pearl's Causality: Models, Reasoning, and Inference](http://bayes.cs.ucla.edu/BOOK-2K/) for another example, where a clean mathematical language enabled our understanding of scientific causality to progress from what seemed like fuzzy nonsense into a powerful practical concept. In summary, the tools of abstraction and generalization enable us to simplify our understanding of old concepts. Thus, we can focus our attention on new problems, affectively augmenting our mental capabilities. I suspect this phenomenon is largely responsible for the Flynn Effect, whereby each generation performs much better than its predecessor on IQ tests. The Internet amplifies this effect by making information free and enabling people to teach one another how they think, thus rapidly iterating upon concepts. It is my opinion that a good explanation should be thought of as a kind of technology in and of itself, similar to a mathematical discovery or an algorithm.

Returning to programming, we're seeing a rise in so-called multi-paradigm languages, which combine aspects of imperative and functional programming. Seeing this got me thinking back to the controversial divide as was taught in school. What makes a language imperative or functional? Which paradigm is better-suited to real-life software development?

According to Wikipedia, functional programming is a particular kind of declarative programming. In this post, I'll only try to contrast imperative with declarative styles. Wikipedia offers the following distinctions to define [declarative programming](https://en.wikipedia.org/wiki/Declarative_programming#Definition):

1. A program that describes what computation should be performed and not how to compute it
2. Any programming language that lacks side effects (or more specifically, is referentially transparent)
3. A language with a clear correspondence to mathematical logic.

Point (3) seems kind of vague since every language can be described mathematically; it would essentially come down to which language looks more "math-like". The first two points make this a bit more precise.

Point (1) is interesting. Ideally, when I call a software routine to, say, compute the sum of the squares of a bunch of numbers, I don't want to worry about how exactly the routine is implemented: whether we start summing from the left or the right, how the data is split between threads for fast parallelism, or any numerical tricks used to reduce rounding errors. What I want is a *layer of abstraction*. By calling a function sum_squares(v), I'm saying that I want the sum of the squares of everything in v. I'm only concerned with the end result, not at how it's obtained. This function can be defined in pretty much any language, to give this abstraction. But how do we implement sum_squares() so that the computer knows what to do when someone calls it? How do we explain the concept of squaring and then summing to a computer, in order to automate it? In an imperative language, we'd have to write a loop as follows:

{% highlight rust %}
fn sum_squares(&[i32] v) -> i32 {
  let mut accumulator = 0;
  for elem in v {
    accumulator += elem * elem;
  }
  return accumulator;
}
{% endhighlight %}

Unfortunately for the mathematical purists, this involves defining all the steps in arriving at a solution, with a mutable accumulator holding the final result. The functional programming equivalent is bit nicer, invoking general-purpose abstractions such as map() and fold() that operate on first-class functions:

{% highlight rust %}
fn sum_squares(&[i32] v) -> i32 {
  v.map(|x| x*x).fold(0, add)
}
{% endhighlight %}

Here we avoided the use of mutable state. It looks more like abstract math, though you kinda have to squint to see it. If we want smarter behavior regarding parallelism and rounding errors, we'd still have to describe these aspects of the algorithm somehow. And for more advanced concepts such as the minimum spanning tree, following the simplest definition blindly would lead to an expensive brute force search.

Truly declarative programming only makes sense for use cases where the bottleneck algorithm can be known by the compiler in advance, such as indexing in SQL, unification in Prolog, or backpropagation in TensorFlow [^1]. For bare-metal programming, even in a so-called functional language, we can at best make the code look a little bit more like the "what", while still specifying the *how*.

That leaves point (2). This too is a good principle, but again the distinction becomes fuzzy. For instance, is this Rust function signature referentially transparent?

{% highlight rust %}
fn do_something(a: &mut A, b: &B) -> C;
let c = do_something(&a, &b);
{% endhighlight %}

The answer can be yes, if we think of it as a function mapping (a, b) to (a, c)! The value assigned to a will change after the function call, but we can think of the latter a as a brand new binding that just so happens to also be called "a". It's equivalent to the following:

{% highlight rust %}
fn do_something2(a: A, b: &B) -> (A, C);
let (a, c) = do_something2(a, &b);
{% endhighlight %}

Sometimes it's convenient to reuse names, to better reflect our mental model or our hardware's complexity model in the case of small modifications to a large object. Readers familiar will Rust will notice that rather than taking a reference to a, do_something2() *consumes* its old value, rendering it inaccessible afterwards. If you were interested in maintaining access to both values of a, before and after modifications, then what's needed is a *persistent data structure*. For more, see [Erik Demaine's lecture](https://www.youtube.com/watch?v=T0yzrZL1py0) on time travel.

The above examples were all In Rust. The function signature specifies all the possible side-effects; thus, after a straightforward mental transformation, we get almost [^2] full referential transparency. The compiler can apply similar reasoning to make various optimizations.

So, is Rust imperative or declarative? The distinction doesn't seem too well-defined. I'd say the style is imperative. Rust code tends to describe quite explicitly how a computation will be performed. And yet it provides most of the practical benefits of a pure functional language (certainly the case when you consider C/C++ as the baseline, although that might just be because those are very poor imperative languages).

As computers become more powerful, a variety of special-purpose high-level programming languages will take off. Machine learning libraries such as TensorFlow are typical examples, in which a programmer declares their intention and can omit at least some parts of the underlying algorithm. However, within the sphere of general-purpose high-performance code, it appears imperative programming has its benefits.

[^1]: Note that even comparatively "low-level" languages may hide some details under abstractions, if it's assumed the programmer shouldn't worry about them. Java has garbage collection, and C++ leaves many choices to the compiler, which in turn leaves some choices to the operating system and hardware. The abstractions in C/C++/Rust aim to be very low-cost. They may even be negative-cost if the compiler is able to optimize better than a typical programmer.

[^2]: With a very important caveat: interactions with the "outside world", such as I/O operations, are not captured in Rust's type system.
