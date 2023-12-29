### Arrays
- arrays have several layers of immutability.
- the array itself can be marked immutable, meaning it cannot be re-assigned to a new array value, meaning
`array = [0,1,2,3]` will fail.
- the array can also flag it's elements as immutable (as a whole, not individually.) this means that
`array[0] = 10` will fail, even if the array itself is `var` aka mutable.

- the way to specify this while declaring is as such:
```
// an immutable reference to an immutable array
array := [0, 1, 2]
// an immutable reference to a mutable array.
array := var [0, 1, 2]
// a mutable reference to an immutable array.
var array := []
// a mutable reference to a mutable array.
var array := var []


// for explicit decl..
var array : Array = []

```
