15.10.2025

Previously on OUI - [[OUI/Predavanja/2/Predavanje 2|Predavanje 2]]

---

Slides: ![[OUI-2 2025-26 Odločitvena drevesa, šum, naključni gozd, ocenjevanje, atributi.pdf]]
**Slide je spremenil od prejšnjega tedna**

[[Odločitveno drevo]]:
	Pri overfitting pride tudi do prevelikega drevesa

---
### Rezanje odločitvenih dreves
*Nijži deli drevesa predstavljajo večjo prilagajanje učnim podatkom, ki so lahko zaradi šuma.*
Zato odstranimo spodnje dele drevesa in s tem dosežemo boljšo posplošitev naučenega drevesa.

>**Kje odrezati drevo?**

##### Strategije rezanja
- Rezanje vnaprej
	*uporaba dodatnega kriterija, za ustavitev gradnje*
	- **hitrejše**
	- **kratkovidno**

- Rezanje nazaj
	*po gradnji drevesa *

#### Rezanje z zmanjševanjem napak (REP)
reduced error pruning

*Uporabimo posebno rezalno množico*, ki je narejena iz:
- učna množica (70%), od tega:
	- množica za gradnjo(70%)
	- rezalna množica(30%)
- testna množica (30%)

**Postopek**:
1. Začnemo pri listih
2. Za vsako vozlišče izračunamo dobitek rezanja:
	(št. napačnih klasifikacij v drevesu $T$) **-** (št. napačnih klasifikacij v vozlišču $v$)
	![[Pasted image 20251015153416.png]]
	(v je starš in T so listi, ==vedno je potrebno gledati samo liste, ne pa vmesnih vozlišč==)
3. Če je dobitek $T-v >= 0$  obreži in nadaljuj postopek s starši, sicer ustavi.

![[Pasted image 20251015153249.png]]

#### Izpitna naloga

![[Pasted image 20251015154609.png]]
#### c)
Odrežemo dvakrat:

![[Pasted image 20251015154347.png]]

---
### Naključni gozdovi
*Je model, ki je zgrajen iz številnih odločitvenih dreves*
Skupaj izboljšajo točnost in zmanjšajo overfitting

**Postopek gradnje**
- Pri gradnji posameznih dreves naključno izberemo razpoložljive atribute pri notranjih vozliščih
- Hkrati omejimo drevesa na podmnožice učne množice.
**Uporaba**
- Ko želimo odgovor pogledamo kaj odgovorijo posamezna drevesa in izračunamo povprečje

---
### Diskretizacija
*Za število se odločimo ali je večje ali manjše od neke meje*

>Kako se odločiti za mejo?
1. Izberemo možne meje za vrednost in izračunamo **residualno entropijo**
2. Izberemo vrednost, ki ima najmanjšo
### Obravnava mankajočih atributov
>Kaj narediti, ko učni primer nima vrednosti za atribut

- Lahko ignoriramo (ne najboljše)
- Uporabimo posebno vrednost (N/A)
- Nadomestimo vrednost
- **Obravnavamo verjetnostno**
	*Verjetnostna klasifikacija*
	
	Pogledamo kakšna je verjetnost za DA / NE pri primeru
	Torej gremo v vsa podrevesa in pogledamo koliko je DA in koliko je NE