#B1 #go #ytrack #ymmersion #optional 

### Instructions

- Write a function that simulates the behaviour of the `Atoi` function in Go. `Atoi` transforms a number represented as a `string` in a number represented as an `int`.
    
- `Atoi` returns `0` if the `string` is not considered as a valid number. For this exercise **non-valid `string` chains will be tested**. Some will contain non-digits characters.
    
- For this exercise the handling of the signs `+` or `-` **does have** to be taken into account.
    
- This function will **only** have to return the `int`. For this exercise the `error` result of `Atoi` is not required.
    

### Expected function

```go
func Atoi(s string) int {

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
	fmt.Println(piscine.Atoi("12345"))
	fmt.Println(piscine.Atoi("0000000012345"))
	fmt.Println(piscine.Atoi("012 345"))
	fmt.Println(piscine.Atoi("Hello World!"))
	fmt.Println(piscine.Atoi("+1234"))
	fmt.Println(piscine.Atoi("-1234"))
	fmt.Println(piscine.Atoi("++1234"))
	fmt.Println(piscine.Atoi("--1234"))
}
```

And its output :

```console
$ go run .
12345
12345
0
0
1234
-1234
0
0
$
```

### Solutions

```go
package piscine

func Atoi(s string) int {
	lenS := len(s)
	nbr := 0

	for i := 0; i < lenS; i++ {
		if lenS == 1 { //gestion des truc solo
			return ElBasicAtoi2(s)
		} else if (s[0] == '-' && s[1] == '-') || (s[0] == '+' && s[1] == '+') { // ++, --
			return 0
		} else if s[0] == '+' { // gestion des +
			return ElBasicAtoi2(s[1:]) //[1:] retire 1 au début
		} else if s[0] == '-' { //gestion des -
			nbr = ElBasicAtoi2(s[1:])
			return -nbr //retourne la valeur au negatif
		} else {
			return ElBasicAtoi2(s)
		}
	}
	return nbr
}

func ElBasicAtoi2(s string) int {
	var nbr int
	for _, char := range s {
		if !(char >= '0' && char <= '9') {
			return 0
		}
		nbr = nbr*10 + int(char-'0')
	}
	return nbr
}
```