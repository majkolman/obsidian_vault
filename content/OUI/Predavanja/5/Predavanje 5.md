12.11.2025

---
# Regresija...
## Slides:
![[OUI-4 2025-26 regresija, nevronske mreže, nenadzorovano.pdf]]
## Content
### Nenadzorovano učenje
Zelo cenejše in lažje kot nadzorovano učenje
#### Gručenje
Je najbolj uporabljena metoda nenadzorovanega učenja
*Cilj je iskanje homogenih skupin v učnih podatkih*
Poznamo dve metodi:
- hierarhično gručenje
	iščemo vnaprej neznano število gruč
- metoda k-means
	iščemo vnaprej poznano število k gruč
##### Hierarhično gručenje
Od listov proti korenu gradimo gruče z pomočjo razdalje.
A, B, C, D, E -> (AC), B, D, E -> ((AC)B),D,E -> ((AC)B)(DE) -> (((AC)B)(DE))
![[Pasted image 20251112143649.png]]
#### Merjenje razdalj
Razdaljo med gručami lahko interpretiramo na več načinov
- razdaljo med najbližjima
- razdaljo med najbolj oddaljenima
- povprečno razdaljo
#### Opombe
Časovna zahtevnost združevalnega pristopa je $O(n^2 logn)$
$n^2$ časa za izračun matrike razdalj, $logn$ za urejanje razdalj
### Izpitna naloga
![[Pasted image 20251112152026.png]]
#### a)
Naredis tabelo razdalj
complete linkage == razdalja med najdaljšima točkama

|     | A   | B   | C   | D   | E   |
| --- | --- | --- | --- | --- | --- |
| A   | 0   | 2   | 2   | 3   | 5   |
| B   | 2   | 0   | 4   | 1   | 3   |
| C   | 2   | 4   | 0   | 3   | 3   |
| D   | 3   | 1   | 3   | 0   | 2   |
| E   | 5   | 3   | 3   | 2   | 0   |
->

|     | A   | BD  | C   | E   |
| --- | --- | --- | --- | --- |
| A   | 0   | 3   | 2   | 5   |
| BD  | 3   | 0   | 4   | 3   |
| C   | 2   | 4   | 0   | 3   |
| E   | 5   | 3   | 3   | 0   |
->

|     | AC  | BD  | E   |
| --- | --- | --- | --- |
| AC  | 0   | 4   | 5   |
| BD  | 4   | 0   | 3   |
| E   | 5   | 3   | 0   |
->

|     | AC  | BDE |
| --- | --- | --- |
| AC  | 0   | 5   |
| BDE | 5   | 0   |

=
```
    |
  ----
 |    |
 |    -- 
 -   |  |
| |  -  |
| | | | |
A C D B E
```

# Neinfor...
## Slides:
![[OUI-5 2025-26 neinformirano in hevristično preiskovanje.pdf]]

## Content

[^1]: 
