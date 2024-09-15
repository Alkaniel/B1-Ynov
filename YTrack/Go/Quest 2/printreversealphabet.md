#B1 #go #ymmersion #ytrack #required 
## Instructions

*Write a program that prints the Latin alphabet in lowercase in reverse order (from `'z'` to `'a'`) on a single line.

*A line is a sequence of characters preceding the [end of line](https://en.wikipedia.org/wiki/Newline) character (`'\n'`).

*Please note that `casting` is not allowed for this exercise!

``` Go
package main

import "github.com/01-edu/z01"

/** Here it was easy, I put the ASCII's value of 'z'*/
func main() {
    var startingASCIINumber int = 122

    for i := 0; i < 26; i++ {
        z01.PrintRune(rune(startingASCIINumber - i))
    }
    z01.PrintRune('\n')
}
```

