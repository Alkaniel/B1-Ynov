#B1 #go #ytrack #ymmersion #required 
## Instructions

**Write a function that prints 'T' (true) on a single line if the int passed as parameter is negative, otherwise it prints 'F' (false).**

## Usage

``` go
package main

import "piscine"

func main() {
	piscine.IsNegative(1)
	piscine.IsNegative(0)
	piscine.IsNegative(-1)
}
```

``` output 
F
F
T
```

## Solution & Explications

```go
/** Here we need only a if statement, if the injected number is negative, then the statement is true. Else, it is false*/
func IsNegative(i int) {
	if i < 0 {
		z01.PrintRune('T')
		z01.PrintRune('\n')
	} else {
		z01.PrintRune('F')
		z01.PrintRune('\n')
	}
}
```

