# What is it?

**WFC** is just another useless esoteric language. It features

-   functional purity
-   literate programming
-   minimalism (there are only two operations)
-   weird IO model (different from monads and uniq types)

# Syntax

It is more simple to describe the syntax of WFC in natural language rather than
in BNF. There are three keywors: "fu", "bar" and "~"; they can be sequenced in
any order. Everything else is considered comment.

A major feature of WFC is lack of comment syntax, as compiler just ignores
everything but "fu", "~" and "bar". It makes literate programming very easy and
convenient. (Tip: one can substitute 'u' and 'a' by similar Cyrillic symbols)

# Compilation

Compilation is done in one pass. Keyword "fu" pushes the `fu` combinator to the
top of a stack. Keyword "bar" pushes the `bar` to the stack.  Keyword "~" pops
two entities, say, `a` (the topmost one) and `b` from the stack, then pushes
`(ba)` back the stack.

An attempt to pop something from an empty stack results in compilation error.

When EOF is reached, the topmost element of the stack is considered resulting
program.

# Control flow

`fu` is a control flow operator. \(fu=λ f.(f S) K\)

# IO

## Output

`bar` is an output combinator. Its first argument should be a Church numeral
representing a unicode symbol code. The second one should be a value of type
RealWorld (we it Ψ).

WFC doesn't have monads, uniq types nor any other means preventing values of
type Ψ from being referenced multiple times. But it isn't a problem, since WFC
is executed in a quantum manner.

## Input

"But there is no input&#x2026;" Wrong. WFC **has** input, but it is rather unusual.

TODO: Describe input