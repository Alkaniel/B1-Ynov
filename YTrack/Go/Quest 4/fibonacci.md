### Instructions

Write a **recursive** function that returns the value at the position `index` in the fibonacci sequence.

The first value is at index `0`.

The sequence starts this way: 0, 1, 1, 2, 3 etc...

A negative index will return `-1`.

`for` is **forbidden** for this exercise.

### Expected function

```go
package piscine

func Fibonacci(index int) int {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	arg1 := 4
	fmt.Println(piscine.Fibonacci(arg1))
}
```

And its output :

```console
$ go run .
3
$
```

### Solution

```go
func Fibonacci(index int) int {
	if index < 0 {
		return -1
	}
	if index == 0 {
		return 0
	}
	if index == 1 {
		return 1
	}
	return Fibonacci(index-1) + Fibonacci(index-2)
}

// Le principe de fibonnacci c'est d'ajouter les 2 chiffres d'avanct encore et encore, jusqu'à 0

```
