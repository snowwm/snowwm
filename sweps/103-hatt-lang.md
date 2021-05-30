# hatt

name: hatt (hatt ain't turing tarpit)
project manager: hatter

!Lexical Transparency!
A practice that lets one write code which only does predictable (for humans and machines) things and can't do more. This can be checked and enforced but isn't as mandatory and knit into the language as e. g. static typing.
Useful not only for security and sandboxing. For example, babel-plugin-ttag needs to statically find ttag in the code.
https://en.wikipedia.org/wiki/Capability-based_security

Import system
explicit exports (or just naming convention?)
late binding: `from mod import obj` made suitable for circular imports and mock patching

Pluggable subsystems:
- async
- (im)mutability
- type system: substructural typing, effect system, ownership types, user-defined relations
- memory management: region-based MM, smart pointers, reference counting, uniqueness typing

The runtime differentiates between two modes of execution: checked mode aimed for development (catching type errors at runtime) and production mode recommended for speed execution (ignoring types and asserts).

Exceptions
context includes which library raised this
no need to define custom exceptions for each library, may use standard ones and filter by library

Literal transformers (`tag"a string"`)
Context managers
Fibers
ADT
Algebraic effects
Uniform Access Principle, less need for future-proofing

Vague:
- homoiconicity
- auto conversion between representations: imperative<->declarative, procedural<->functional
- auto constraint deduction:
    auto i; i = input(); vector v(i); //i will be of type size_t
- DCI (data, context, integration), role-orientedness

Composables: functions, monads, tokens, iterables, transducers, promises...
And some way to make behavior composable...
