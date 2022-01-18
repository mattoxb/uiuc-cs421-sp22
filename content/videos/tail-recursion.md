---
title: Video - Tail Recursion
date: 2021-01-01
type: book
weight: 3
slug: tail-recursion
links:
  - category: Slides
    links:
      - title: Slides
        display: true
        url: /slides/01.2.3-tail-recursion.pdf
      - title: Slides (4up)
        display: true
        url: /slides/01.2.3-tail-recursion-4up.pdf
---

There is a powerful optimization available if you structure your recursion the right way.
It's called *tail recursion*, and it enables the compiler to convert the recursion into
a loop in the compiled assembly code.

{{< video slug="01.2.3-tail-recursion" transcript="n" slides="y" >}}

{{< links >}}

