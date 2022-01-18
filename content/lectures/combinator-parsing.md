---
title: Combinator Parsing
date: 2021-06-21
type: book
weight: 18
hidden: []
links:
  - category: Videos
    links:
      - title: Combinator Parsing
        url: /videos/combinator-parsing
        display: true
      - title: Combinator Parsing Activity
        url: /videos/combinator-parsing-activity
  - category: Handouts
    links:
      - title: Combinator Parsing Activity (TPS Version)
        url: /handouts/combinator-parsing-tps.pdf
        display: true
      - title: Combinator Parsing Activity (POGIL Version)
        url: /handouts/combinator-parsing-pogil.pdf
        display: true
  - category: Further Reading
    links:
      - title: Monadic Parser Combinators (Graham Hutton)
        url: http://www.cs.nott.ac.uk/~pszgmh/monparsing.pdf
        display: true
        desc: This paper is a tutorial about monads and parser combinators. It uses a language called Gopher, a precursor to Haskell.
---

## Synopsis

We have seen a few different kinds of parsers to this point.  They all work by constructing
state machines to handle the parsing.  A new class of parsers has started to become popular
lately.  Combinator parsers use functions to represent parsers, and they can be composed together
to make more sophisticated parsers.

We will show how to build one of these from the ground up, and make use of monads to give us
a natural syntax.

{{< links >}}
