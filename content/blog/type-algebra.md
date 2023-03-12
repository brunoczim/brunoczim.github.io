+++
title = "Type Algebra Explained"
template = "index.html"
+++

# Type Algebra

## Introduction

Data types in programming come in all flavours, and to many programmers, the
theories behind them pass unnoticed. In this post I will explain one of these
theories: algebraic data types. Have you ever used a struct/record in your
favourite programming language? That is an algebraic data types. Have your ever
hard about "sum types"? That is also an algebraic data type!

Algebraic data types (ADT) are a way of modelling the combination of data types
using algebra as an analogy. As an example, a struct/record is also called
_product type_ because a record `C` that combines type `A` and type `B` has a
total number of elements equals to total elements of `A` multiplied by total
elements of `B`, i.e. `|C| = |A| * |B|`. This is a very similar concept to an
ordered pair in set theory.
