---
title: LR Parsing
date: 2021-06-21
type: book
weight: 17
hidden: []
links:
  - category: Videos
    links:
      - title: LR Parsing
        display: true
        url: /videos/lr-parsing
      - title: Activity Walkthrough (Spring 2021)
        url: https://mediaspace.illinois.edu/media/1_s6cnmnlz
  - category: Activities
    links:
      - title: LR Parsing Activity (POGIL version)
        display: true
        url: /handouts/lr-parsing-pogil.pdf
      - title: LR Parsing Activity (TPS version)
        display: true
        url: /handouts/lr-parsing-tps.pdf
  - category: Further Reading
    links:
      - title: LR Parsing Tables
        display: true
        url: /handouts/lr-parsing-tables.pdf
---

## Synopsis

LR parsers have been the industry standard for quite some time.  The gnu C compiler
even comes with an LR parser generator (called `bison`, a take-off of an older utility
called `yacc`.  Computer people like puns.).  These parsers are fast and capable, but
to be effective using them you really need to understand how they work.

{{< links >}}
