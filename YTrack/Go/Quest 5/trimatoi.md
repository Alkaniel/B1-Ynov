#B1 #go #ymmersion #ytrack #required 
### Instructions

- Write a function that transforms numbers within a `string`, into an `int`.
    
- If the `-` sign is encountered before any number it should determine the sign of the returned `int`.
    
- This function should **only** return an `int`. In the case of an invalid input, the function should return `0`.
    
- **Note**: There will never be more than one sign in a `string` in the tests.
    

### Expected function

```go
func TrimAtoi(s string) int {

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
	fmt.Println(piscine.TrimAtoi("12345"))
	fmt.Println(piscine.TrimAtoi("str123ing45"))
	fmt.Println(piscine.TrimAtoi("012 345"))
	fmt.Println(piscine.TrimAtoi("Hello World!"))
	fmt.Println(piscine.TrimAtoi("sd+x1fa2W3s4"))
	fmt.Println(piscine.TrimAtoi("sd-x1fa2W3s4"))
	fmt.Println(piscine.TrimAtoi("sdx1-fa2W3s4"))
	fmt.Println(piscine.TrimAtoi("sdx1+fa2W3s4"))
}
```

And its output :

```console
$ go run .
12345
12345
12345
0
1234
-1234
1234
1234
$
```

### Solution 

```go
package piscine

/** TrimAtoi vas parcourir mon sting, on vas check si c'est négatif dans une première condition et si c'est un nombre dans dans une autre.
La seconde contion, il vas juste virer les 0 au début en faisant un x10 du nombre de base puis en rajoutant le chiffre que l'on allait traité -0 car c'est les 0 de droites (important)

Si c'est négatif, il faut juste que ça soit t'aité, donc on fait *-1 au resultat
*/

func TrimAtoi(s string) int {
	var result int
	var isNegative bool
	var isNumber bool
	for _, r := range s {
		if r == '-' && !isNumber {
			isNegative = true
		} else if r >= '0' && r <= '9' {
			isNumber = true
			result = result*10 + int(r-'0')
		}
	}
	if isNegative {
		result *= -1
	}
	return result
}
```