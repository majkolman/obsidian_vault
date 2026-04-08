COCOMO 2 medota za financno porocilo:
==pri racunanju naj povemo da smo uporabli tocno to==

Časovna zahtevnost projekta (v človek-mesecih) ocenimo po sledeči formuli:
$effort_{ČM} = A * size^B *M$
privzeta vrednost A = 2,94

COCOMO se uporablja, ko imamo zahteve vendar pa se nimamo načrtovanja (zgodnja faza)

$size^B$ je obseg projekta v številu vrstic kode (v tisočih)
-  rešitev razbijemo glede na funkcionalnost
-  EI - proces, ki uporablja zunanje podatke
-  ILF - če uporablja bazo npr MongoDB
-  EIF - če uporablja bazo od zunanje aplikacije
-  EQ - proces, ki naredi poizvedbo in vrne podatke
-  EO - pripravi podatke za zunanji svet brez baze

-  nato jim določis kvalitativni obseg (nizek, povprečni in visok)
	- EI - glede na DET in FTR
		- DET je št skupnih vnosnih el. (gumb,...)
		- FTR je število baz do katerih dostopa.
	- EQ in EO na podoben način
		- DET je št prebranih podatkov
	- ILF in EIF
		- DET je št unikatnih stolpcev v vseh tabelah skupaj
		- RET je st razlicnih skupin podatkov
	- https://www.qsm.com/resources/function-point-languages-table
	- vzames average in mnozis z izracunanim zgoraj
	- nato /1000

Parameter B
-  $B = 1.01 + 0.01 \sum{w_i}$
-  wi (zelo nizka, nizka, nominalna, visoka, zelo visoka, zelo visoka, izjemno visoka):
	- PREC - ce smo ze delal podobno (nekje nizko)
	- FLEX - koliko se zahteve spreminjajo (kuk si narocnik zmisluje --> pri nas nizko)
	- RESL - koliko smo pripravljeni na tveganja(pri nas zelo)
	- TEAM - kuk se ekipa pozna (differs)
	- PMAT - maturity level procesa po modelu CMM(nivo max tak res max 2 bolj 0 al pa 1)
		- v dokument treba napisat kako smo prsl do stev, ce je nivo 1 je potem vrednost wi = 5. to ni dovolj, treba backat up claim z modelman pdf page 23-24. Vzames tabelo in jo izpolnes nato sestejes z formulo na page 24.
		![[Pasted image 20260309084835.png]]
- https://www.cs.montana.edu/courses/spring2004/352/public/cocomo/modelman.pdf
==vrednosti nizka,... se preslikajo v stevilke zelo nizka = 5, ..., izjemno visoka = 0==

Parameter M
- $M = \prod{multiplier_i}$
- zelo nizka, nizka, nominalna, visoka, zelo visoka, izjemno visoka	
	- PERS
	- PREX
	- RCPX
	- RUSE - kuk se morajo reusat komponente (nizka)
	- PDIF - (nizka)
	- SCED - (1.0)
	- FCIL - (odvisno kaj uporabljamo pri razvoju)

Po izracunu pogledamo ali je projekt izvedljiv
62 dni dela * 5 ljudi = 310 ŠČD (Študentski človek dan; 2,5ur - 5ur na dan dela za projekt)
ŠČD = 4h, $\frac{ČD}{ŠČD} = \frac{8h}{4h} = 2$
$7,39ČM = 7,39 * 20 = 147,80 ČD = 295,6 ŠČD -- 295,6 < 310$
torej je projekt izvedljiv, če vsak student dela 4 ure na dan za 62 dni
==mora bit izvedljiv==

Finance
Strošek dela + ostali costs
po aktivnostih je bolše

Kar je napisan sam link do dol mora bit spodi (cilji projekta), ker uporabljajo prompt za ocenjevanje. Uvod naj ima motivacijo za "direktorja" da dobi hiter vtis nekje 200 besed.
Opis sistema naj ima blokovni diagram (vsaj client - server), ki je za zdaj zelo abstrakten.
Dnevnik sprememb naj vsebuje res vse kar se spremeni.

