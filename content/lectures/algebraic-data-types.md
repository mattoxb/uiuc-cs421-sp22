---
title: Algebraic Data Types
linktitle: Algebraic Data Types
date: 2021-05-21
type: book
weight: 3
hidden: []
links:
  - category: Videos
    links:
      - title: Product Types
        display: true
        url: /videos/product-types
      - title: Sum Types, Part 1
        display: true
        url: /videos/sum-types-pt1
      - title: Sum Types, Part 2
        display: true
        url: /videos/sum-types-pt2
  - nocategory: Activitites
    links:
      - title: TPS version
        display: true
        url: /handouts/adt-tps.pdf
      - title: POGIL version
        display: true
        url: /handouts/adt-pogil.pdf
      - title: Algebraic Data Type Activity Walkthrough (Spring 2021)
        display: true
        url: https://mediaspace.illinois.edu/media/1_tpfgtxfa
      - title: Algebraic Data Type Activity Walkthrough (Fall 2020)
        display: true
        url: https://mediaspace.illinois.edu/media/1_e4ibuw6u
  - category: Further Reading
    links:
      - title: Generalized Algebraic Data Types
        display: true
        url: https://en.wikibooks.org/wiki/Haskell/GADT
        desc: There is a more general version of the product types supported by the language.  They are more powerful than the types we will use in class, and you may find them useful in your own programming.
---

If a language is to be extensible at all, it has to give the programmer a way to define new types.
<Sc>Haskell</Sc> provides user-defined disjoint types as one of its solutions to this problem.  A disjoint
type is a type that has more than one kind of constructor.  These turn out to be very useful in
representing expressions of a programming language internally, so we will make heavy use of them.

We will also cover pairs, which we will use a lot, and records, which we will use infrequently.

{{< links >}}
