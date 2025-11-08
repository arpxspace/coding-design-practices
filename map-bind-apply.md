# Map, Bind and Apply

Problem: understand these in order to make effective use of the data structures that implement them (List, Option, Result)

>>>
given a type:

```
type Point =
  | X of int
  | Y of int
```

# Renovating the inside of a house without changing its exterior

if you do `map` you are modifying the product of the DU case:

```
let point = X 2

point
|> Point.Map (fun value -> value + 5)

// X 7

```

# Taking materials from one house to build a different kind of house

if you do `bind` you are applying a function to the whole DU case which transforms it within the constraints of what the DU allows (X or Y cases):

```
let point = X 2

point
|> Point.Bind (fun value -> Y (value + 5))

// Y 7
```
