#B1  #go #ytrack #ymmersion #optional 
### Instructions

- Write a function that prints all possible combinations of **n** different digits in ascending order.
    
- n will be defined as : 0 < n < 10
    

Below are the references for the **printing format** expected.

- (for n = 1) '0, 1, 2, 3, ..., 8, 9'
    
- (for n = 3) '012, 013, 014, 015, 016, 017, 018, 019, 023,...689, 789'
    

### Expected function

```go
func PrintCombN(n int) {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	piscine.PrintCombN(1)
	piscine.PrintCombN(3)
	piscine.PrintCombN(9)
}
```

And its output :

```console
$ go run .
0, 1, 2, 3, 4, 5, 6, 7, 8, 9
012, 013, 014, 015, 016, 017, 018, ... 679, 689, 789
012345678, 012345679, ..., 123456789
$
```

### Solution 

```Go 
package piscine

import "github.com/01-edu/z01"

/**On vas utiliser d'abord PrintCombN, on commence d'abord avec une sécurité car on souhaite avoir entre 1 et 9 chiffres maxi donc la première boucle sert à ejecter tout ce qui n'est pas au entre 1 et 9 inclus.
Ensuite on vas appeler la fonction helper avec une slice vide, N en constructeur et la rune de start qui est '0'
Current represente la combinaise actuellement print, n la longeur maxi de nombre dans la combinaison et start qui est le chiffre de départ. Si la combinaison n'est pas la dernière possible (check en comparant la première rune de current à la rune '9'-n+1, cela imprime une virgule et un espace puis ça retourne la fonction. 
Si la longeur de current est plus petite 
)
*/

func PrintCombN(n int) {
	if n <= 0 || n >= 10 {
		return
	}
	helper([]rune{}, n, '0')
	z01.PrintRune('\n')
}

func helper(current []rune, n int, start rune) {
	if len(current) == n {
		for i, r := range current {
			z01.PrintRune(r)
			if i == n-1 {
				continue
			}
		}
		if current[0] != rune('9'-n+1) {
			z01.PrintRune(',')
			z01.PrintRune(' ')
		}
		return
	}

	for r := start; r <= '9'; r++ {
		helper(append(current, r), n, r+1)
	}
}

```