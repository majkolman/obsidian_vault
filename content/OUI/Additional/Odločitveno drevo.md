*Ponazarja relacijo med vhodnimi vrednostmi in odločitvijo*

![[Pasted image 20251008142026.png]]

**Listi** predstavljajo našo odločitev **(oznako razreda)**
$h(\vec{x}) = y$

Je razdelitev vhodnih podatkov po razredih, ki imajo enake vrednosti.

---
### Algoritem

*Je hevristični požrešni algoritem s strategijo razveji in omeji*:

1. Izberemo **najbolj pomemben atribut** in naredimo drevo glede na njegove vrednosti.
	To je atribut, ki **najbolj odločilno** razdeli primere v poddrevesa.
	
	![[Pasted image 20251008143511.png]]

1. **Rekurzivno** ponovimo na njegovih poddrevesih

2. **Če vsi elementi pripadajo istemu razredu (imajo isto vrednost) ali vozlišča ni možno deliti naprej**, ustavi gradnjo

---

### Izbira najbolj odločilnega atributa

*Je tisti ki razdeli učno množico v najbolj 'čiste' podmnožice*

> Lahko uporabimo mero entropije

$H = - \sum{p_k * log_2(p_k)}$

![[Pasted image 20251008143956.png]]

Zanima nas znižanje entropije ob delitvi učne množice glede na deljenje po atributu.
Želimo čim večji **informacijski prispevek** ali najmanjša **rezidualna entropija**

![[Pasted image 20251008144656.png]]
#### Informacijski prispevek
	$Gain(A) = I - I_{res}(A)$
#### Rezidualna entropija
	$I_{res} = -\sum{p_{v_i} \sum{p(c|v_i) * log_2(p(c|v_i))}}$
	$I_{res} = \sum{p_{v_i} * H(C|v_i)}$ 
		 kjer je C posamezen razred

---

### Problem: Večvrednostni atributi

*Atributi imajo lahko več razredov (trit, ...)*

> Brez dodatnih postopkov bo nekatere atribute ocenil boljše kot druge, čeprav so enakovredni.

##### Rešitve:
- Relativni informacijski prispevek in Gini
	*Normalizacija*
	$GainRatio(A) = \frac{Gain(A)}{I(A)} = \frac{I- I_{res}(A)}{I(A)}$
	
	*Alternativna mera*
	$Gini = \sum{p(c_1) \: p(c_2)}$
	$Gini(A) = \sum{p(v) \; \sum{p(c_1|v)\:p(c_2|v)}}$

- Binarizacija atributov
	*Pretvorba atributov v binarno vrednost*
	
	Primer {rdeča, rumena, zelena, modra}
	-> {rdeča, rumena} = F in {zelena, modra} = T
	-> {rdeča} = F in {rumena, zelena, modra} = T
	
	*Ali pa vpeljava binarnih atributov za vsako barvo*
		Dodamo v tem primeru 4 nove atribute ki so vsi T / F

- Prostor hipotez
	Če je vrednost številka izberemo mejo
		npr. vrednost je lahko 0-100
		Izberemo {<50, >=50}
		Lahko sta tudi dva ali več atributa:
		![[Pasted image 20251008163157.png]]


---

![[Kratkovidnost algoritma]]

---

![[Privzeta točnost]]

---
### Primer

- *Vhodni podatki*
	![[Pasted image 20251008142659.png]]

- *Zgrajeno drevo*
	![[Pasted image 20251008142712.png]]

- *Izračun Informacijskega prispevka*
	![[Pasted image 20251008145421.png]]

> Vidimo da deljenje po **'Type' ne zniža** entropije medtem ko deljenje po **'Patrons'** pa **precej zmanjša**
