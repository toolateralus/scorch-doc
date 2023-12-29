### Structs
- structs are our data object type, they may contain fields only.
- methods can be implemented kind of like rust, in a specific block associated with the type, and probably taking `this` as a parameter.
- extension methods can be implemented by writing a free function that takes the target type as the first parameter.
- structs have a very distinct syntax as they are non-executable code in a sense: they merely outline a structure for data to be put into at a later date.

```
struct Game |
    var player : Player = None
    const objects : Array<Object> = var []
|
struct Player |
    pos : Vector2
    scale : Vector2
    rot : Double
|
struct Vector2 |
    x : Double
    y : Double
|
```

then to use these types

```
// use all the default values provided,
// since they were explicitly provided for this struct.
game := Game {}

// there's two ways we could add our player to our game..
// first, the 'ordered constructor'.
game.player := Player {
    Vector2{0, 0}
    Vector2{0, 0}
    0
}

// or alternatively:
// with named parameters.
game.player := Player {
    pos: Vector2{0, 0}
    scale: Vector2{0, 0}
    rot: 0
}

// create a chair object.
chair := Chair {scale : 1, wood_type : Wood::Oak}

// add it to the array.
game.objects.push(chair)
```