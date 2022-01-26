---
title: Getting Haskell
linktitle: Getting Haskell
date: 2021-06-25
draft: false
weight: 5
type: book
---

## Getting Haskell

In order to use Haskell on your own machine, you need to install a program called
`stack`.  This is the package manager and build system for Haskell, similar to
`npm` for Node and `maven` for Java.

You can install `stack` from [the official website](https://github.com/commercialhaskell/stack/blob/master/doc/install_and_upgrade.md)
but there is an installer called `GHCup` that will automate a lot of this for you.

You can get `GHCup` [here](https://www.haskell.org/ghcup/).  You should install
`stack`, `ghc`, `cabal`, and `HLS` (this will connect to your editor and make
things easier.

If you are on Linux, you might also be able to do this with your package manager.

## Mac M1

There have been problems recently installing it on the newer Mac M1s.  One of the students
(Yuhan Lu) found a workaround and got it working.

#+begin_quote
Install the ~x86_64~ based Homebrew instead of ~ARM~, and use ~x86_64 brew~ to install ~stack~. You could follow the steps here
https://medium.com/mkdir-awesome/how-to-install-x86-64-homebrew-packages-on-apple-m1-macbook-54ba295230f
#+end_quote

## Configuring Your Editor

Your editor is the most important tool you will use on a computer.  Mastering a good editor
can make a world of difference in your productivity as a programmer.

If you like vscode, this blog post is helpful.
 - https://medium.com/@iandrc/haskell-vs-code-setup-in-2021-6267cc991551
 

