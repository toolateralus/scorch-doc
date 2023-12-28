### Functions
- functions behave like function pointers by default: you can just pass a reference to a function by identifier.
- function parameters are default immutable.
- `const` & `var` can be used to specify mutability of function parameters & struct members.


There are basically  5 different ways to define a function.
```
f1 := {
    break
}
f2 := (s : String) {
    break
}
f3 := (s : String) -> None {
    break
}
f4 : Fn() -> Bool {
    break true
}
f5 : Fn(s : String) -> String {
    break 'hi'
}
```

### Methods
Methods are functions that belong to a specific Struct type, and can be called from the instance.

To define a method :

```coffeescript
# we associate our body with the Player type. this can contain functions & methods only.
Player :: {
    # create a function called 'move' and turn it into a method by adding the 'this' parameter as the first in the list.
    # we use a 'var this' so we can mutate the instance, leaving our intended side effects.
    move := (var this, dt : Double) {
        input := this.input.stick_left
        move_vec := Vector2{input.x, input.y}
        this.pos +=  move_vec * this.velocity * dt
    }
}
```

To call a method :
```
// we'll use our player from before (the structs tutorial.)
game.player := Player {}

// 'this' is passed as the first parameter implicitly.
game.player.move(renderer.deltaTime)
```

### Associated Functions
Associated functions are functions that are callable via a type reference and semi colons,
comparable to a static member function of a type in many languages.

to define an associated function, you can use the same syntax as methods, you just can't include `this` as a parameter.
that's what sets methods and associated functions apart.
```
// we associate this function with this type.
// this body could contain several definitions,
// but only ever functions.
Player :: {
    // we create a function called 'new' for Player
    new := {
        // we construct a player object with defaults and return it.
        return Player {}
    }
}
```

To call an associated function...
```
// just provide the qualified typename, :: and the function name.
game.player := Player::new()
```

### Extension Methods
Extension methods are functions that are defined outside of a type, but can operate on instances just like a method would.
this is useful for _extending_ a set of types or behaviors when you don't have immediate access to them.

here we're defining an extension method for the builtin type String.
it just concatenates anything provided as an argument after performing a
`tostr()` function on it, which just converts most types to a string.

when we use this syntax, we automatically get the 'this' keyword as a parameter,
so we don't need to explicitly define that.
the dynamic type / keyword just excludes type checks from an instance or field.
in this case, that allows us to take in any type.
```
String::concat := (other : dynamic) -> String {
    return this + tostr(other)
}
```
so now, on any instance of a string, we can call our `concat` method, including literals.
```
message := "hello, ".concat("world.")
println(message) // prints "hello, world."
println(message.concat(" woo")) // prints "hello, world. woo"
```
