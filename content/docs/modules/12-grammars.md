---
title: Learning Module 12 — Grammars
linktitle: LM 12 – Grammars
date: 2021-06-25
draft: false
weight: 12
type: book
---


**Why this is important:**  If you want to write an interpreter, you need a way of
converting the user's text into a data structure that `eval` can process.
The first step is to use a grammar to specify the language, and identify properties
of the grammar that will constrain our implementation later.

## Outcomes
  - 12.1 -- Identify grammar properties such as *ambiguous*, *right-linear*, and *left-recursive*  (1 point)
  - 12.2 -- Given a grammar, show that it is ambiguous by giving an expression and two different parse trees. (3 points)
  - 12.3 -- Given a grammar, disambiguate it by stratifying it. (2 points)
  - 12.4 -- Given a grammar, determine the FIRST and FOLLOW sets of its non-terminal symbols. (4 points)
