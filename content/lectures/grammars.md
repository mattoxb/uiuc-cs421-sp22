---
title: Grammars
date: 2021-06-14
type: book
weight: 14
hidden: []
links:
  - category: Videos
    links:
      - title: Introduction to Grammars
        display: true
        url: /videos/introduction-to-grammars
      - title: First Sets
        display: true
        url: /videos/first-sets
      - title: Follow Sets
        display: true
        url: /videos/follow-sets
  - category: Handouts
    links:
      - title: Grammars Activity (TPS version)
        display: true
        url: /handouts/grammars-tps.pdf
      - title: Grammars Activity (POGIL version)
        display: true
        url: /handouts/grammars-pogil.pdf
      - title: Grammar Activity Solutions
        url: /handouts/grammars-activity-solution.pdf
  - category: Further Reading
    links:
      - title: FIRST and FOLLOW Sets (an implementation)
        display: true
        url: /handouts/first-and-follow-sets.pdf
---

## Synopsis

We have talked a lot at this point how to manipulate abstract syntax trees to interpret a
computer program.  But how do we generate those abstract syntax trees in the first place?
We start off with a mathematical description of a language --- or more accurately, a
mathematical description of the valid sentences of a language --- and use that to build
a tool to build a parser.

This "mathematical description" is called a *grammar*, and there are a lot of things
you will need to understand about them to make them useful to you.

{{< links >}}
