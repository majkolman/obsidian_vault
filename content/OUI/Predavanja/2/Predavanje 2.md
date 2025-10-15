8.10.2025

---

### Slides:
![[OUI-2 2025-26 Odločitvena drevesa, šum, ocenjevanje, atributi.pdf]]

Prejšnič:
[[OUI/Predavanja/1/Predavanje 1|Predavanje 1]]

![[Odločitveno drevo]]


![[Kratkovidnost algoritma]]

### Program Orange

Za vizualizacijo podatkov, developed v laboratoriju za bioinformatiko na FRI

### Pristranost na učni množici

Problem nastane, ko imamo učno množičo neuravnoteženo, npr. dobimo podatke iz bolnice, ki vpisuje samo bolane paciente. Iz te mnozice nemoremo sklepati kdaj je človek bolan.

cilj: Maksimiziraj pričakovano točnost drevesa (vendar ne na učnih podatkih - **Nastane overfitting**)

- uporaba nevidnih podatkov

![[Pasted image 20251008164757.png]]


### Izpitna naloga

![[Pasted image 20251008153433.png]]

#### a)
$I = 0.991$	
	$I_{res}(vreme) = 0.918$

	 $I_{res}(pritisk) = 0.889$
->
Pritisk ima manjšo entropijo torej je boljši
V koren drevesa damo pritisk, ki ima tri možne vrednosti

|       | pritisk |       |
| ----- | ------- | ----- |
| nizek | srednji | visok |
| 3,1   | 1,2     | 1,1   |
| NE    |         |       |
Nato delimo še po vremenu

|        | nizek |         |
| ------ | ----- | ------- |
| sončno |       | deževno |
| 3,1    |       | 0,0     |
List je neuporaben, zato rečemo da je zgornji ze končni, in mu določimo NE

|        | srednji |         |
| ------ | ------- | ------- |
| sončno |         | deževno |
| 0,1    |         | 1,1     |
| DA     |         | NE      |
izberemo ne pri 1,1 ker je v celotni množici več NE

|        | visok |         |
| ------ | ----- | ------- |
| sončno |       | deževno |
| 1,0    |       | 0,1     |
| NE     |       | DA      |
**Dobimo končano drevo**

#### b)

#### c)
**V razred NE**