---
layout: index
title: Math concepts and notation
permalink: /chapter2/
sidebar_link: true
sidebar_sort_order: 2
---

<div id="toc-wrapper" markdown="1">
* Table of contents
{:toc}
</div>

Like sculpting, theoretical modeling requires its own set of dedicated tools. The theoretical modeler's tools are mathematical concepts, formal expressions, and notational conventions. One can already get quite far with the basics in _set theory_, _functions_ and _logic_. Below we present a brief primer. Readers who have taken introductory classes on these topics can skip this section without loss of continuity.

# Set theory
A set is a collection of distinct objects. For example, a set of people $$P=\{\text{Ramiro},\text{Brenda},\text{Molly}\}$$, animals $$A=\{\text{cat},\text{turtle},\text{blue whale}, \text{cuttlefish}\}$$ or numbers N=\{1,5,7,12\}. Sets are usually denoted by a capital letter and their elements listed between curly brackets. They can also be visualized as circles.

![Basis sets](../assets/img/set-eg.svg "Sets can be visualized as circles.")

Sets can contain an infinite number of objects, e.g. all positive odd numbers $$O=\{1,3,5, 7,\dots\}$$.

## Set membership
When we want to write that an object $$x$$ is (or is not) part of a set $$X$$, we use _set membership_ notation:

$$5 \in N\\17 \notin N\\\text{Ramiro}\in P\\\text{Saki}\notin P$$

![Set membership](../assets/img/set-in.svg "Set membership.")

## Subset and superset
Often, we want to express things like 'the set of mammals $$M$$ is part of the set of all animals $$A$$'. We then use _subset_ notation: $$M\subseteq A$$ or $$M\subset A$$. The latter means that $$M$$ is smaller than $$A$$.

![Subset](../assets/img/set-sub.svg "Subset relationship.")

Vice versa, we can express that 'the set of all things on earth $$T$$ contains all animals $$A$$' using _superset_ notation: $$T\supseteq A$$ or $$T\supset A$$. The latter means that $$T$$ is bigger than $$A$$.

![Superset](../assets/img/set-sup.svg "Superset relationship.")

## Intersection, union and difference
Let's look at what more we can do with two sets. For example, take the set of your friends and my friends.

$$F_{you}=\{\text{John},\text{Roberto},\text{Holly},\text{Doris},\text{Charlene}\}$$

$$F_{me}=\{\text{Vicky},\text{Charlene},\text{Ramiro},\text{Johnnie},\text{Roberto}\}$$

![Set example](../assets/img/set-two.svg "Example sets.")

Who are our common friends? We use _set intersection_:

$$F_{you}\cap F_{me} = \{\text{Roberto},\text{Charlene}\}$$

![Set intersection](../assets/img/set-disjunction.svg "Set intersection.")

Who do we know together? We use _set union_:

$$F_{you}\cup F_{me} = \{\text{John},\text{Roberto},\text{Holly},\text{Doris},\text{Charlene},$$ $$\text{Vicky},$$ $$\text{Ramiro},$$ $$\text{Johnnie}\}$$

![Set union](../assets/img/set-union.svg "Set union.")

Who do I know that you do not know? We use _set difference_:

$$F_{me}\setminus F_{you}=\{\text{Vicky},\text{Ramiro},\text{Johnnie}\}$$

![Set difference](../assets/img/set-minus.svg "Set difference.")

## Set builder
A more advanced way to denote sets, is to define a set using _set builder_ notation. This allows us to define (build) a new set given other set(s). A set builder consists of two parts, a variable and a logical predicate:

$$\{\text{variable}~|~\text{predicate}\}$$

Let's look at an example and build a set of all mammals from $A$. We explain logical predicates below, for now lets use verbal language:

$$M=\{a~|~a\in A\text{ and }a\text{ is a mammal}\}$$

You can read this as '$$M$$ contains all $$a$$'s _with the property that_ $$a\in A$$ and $$a$$ is a mammal'.

![Set builder](../assets/img/set-builder.svg "Set builder.")

## Cardinal product
Set builder notation is useful to filter objects from a single set, but becomes very potent when building from multiple sets. For example:

$$F=\{(p,a)~|~p\in P\text{ AND }a\in A\}$$

![Cardinal product](../assets/img/set-cardinal.svg "Cardinal product.")

Read this as '$$F$$ contains all pairs of $$p$$ and $$a$$ _with the property that_ $$p$$ is a person and $$a$$ is an animal'. Pairs are denoted in brackets. You can think of $$F$$ containing all possible combinations of person-animal pairs. For example, these are all the options you have when trying to guess what the favorite animals are of your friends.

Many other set builders are possible too, but this specific 'pair builder' is called the _cardinal product_ of two sets. It is used often enough that it has its own special symbol: $$F=P\times A$$.

## Special sets
Finally, there are some special sets which we often use that have their own symbols:


* Empty set $$\varnothing=\{\}$$
* Natural (whole) numbers (with zero) $$\mathbb{N}_0=\{0,1,2,3,4,\dots\}$$
* Natural (whole) numbers (without zero) $$\mathbb{N}^*=\{1,2,3,4,\dots\}$$
* Integer numbers $$\mathbb{Z}=\{\dots,-3,-2,-1,0,1,2,3,\dots\}$$
* Real numbers <span>$$\mathbb{R}=\{r~|~-\infty<r<\infty\}$$</span>

# Functions
Building on set theory, we can define functions. Functions are relations that map all objects from one set (the _domain_) to exactly one object from another set (the _codomain_). We define functions with the following notation, here $$f$$ is the name of the function:


$$f:D \rightarrow C\text{ with }f(d)=c$$

Let's make this more concrete:

$$like: P \rightarrow \mathbb{Z}$$

You can read this as '$$like$$ is a function that maps persons $$p\in P$$ to an integer'.

![Function](../assets/img/fun-basic.svg "Function.")

We sometimes omit the exact specification of the function when it is clear what it would be. For example, here it could be a list of numbers representing how much you (dis)like the person, based on your social interactions with that person.

## Advanced functions
We can also give functions more complex domains by using set theory. What would a function that captures how much two persons like each other look like?

$$like_2:P\times P\rightarrow \mathbb{Z}$$

The cardinal product $$P\times P$$ denotes all pairs of persons and $$like_2$$ maps pairs to an integer.

![Advanced function](../assets/img/fun-adv.svg "Advanced function.")


## Sum and product
We can now define _summation_ and _product_. These functions iterate over members in a set and return a summary value.

Summation $$\sum$$ takes all $$x$$'s from $$X$$, applies $$f(x)$$ to each and adds all values:

$$\sum_{x\in X}f(x)=f(x_1)+f(x_2)+f(x_3)+\dots$$

Product takes $\prod$ all $x$'s from $$X$$, applies $$f(x)$$ to each and multiplies all values:

$$\prod_{x\in X}f(x)=f(x_1)f(x_2)f(x_3)\dots$$
