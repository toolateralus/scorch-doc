### Declarations
- we support both implicit & explicit declarations, with different syntax for each.
- variables cannot be assigned to if they have not been declared first.
- all declarations are default immutable. `const` & `var` can be used to declare a field as mutable or not explicitly.

#### explicit
```
my_variable : Int = 0
var my_bool : Bool = false
my_bool = 10
do_not_call_this_function : Fn(s : String) -> String {
    return 'woo hoo'
}
// note : the rules for a struct's fields are the same as any other field.
// global variables & state are to be avoided, but are very possible.
struct MyStruct |
    x := 0 // structs can have implicitly typed members.
    y : Int // this will default automatically. 0 for int, etc.
    z : Int = 0 // this is an explicity default value provided at construction time.
|
```
#### implicit
```
my_variable : Int = 0
my_bool : Bool = false
// implicit function, parameterless.
funcy := {
    break
}
// implicit function.
my_func := Fn(s : String)  {
    return 'hamburgers'
}
```
