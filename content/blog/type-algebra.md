+++
title = "Type Algebra Explained"
template = "index.html"
+++

# Type Algebra

## What Are Algebraic Data Types?

Data types in programming come in all flavours, and to many programmers, the
theories behind them pass unnoticed. In this post I will explain one of these
theories: algebraic data types. Have you ever used a struct/record in your
favourite programming language? That is an algebraic data types. Have your ever
hard about "sum types"? That is also an algebraic data type!

Algebraic data types (ADT) are a way of modelling the combination of data types
using algebra as an analogy. More specifically, the analogy is about the
cardinality of types, i.e. total number of elements belonging to the type.
As an example, a struct/record is also called _product type_ because a record
`C` that combines type `A` and type `B` has cardinality equals `A`'s  multiplied
by `B`'s cardinality, i.e. `|C| = |A| * |B|`. This is a very similar concept to
an ordered pair in set theory.

Another example of algebraic data type is a sum type. As the name indicates, a
sum type C combining types A and B has a total number of elements equals to the
sum of total elements of `A` and total elements of `B`, i.e. `|C| = |A| + |B|`.
This corresponds to disjoint unions in set theory, but not to regular unions.
In fact, in contrary to set theory's unions, summing a type with itself produces
a new type, as we'll see in a section below.

There are other types, such as exponential types (whose cardinality you all
might have guessed), unitary types and nullary types. As the names suggest,
unitary types have one element, nullary types have no elements. In the following
sections all of this will be explored in more details.

## Table of ADTs

<table>
    <tr>
        <th>Names</th>
        <th>Notations</th>
        <th>Cardinality Formula</th>
    </tr>
    <tr>
        <td>void type, bottom type, never type, nothing type</td>
        <td><code>0</code>, <code>⊥</code></td>
        <td><code>|0| = 0</code></td>
    </tr>
    <tr>
        <td>unitary type, unit type, top type, void type (C-like)</td>
        <td><code>1</code>, <code>⊤</code>, <code>()</code></td>
        <td><code>|1| = 1</code></td>
    </tr>
    <tr>
        <td>sum type, variant type, tagged union, discriminated union</td>
        <td><code>A + B</code></td>
        <td><code>|A + B| = |A| + |B|</code></td>
    </tr>
    <tr>
        <td>product type, struct, record</td>
        <td><code>A * B</code>, <code>(A, B)</code></td>
        <td><code>|A * B| = |A| * |B|</code></td>
    </tr>
    <tr>
        <td>exponential type, function type</td>
        <td><code>B ^ A</code>, <code>A -> B</code></td>
        <td><code>|B ^ A| = |B| ^ |A|</code></td>
    </tr>
    <tr>
        <td>dependent sum type, dependent record</td>
        <td><code>Σ(x : A). B(x)</code>,<br><code>(x : A, B(x))</code></td>
        <td><code>|Σ(x : A). B(x)| = Σ(x : A). |B(x)|</code></td>
    </tr>
    <tr>
        <td>dependent product type, dependent function</td>
        <td class="no-break"><code>Π(x : A). B(x)</code>,<br><code>(x : A) -> B(x)</code></td>
        <td class="no-break"><code>|Π(x : A). B(x)| = Π(x : A). |B(x)|</code></td>
    </tr>
</table>
