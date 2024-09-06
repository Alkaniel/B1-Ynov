#ynov #fonction #algorithmie #ymmersion #B1 

## Qu'est-ce une fonction 
*Un bloc de code réutilisable*

* Paramètre *(int, str, double, float ...)*
* Renvoyer une/des données *(tous types)*

**Exemple : Multiplier un nb par 2**

``` Go
func Mult2 (nb int) int {
return nb * 2  
// Ca c'est une fonction car il y a un return sinon c'est une procédure
}

nb = 5
nb = Mult2(nb)
Print(nb) // -> 10
nb = Mult2(nb)
Print(nb) // -> 20
```

## Qu'est-ce que l'algorithmie
*Une suite d'information*

C'est à faire avant le code.

**Exemple :

 * Condition  ( Si ... Alors ... Sinon ... )
 * Boucles ( Tant que ... Alors ... )

```
Fonction Mult2(nb : Entier) : Entier
	Retourner le nb * 2
Fin Fonction

Début du programme
	nb <- 5
	nb <- Mult2(nb)
	Afficher nb
	nb <- Mult2(nb)
	Afficher nb
Fin du programme
```
## Les conditions
*Qu'est-ce que c'est*

* Des comparaison de valeurs
	* Si...
		* 5 < 125
		* "Bonjour" == "Bonjour"
		* 36 > 12
	* Alors...

* Comparateur 
	* Opérateur de comparaison
		* <    (est inférieur à)
		* <=  (est inférieur ou égal)
		* ==  (est égal à) 
		* !=    (est différent de)
		* >=  (est supérieur ou égal)
		* >     (est supérieur à )
	* Opérateur Logique
		* ||     (Ou)
		* && (Et) 
		* !      (N'est pas)

``` Go
bb := 56

if nb < 100 {
	Print("nb is less than 100")
} else if number > 100 {
	Print("nb is greater than 100")
} else {
	Print("nb is equal to 100")
}
```

``` Go
nb := 56
if nb < 100 || nb > 100 {
	Print("nb is less or greater than 100")
} else {
	Print ("nb is equal to 100")
}
```

## Boucles
*Qu'est-ce que c'est*

Execution répété d'un bout de code tant qu'une condition est respecter

* Tant que ...
	* Conditionelle (Conditions seules)
	* Itérative (Mis en place d'un itérateur)
	* Parcours
	* Recursive


* Conditionelle -> Conditions seule
	* Pour *Condition* 
	* nb < 9
	* Phrase != "Salut"

``` Go
nb := 36
for nb < 100 {
	nb = Multi2(nb)
}

Print(nb) // -> 140
```

* Iterative
	* 3 mots (Déclaration, Condition, Execution)
		* i := 0
		* i < 9
		* i ++

``` go
nb := 0

for i:= 0; i < 10; i++ {
	nb += 1
}
Print(nb) // -> 45
```

* Parcours (Traverse un obj)
	* On a des Arrays (listes), des Slices, et des Strings

``` Go
hello := "Hello everyone ! How are you today ?"

for _, c := range hello {
	Print(c)
}

// -> Hello everyone ! How are you today ?
```

* Récursive (Utilisation d'une fonction)

``` Go
nb := 0

fuc Recursive(nb int) int {
	if nb > 15 {
		return nb
	}
	return Recursive (nb + 1)
}
nb = Recursive (nb)
Print(nb) // -> 16
```
