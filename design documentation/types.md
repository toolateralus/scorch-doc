### Types
- we want to pre-compile & do static compile time typing, but allow a `dynamic` type that performs like C#'s dynamic.

### basic types :
- these types are available anywhere with no includes.
- `Double` is a 64 bit float.
- `String` is a reference type string.
- `Int` is a 32 bit integer.
- `Bool` is a boolean type.
- `Fn` is a function pointer, or a explicitly declared function signature.
- `Array` is an implicitly typed array.
- `None` is _kind of_ equivalent to null or undefined in many other languages, but also void in C style languages. it also is used in a Some/None() like option system from rust, potentially.
we aim to make something much more usable than that, with the same sentiment.

_see structs for defining user types._