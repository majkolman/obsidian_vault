Funkcionalne zahteve morajo biti tocno dolocene in nedvoumne (da uporabnik nemore jambrat kaj je drugo hotu)

kaj naj ze ima aplikacija
- zaslonske maske
- API (vmesnike do sistemov)

Zaslonske maske je vsejeno kako naredimo vazno je da se vidi kako izgleda (lahko je prototip, samo oblika, ...). 

UXD - user experience design - tega verjetno nebomo delal
UID - user interface design - to pa bomo delal
UED - user interface engineering - kako spraviti to v kodo

Lahko naredimo v figmi, inVision ali pa dejanski prototip

Ce se uporablja funkcija v razlicnih vlogah je treba za vsako vlogo naredit svojo masko. Npr home page za uporabnike in admine je mogoc different

RestAPI - najboljs da uporabmo SWAGGER UI - ==opis vhoda, opis izhoda za vsak karakteristicni primer atributov. tudi s primeri, kake record sete nam vrne==

Nefunkcionalne zahteve 
==Zelo pomembna točka 4.!!== nefunkcionalne zahteve so lahko bolj kriticne kot funkcionalne zahteve.

Znacilno je da so pogosto kvantificirane, vplivajo na uporabnisko izkusnjo in na arhitekturo tehnolihijo in stroske, se neki ko nism slisu.

Funkcionalna zahteva:
- skatla za mleko
nefunkcionalna:
- skatla mora zdrzat padec 1m
- nesme se razgradit
- material mora bit recyclable
- odpiranje mora bit izvedeno z eno roko

Metrike za dolocanje nefunkcionalnih zahtev izdelka:
- uporabnost (ucna krivulja)
	- ucinkovitost(cas potreben za doseganje ciljev, stevilo opravljenih transakcij brez napak)
	- intuitivnost(kako preprosto je ratumeti vnosnik)
	- nizka zaznana delovna obremenitev (koliko uporabnikov je potrebno za izvedbo naloge)
- varnost (slika kljucavnice)
- zanesljivost (slika spedometra)
	- odstotek pravilno opravljenih operacij
	- povprecen cas brez napake
- uspesnost / izvedba
- razpolozljivost (uptime)
	- upostevati nadgradnje
	- kaj mora bit vedno
	- uporabniska obvestila o vzdrzevanju (kdaj, kaj, kako pocasneje bo delal, kaj bo okrnjeno)
- razširljivost (slika ko se window poveca)

Za vseh teh 6 je treba napisat kaj velja za nas in za naso aplikacijo. Ne samo to ampak tudi organizicijske in zunanje zahteve

npr.
Organizacijske zahteve

Zunanje zahteve:
SIpass
GDPR
morjo bit apiji v skladu s standardom
sistem mora bit compatible z zunanjim sistemom ERP (SAP pri primeru)
podpore za manjsine (jezik)

**Predstavitev zahtev (do zdej je blo z uporabniskimi zgodbami)**
Vsako interakcijo s sistemom bomo prestavili z primerom uporabe
Vsaka zahteva se gleda s strani uporabnika

*Kako predstavmo primer uporabe?*
Primer uporabe prestavimo z:
1. Diagram primera uporabe
2. Specifikacije primerov strukturirane v besedilni obliki
	1 - 11 tock za vsak tock primera uporabe

Diagram je narejen iz:
- ne uporabljat imen v slislu "racun" ampak naj bo glagolska fraza
	Primer uporabe: (predstavlja scenarij uporabe); in ime mora bit glagolska fraza
	npr.
	Ustvari racun, kupi karto namesto racun, karta
	nikol nebo !!nesme!!
	A -> B -> C
- akterji so na levi, na desni so zunanji sistemi, naprave
- meje sisteme (s kom mamo opravka) je by the book levo zgori v kvadratu
- akterji so zunanji sistemi (google drive, ...)
- akterji so lahko tudi med sabo povezani kar pomeni da en akter podeduje vse aktivnosti ki jih lahko naredi drug
- povezave delimo na 3:
	visji referend -> kupi karto
	1. asociacija
		je komunikacijska linija med akterjem in primerom uporabe
		wrong primer:
		kupec -> visji referend -> kupi karto
		pravilno:
	2. generalizacija (dedovanje)
		lahko delamo med akterji in med primeri uporabe
	3. odvisnost
		include in extends
		npr. 
		a -> b
		extends
		a-> b, hkrati a->c, a->d

Specifikacija primera uporabe:
Extends moramo napisati pri specifikaciji npr.
IME RAZSIRITVENE TOCKE : Pogoj : IME PRIMERA UPORABE

1. Naslov, ime primera uporabe
	- narocanje dokumenta, dodajanje knjiznice v sistem (to so krogci na diagramu)
2. Akterji
	- uporabnik, delavec(za vsakega navedemo ali gre za vlogo, zunanji sistem ali napravo)
3. Povzetek funkcionalnosti
	- v enem ali vec stavkih kratek tekstovni opis kaj posamezen primer uporabe pocne
	npr. Uporabnik ali delavec knjiznice lahko naroci dokument iz drugih knjiznic
4. Osnovni tok (happy path / main flow)
	- Opredelite zaporedje akcij tocno tako kot je predvideno brez izjem
5. Alternativni tokovi (posamezen tok mora bit poimenovan po tem kaj naredi)
	- alternativni tokovi (unusual ampak pripelje od resitve)
		opisemo v celoti od zacetka do konca
	- izjemni tok (napake) 
6. Predpogoji 
	(kaj mora bit izpolnjeno da se tok lahko zacne izvajati)
7. Popogoji
	kaksni so ucinki bodisi uspesnega bodisi neuspesnega izvedenega primera uporabe
8. Posebne zahteve
9. Prioriteta (Must have, Should have, Could have, wont have this time)
10. ==Sprejemni testi==
11. ==Razsiritve, pogostost uporabe, posebne zahteve, trigger==
	pomembno ali se izvede samo enkrat ali veckrat na dan, kaj je sprozilec tega use casa

==to vse je glavni del 2. porocila to mora bit v nulo narejeno==

