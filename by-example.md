# NAG By Example

Comment out a line
```nag
;; comment
```

Define a production
```nag
Name = pattern
```

Define a local-only subset of productions
```nag
Name = pattern
where
	Sub1 = pattern
	Sub2 = pattern
	..
```

Define a production via a subset of productions
```nag
Name |=
	Sub1 = pattern
	Sub2 = pattern
	..
```
> This may be interpreted as
> ```nag
> Name = Sub1 | Sub2 | ..
> where
> 	Sub1 = pattern
> 	Sub2 = pattern
> 	..
> ```

Define a functional production with parametric variables x and y
```nag
Name x y = pattern
```

Apply a functional production
```nag
Name(pattern, pattern, ..)
```

Lowercase identifiers designate raw lexemes or variables
```nag
name
```

Uppercase identifiers designate productions
```nag
Production
```

Designate an empty input
```nag
()
```

Semantic grouping operator
```nag
(pattern)
```

Designate a literal input
```nag
"text"
```

Match either the left or the right
```nag
pattern | pattern
```

Match the left and then the right
```nag
pattern pattern 
```

Match without causing its parent to fail if it fails
```nag
pattern?
```

Name the result of a pattern `x` for reference by later patterns in the sequence
```nag
x of pattern
```

Create a guard of an inner pattern, based on whether a variable `x` matches a predicate pattern
```nag
if x is pattern then pattern
```

Match anything except (), as long as it does not match a given pattern
```nag
not pattern
```

Match a zero-or-more list
```nag
pattern*
```
> `*` lists may be interpreted as
> ```nag
> * element = x of element? if x is not () then element*
> ```

Match a one-or-more list
```nag
pattern+
```
> `+` lists may be interpreted as
> ```nag
> + element = element element*
> ```

Match a zero-or-more list of the lhs separated by the rhs
```nag
pattern**pattern
```
> `**` lists may be interpreted as
> ```nag
> ** element separator = element (separator element)* | ()
> ```

Match a one-or-more list of the lhs separated by the rhs
```nag
pattern++pattern
```
> `++` lists may be interpreted as
> ```nag
> ++ element separator = element (separator element)*
> ```
