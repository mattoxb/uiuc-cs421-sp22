---
title: Learning Module 11 — Type Classes and Monads
linktitle: LM 11 – Type Classes and Monads
date: 2021-06-25
draft: false
weight: 11
type: book
---

**Why this is important:**  Type classes are Haskell's solution to the
"expression problem": in an existing system, how do we add new functions (verbs)
or new types (nouns)?  In most languages it is dramatically easier to do one
than the other.  Type classes are an attempt to make both of these things
easier.

The type classes we will focus on are the Functor (allowing for `map` to be
written for any type), Applicative (like `map` for multiple-argument functions),
and Monad (allowing us to be able to model state and other forms of computation
in a safe way).  They've been described as "programmable semicolons."

## Outcomes
  - 11.1 -- Implement the `Eq` or `Ord` type class for a given type. (2 points)
  - 11.2 -- Implement a `Functor` type class for a given type. (2 points)
  - 11.3 -- Implement an `Applicative` type class for a given type. (2 points)
  - 11.4 -- Implement a `Monad` type class for a given type. (4 points)

