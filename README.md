# NAG Notation

This is a quick explainer for NAG (Nox's Abstract Grammar) notation,
a grammar specification syntax I created with the idea it would be a cosey syntax wrapper for EBNF,
which is itself essentially just sugary BNF. Unlike BNFs however, due to my uncontrollable
pursuit of logical extremes NAG is turing complete. This is due to the introduction
of functional abstractions and conditional guards, which simply make it easier
to express certain aspects of grammar such as interdepedence among subsequences.

In this repository I present [NAG By Example](./by-example.md), as well as a formal specification of [NAG defined in NAG](./nag.nag)
