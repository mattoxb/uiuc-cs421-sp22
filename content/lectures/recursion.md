---
title: Recursion
slug: recursion
date: 2021-05-19
draft: false
type: book
weight: 2
links:
  - category: Videos
    links:
      - title: Basic Recursion
        display: true
        url: /videos/basic-recursion
      - title: Induction
        display: true
        url: /videos/induction
      - title: Tail Recursion
        display: true
        url: /videos/tail-recursion
  - nocategory: Activities
    links:
      - title: Recursion Activity Handout
        url: /handouts/recursion-pogil.pdf
      - title: Activity Walkthrough (Spring 2021)
        url: https://mediaspace.illinois.edu/media/1_vr93ex47
  - category: Further Reading
    links:
      - title: There and Back Again
        url: http://www.brics.dk/RS/01/39/BRICS-RS-01-39.pdf
        desc: This is a research paper about a hybrid of forward recursion and tail recursion.
        display: true
---

## Synopsis

We will talk about recursion, the second most powerful idea of
computer science.  We assume you have seen recursion before, as well as
proofs by induction.  This ties the two concepts together and shows you
how to write recursive functions in <Sc>Haskell</Sc>, as well as how to make a function
tail recursive (and why you might want to).

Before watching the videos, think about these
questions for five minutes or so.

 - Did you know that if you take the first \\(n\\) odd numbers and
   sum them, that the result is \\(n^2\\)? i.e., $$\Sigma_{i=1}^n
   2i-1 = n^2$$  Try to prove this by induction; remember you need
   a base case (when \\(n=1\\)) and an induction case (when \\(n > 
   1\\) ).
 - In your favorite language, try to write a recursive function that
   computes \\(n^2\\) in the same way, by summing the first \\(n\\) odd numbers.
 - Imagine that you had a recursive function that never made use
   of the result of its recursive call.  Would such a function even
   be useful? (Hint: the answer is "yes".) What kinds of things could
   you do if you could guarantee to the compiler that this would be
   the case?

{{< links >}}
