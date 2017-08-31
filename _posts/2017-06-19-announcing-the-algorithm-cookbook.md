---
layout: mathpost
title:  "Announcing the Algorithm Cookbook"
date:   2017-06-19
categories: algorithms
tags: rust algorithm cookbook programming language contest
---
I built a reference cookbook of algorithms and data structures for contest problem solvers. It's written in the Rust programming language, as I believe it's ideally suited to the task. For more info, please check out the repository at [github.com/EbTech/rust-algorithms](https://github.com/EbTech/rust-algorithms).

[![Codeforces](http://stat.codeforces.ru/images/codeforces-logo-with-upper-beta.png)](http://codeforces.com) [![Rust](https://www.rust-lang.org/logos/rust-logo-128x128.png)](https://www.rust-lang.org)

While I believe Rust is not too difficult in absolute terms, it does present a significant departure from most developers' mental models. If you'd like to practice the language on small toy problems, contests can serve as a useful playground. Unfortunately, it's hard to get started when there are still so few examples of Rust contest code out in the wild, and no established guidelines to tie Rust's compile-time discipline with the constraints of contest programming. This project seeks to remedy the situation.

Note that it's not meant to act as a full-fledged general-purpose library. Contest problems often require understanding an algorithm so well that you can dig in and make subtle modifications to make it suitable for a brand new problem. Therefore, in this setting, one ought not to rely on blackbox implementations. Instead, I try to distill each algorithm into its simplest possible form, so that you can quickly read over the code, understand it, and augment it to suit your needs.

[Rust](https://www.rust-lang.org) and [Codeforces](http://codeforces.com) represent two of my favorite technology communities, so I'm interested to see how they can support each other. If you're a Rust programmer interested in honing your technical interview skills or solving cool algorithmic puzzles, you might enjoy Codeforces. If you're a Codeforces member and find that debugging is a huge time drain, Rust's emphasis on safety may give you a competitive edge. In either case, I hope this reference will help ease the learning curve. I'm still learning too; suggestions are welcome!

