## Abstract

Lisp is one of the easiest languages to bootstrap, to write an interpreter or compiler for, and to do meaningful metaprogramming in. I claim that this is because of how neatly Lisp code maps onto the cons list datastructure, which has a simple set of manipulation functions, and how dynamically typed... can ignore the well-typing problem in code construction...; Lisp has an incredibly simple AST. AST manipulation thus provides an entry level of staging 'for free'. For other languages, the AST typing problem quickly becomes an instance of The Expression Problem, with a 'tying the knot' fixpoint complication. Here I will introduce a new type system and datastructure - a modest extension to GADTs - which is adequate for the general ast typing problem, and show how this makes it easier to bootstrap, build an interpreter and compiler, and metaprogram in languages with more complex syntax while maintaining type safety.

Typed staging...


## Related work
This is related to the finally-tagless approach to staging...

The typed self-interpreter problem...

The Expression Problem...

Type safe code generation...
1. You can't generate non-syntax-correct code, because types - that is, all manipulations of quoted code remain well-formed
  - The extension to 'fragments' which are not well formed, but which we can typecheck how they are used to show that they only end up being used in ways that generate well formed code
  - 'Holes' as an example which we can see as syntax sugar for a restricted case of this
2. The type of the staged, generated code references the type of the generated code
  - 2 is made easier by having a context variable that takes part in typechecking bidirectionally, so that we can see the constraints generated code will have, even though we cannot necessarily fully type it without the context it is going to be reified in.

## The Data Type

A multi sorted algebra, with labelled sums, products, and exponents. first class labels, first class cases, and first class patterns. Introduction vs elimination forms, change of direction, bidirectionality. Modal types for mobile code. Intensional recursion through PCF.

## The rest

Explicit name introduction via quantifiers. Staging via typed quasiquotation with typed holes. Lifting. Bidirectionality elaborated.

---

Ambients - coeffects + modal locations ⇒ target types
Staging across this gives you cross compilation
This is needed to get even fairly simple things like the web dev thing of server side rendering, client side rendering, rehydration, different capabilities, with conneg and mimetypes 'for free'.
Bidir for synthesis.
+ve/-ve types for value/code distinction (value level destructuring/pattern matching etc, but also the Intensional PCF thing with the Godel-Lob thing and modal recursion)


---

References:

"Intensionality, Intensional Recursion, and the Gödel-Löb axiom", G. A. Kavvos
