---
title: Higher Order Functions
date: 2021-05-24
type: book
weight: 4
hidden:
links:
  - category: Videos
    links:
      - title: Introduction
        display: true
        url: /videos/introduction-to-higher-order-functions
      - title: Map and Foldr
        display: true
        url: /videos/map-and-foldr
  - category: Activities
    links:
      - title: TPS version
        display: true
        url: /handouts/hofs-tps.pdf
      - title: POGIL version
        display: true
        url: /handouts/hofs-pogil.pdf
      - title: Activity Walkthrough Video
        url: https://mediaspace.illinois.edu/media/t/0_e0u0p8fm
---

## Synopsis

A higher order function allows you to pass a function as an
argument to another function.  Sure, you could do this with
function pointers in C, but HOFs also allow you to have functions
create new functions and return them, store them in variables, and
call them at will.

Before watching the videos, consider the three functions below.
The first two have a lot of code duplication.  Most languages give
you no mechanism to avoid this.  Then consider the third function.
How could you call this function to provide the functionality of the
first two functions?

```haskell
incList [] = []
incList (x:xs) = x + 1 : incList xs

decList [] = []
decList (x:xs) = x - 1 : decList xs

map f [] = []
map f (x:xs) = f x : map f xs
```

{{< links >}}
