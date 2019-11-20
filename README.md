# staging-thing
Staging thing (Nothing here right now)

Ingredients:

Staging via a haskellish quasiquotation. Maybe levitation?

- A module that types the parts of the language ('term)
- A parser/unparser/optics text \lr 'term
- Helpers to generate 'term
- Holes

As for 'term \arrow term, we need
- An evaluator for things typed by the module
- Various other stuff

Remember:

The type safe interpreter/quotation/evaluator/meta-circular problem

Coeffects or something - what is the underlying computation/runtime

Typing a possible world - modality

Quoters/unquoters

Non-actual-object oriented programming, as in manipulating things in the domain constructed in terms of the 'term module

Mirrors

Delphin etc - linear difference lists -> link to various first class polarity polymorphism stuff

Quotation, evaluation, levity (in Purple/Pink style), polarity (delphin etc), and modality (modal types for mobile code) all have a part of the notion of 'stage'.

# Typed Multi-Stage Programming

## What is the motivation

- Type safe code generation
- Stage fragment manipulation
- Teasing out what is meant by a 'stage'
  * Typically, used like macros
  * But can also talk about build pipeline, CI, the 'type' of your test suite, dependency management, deployment...
  * Yes, deployment. 'Mobile code' was an old idea (ref emerald etc) but modern interpretations use modol types to encode 'location'
  * There are also temporal modalities; we can use those to represent traditional 'macro like' multistage programming.
  * With effects and coeffects we can express the environment that code needs to be generated for/run in


## References

Emerald - early mobile code as 'active objects'
Build Systems à la Carte - that hypothetical matrix of build system possibilities paper, which introduces Shake
modal types for mobile code - thesis about what it says on the tin
two-dimensional modal logics ...
modal quantification ...
polymorphic row types ...
various oleg papers about effects and coeffects...
entropic - (federated package management) https://github.com/entropic-dev/entropic/tree/master/docs#apis
dataflow languages like oz/mozart
