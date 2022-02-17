---
title: Continuation Passing Style
date: 2021-06-04
type: book
weight: 10
hidden: []
links:
  - category: Videos
    links:
      - title: CPS
        display: true
        url: /videos/cps
      - title: CPS Transform
        display: true
        url: /videos/cps-transform
      - title: Activity Walkthrough (Fall 2021)
        display: true
        url: https://mediaspace.illinois.edu/media/t/1_iq269ey3
      - title: Activity Walkthrough (Fall 2020)
        url: https://mediaspace.illinois.edu/media/1_mi4vbmzk
      - title: Activity Walkthrough (Spring 2021)
        url: https://mediaspace.illinois.edu/media/1_e015vcq7
  - category: Handouts
    links:
      - title: CPS Activity (TPS version)
        display: true
        url: /handouts/cps-tps.pdf
      - title: CPS Activity (POGIL version)
        display: true
        url: /handouts/cps-pogil.pdf
---

## Synopsis

You have seen, especially in the [Higher Order Functions](/lecture_higher-order-functions)
lecture, how we can use functions to generalize an operation. Continuations are
another example of this. Many languages have a `return` keyword to tell the
program to return from a function call with a certain result. What if you could
replace that with a parameter of your own choosing? The result is called a
*continuation*, and they have enormous power over the execution flow of a
program.

These may well seem abstract to you, but you will recognize them if you ever program in
languages like <Sc>Javascript</Sc>, where they are usually called "callbacks".

{{< links >}}
