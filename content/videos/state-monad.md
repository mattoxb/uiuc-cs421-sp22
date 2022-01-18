---
slug: state-monad
title: Video — The State Monad
date: 2021-01-01
type: book
weight: 22
links:
  - category: Slides
    links:
      - title: Slides
        display: true
        url: /slides/06.2.1-state-monad.pdf
      - title: Slides (4up)
        display: true
        url: /slides/06.2.1-state-monad-4up.pdf
---


# Transcript

Hello everyone, welcome to CS 421.

When monads were first applied to programming languages,
they were not made simply to do interesting things with
lists; the thing that got everyone excited was that they
could be used to model stateful computations in a purely
functional setting.

## Objectives

When you are done with this video, you should be able to
  - describe the `newtype` keyword and the record type we use for representing state.
  - implement the `pure` operation for the state monad.
  - implement the `bind` operation for the state monad and trace an execution.

## Defining the Types

The first thing we need to do is decide how to represent a
stateful computation. A stateful computation starts with an
input state, and returns some kind of result, possibly
modifying that state. We can represent that as a function of
type $a \rightarrow (s,a)$, where $a$ is the state type and
$s$ is the result type.

As an example, check out this `ex1` function. It takes a
state $s$ and returns a computation $s*2$ as a result, and
increments state $s$ in the process.

## Encapsulation

To represent states more explicitly so that our type checker
can keep us from mixing things up, we will use this record
syntax. Here, we are creating a type called `State`, with
two parameters. We have $s$ as the output type and $a$ as
the state type as before. The order is important! We'll
explain why in a few minutes.

The constructor is called `State` as well, and inside it we
have a record with one field: `runState`. The `newtype`
keyword in Haskell causes the types to be synonyms of each
other internally. The result is that we don't have to use
pattern matching to extract the record part of the `State`
value.

Here's an example to make this clear.

The long form way to declare a state value might be here
where I define `ex2a`.  It's just like `ex1` from the
previous slide.  Notice I have created the record
and set the `runState` field explicitly.

But you can also declare a state value like `ex2b`, just
passing the function in.  This will save us some typing.

The `runState` field name accesses the function part of the
record. It's a little bit weird to name it this way: most
people would have thought to call it `function` or
`theComputation` or something like that.  But in Haskell
label names are also functions, so it looks more natural
when we use it to extract the function out of the state.

You should probably try typing all this in to be sure you
understand how it works before going to the next slide.

# The Type Classes
## Functor

To write a monad, there must be a functor and applicative
class already defined. For functors, we want to pretend that
the state contains a value that we want to `fmap` a function
across those values, returning new states in the process.

Here is that `ex2` function with inc, and a sample run.

## Functor Definition 1

Now we can define our functor typeclass.  Remember how I
said that the `State` type parameters had to be in a
certain order?  The state type has to come first, then
the result type.

We have two things that we want to call `State` now: the
constructor or type spelled S T A T E, and the
representation of the state in type $s$. To avoid confusion,
when I refer to the variable I'll call it *state s*, using
*state* as an adjective, and when I want to refer to the
entire encapsulated function I'll just say *state*, using
it as a noun.  If I want to talk about the constructor,
I'll call it the `State` constructor.

Right.  Back to why the state type has to come first
in the type definition.

The reason is that functors need a container type. If
we have a `State s a`, then we can say that this type
is a container that has values of type `a` within it.
If we had put the result type first then the functor
typeclass would have wanted to map over state values,
not result values.

Our task now is to write `fmap`.  Here, `f` is the function
from $a\rightarrow b$ and $g$ is a `State s a`.
We want to output a `State s b`.

## Functor Definition 2

It is much easier to do this kind of thing if you think
explicitly about the types.  Notice that
`fmap` needs to return a state, so we go ahead and write
down the `State` constructor.

## Functor Definition 3

That constructor needs to have a function in it that
takes an initial state value and returns a pair, so let's
take in the initial state s1.

## Functor Definition 4

Variable g contains a state, so we runState it on our
state value s1.  This gives us a result x and a new
state value s2.
Finally, we apply f to the result x, and return the
correct tuple.

And that's it!

Again, you should try typing this in to be sure you
understand how the states and results flow in the
program.

## Applicative

Similar reasoning gives us the definition of the applicative typeclass.

We need to define pure, which takes an element and wraps it into a state.
This will seem weird because what we get is something that takes in a
state variable and *then* returns the result without even consulting it.
But, when we say that something is pure that is exactly what we mean in
this context: that is not "contaminated" by state.

For the star operation, we have two states, f1 and x1.  We know that
f1 contains a function of some kind, and that x1 contains a value to
give to that function.  But both of these are contained withing a state.

Further, we have to return our own state as a result.

You can see all of this in the type declaration.

So, following the types, we emit a State constructor and take an initial
state variable s.  To get the function out of f1 we runstate f1 with s.
This gives us f and a new state s2, which we use to runstate x1 and get
our value x and a final state s3.  We can then return f of x and s3 as
the result.

That's all there is to Applicative.  Before you continue, you should
pause the video and be sure you understand this definition.  Resume
when you are ready to see the monad!

# Monads


Now we can show you the monad.

The return definition is the same as pure from applicative; this is the
usual situation.

Now we want to discuss bind.  The first parameter is simply a state.
The second parameter is a function that takes the content of a state
and return a new state, possibly with a different type of content.
That's why the type of f is listed as $a \rightarrow State\ s\ b$.

Finally, the output should be of type State s b.

Since we are returning a state, we can write down the State constructor
and a lambda to accept the incoming state variable s.  Now what we have
to do is extract the contents of x.  Let's call it y. 

Once we have y we can feed it to f.

Think for a second though; what will be the type of (f y)?

(pause)

I hope you thought "It will be a state".  But now we have more work to do,
because we are already returning a state, and we have this result state from
(f y).  So, we take the state variable result s2 from the previous runstate
where we extracted y from x.  We then use that to runstate (f y), which yields
a new result z and new state variable s3.  We can simply return that tuple as
the result of our top-level state.

This is the end of this particular video, but we have one more where we show
how to use the state monad.  Before you watch that, it would be good for you to
work through this code to be sure you understand how it works.  It's true we
haven't shown you the examples yet, but just from knowing the types of the parts,
you can derive this particular definition.  See if you can get to the point where
you can write this definition out without consulting any resources.  It will help
you to understand what comes next.

{{< video slug="06.2.1-state-monad" transcript="n" slides="y" >}}

{{< links >}}

