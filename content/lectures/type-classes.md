---
title: Type Classes
date: 2021-06-07
type: book
weight: 11
links:
  - category: Handouts
    links:
      - title: Annotated type class example
        url: /code/annotate_type_classes.hs
  - category: Videos
    links:
      - title: Type Classes
        display: true
        url: /videos/type-classes
      - title: Functors and Applicative
        display: true
        url: /videos/functors-and-applicatives
      - title: Activity Walkthrough (Fall 2020)
        url: https://mediaspace.illinois.edu/media/1_dv30ngkn
      - title: Activity Walkthrough (Spring 2021)
        url: https://mediaspace.illinois.edu/media/1_nkpvx62x
  - category: Further Reading
    links:
      - title: The Typeclassopedia
        display: true
        url: https://wiki.haskell.org/Typeclassopedia
        desc: Read this if you want a broader understanding of type classes.
      - title: Variadic functions in Haskelll
        display: true
        url: http://okmij.org/ftp/Haskell/polyvariadic.html
        desc: They used type classes to trick Haskell into allowing us to have functions with a variable number of parameters!
---
## Synopsis

Most languages support polymorphism of one sort or another. In the type classes video we will
discuss some of the different approaches you will see in different languages, and then introduce
<Sc>Haskell</Sc>'s method. Then we will go over the functor type class, which allows
you to define the higher order function `map` for any type you want.

{{< links >}}
