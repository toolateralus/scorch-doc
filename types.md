### Types
- we want to pre-compile & do static compile time typing, but allow a `dynamic` type that performs like C#'s dynamic.

### basic types :
- these types are available anywhere with no includes.
- `double` is a 64 bit float.
- `string` is a reference type string.
- `int` is a 32 bit integer.
- `bool` is a boolean type.
- `fn` is a function pointer, or a explicitly declared function signature.
- `array` is an implicitly typed array.
- `none` is _kind of_ equivalent to null or undefined in many other languages, but also void in C style languages. it also is used in a Some/None() like option system from rust, potentially.
we aim to make something much more usable than that, with the same sentiment.

_see structs for defining user types._



### what a type contains..
---

##### metadata
name, defining namespace/module, etc etc.

--- 

##### type attributes & annotations 
while we'll use simple flags like `struct, value, array, function` etc. we also want to provide an easy to use reflection system since we're paying the price of runtime types.
this should be pretty easy to use, and pretty powerful. not as powerful as c#.

---

##### member methods & extension methods
see fns&methods tutorial

---

##### runtime fields & members.        
a context that contains all the fields this type owns that gets copied at instantiation time. 
right now, it's just a hashmap of key: type pairs that get instantiated, but this is unneccesary.