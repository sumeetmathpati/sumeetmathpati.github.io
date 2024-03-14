+++
title = 'Golang Notes'
date = 2024-01-27T19:33:12Z
author = "Sumeet"
+++

This is collection of notes I've taken while learning Golang.

## Loops

Go only has keyword for looping, and that's `for`.

```go {}
for <initial statement>; <condition>; <post statement> {
  <statements>
}
```

- `initial statement`, executed once, optional.
- `condition`, executed before each loop, optional.
- `post statement`, executed after each loop, optional.

Another form of loop is with `range`. Syntax for that is,


```go
// Loop with range
for <key>, <value> := range <map> {
  <statements>
}
```

We can use arrays, and slices here as well. Due to `range` keyword, the for loop iterates through all the elements in array, slice or map.

```go
// Loop with range example
myMap := map[string]string{
    "name": "Sumeet",
    "age":  "100",
}

for key, value := range myMap {
    fmt.Printf("%s: %s\n", key, value)
}
```

## Primary Types

### Bool

A `bool` type can only have value `true` or `false`.

### Numbers

In Go, we can have two types of numbers integers (whole numbers), and floating points.

The zero-value, or default value for number types is `0`.

|Type|Description|
|-|-|
|uint8| Unsigned integer, 8-bits, 0-255|
|uint16| Unsigned integer, 16-bits, 0-65535|
|uint32| Unsigned integer, 32-bits, 0-4294967295|
|uint64| Unsigned integer, 64-bits, 0-18446744073709551615|
|int8| Signed integer, 64-bits, -128-127|
|int16| Signed integer, 16-bits, -32768 to 32767|
|int32| Signed integer, 32-bits, -2147483648 to 2147483647 |
|int64| Signed integer, -9223372036854775808 to 9223372036854775807|
|uint| Signed integer, 32 or 64 bits|
|int| Signed integer, 32 or 64 bits|
|byte|Alias for uint8|
|rune|Alias for int32|

We cnnot assign value larger thatn the capacity

```go
var myint int8 = 128 // cannot use 128 (untyped int constant) as int8 value in variable declaration (overflows)
var myint int8 = 128 // cannot use 128 (untyped int constant) as int8 value in variable declaration (overflows)
```

If we add a number fo the variable which is already at its highest value, it will wraparound.

```go
func main() {

	var myint uint8 = 255
	fmt.Println(myint + 1) // 0

}
```

### String


Go has `string` type fo represent string.

There are two types of string literals
- Raw strings, enclosed in  `` `  `` (backtick)
    - Variable will have whatever we see on screen. I.e., if we write `\n` in raw string, it will be printed as it is.
- Interpreted, enclosed in `"` (double quotes). 
    - Go might transform the string, i.e. if we write `\n` in interpreted string, it will be printed as newline, and not `\n`.

### Rune

Rune is an alias for `int32`. A `string` type of a collection of runes, where rune represent a character in a string.

### `nil` Value

`nil` is a special value in Go.

## Composite Types

Composite types are composed of Go's fundamental types.

### Array

Array is a fixed sized list of a fixed type. 

Syntax is `[<size>]<type>`, for example `[3]int` represents array of size 3 of type int.