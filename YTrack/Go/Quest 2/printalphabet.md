#B1 #go #ymmersion #ytrack #required 

## Instruction 

*Write a program that prints the Latin alphabet in lowercase on a single line.*

*A line is a sequence of characters preceding the [end of line](https://en.wikipedia.org/wiki/Newline) character (`'\n'`).*

## Usage 

```bash
$ go run .
abcdefghijklmnopqrstuvwxyz
$
```

## Solution & Explications

```Go
package main

import "github.com/01-edu/z01"

/* Rune could be compare as Java's char, it show 'char' as the typed value, but numbers are turned into chars according to their ASCII number.
So to print all the alphabet in a factorized way, we have to define a starting value starting by ASCII's value of 'a'.
Then create a for loop which has for end condition the number of the letter of the alphabet, in which we print the starting ASCII number additionned with the int.

Don't forget to go to the line afterthat.
rune() turns anything into rune. It is has Java parse...(value)
*/

func main() {
    var startingASCIINumber int = 97 //
    for i := 0; i < 26; i++ {
        z01.PrintRune(rune(startingASCIINumber + i))
    }
    z01.PrintRune('\n')
}
```
