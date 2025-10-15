1.10.2025
#### Slides: 
![[OUI-1 2025-26 Uvod, strojno ucenje.pdf]]

#### [[Kvizi]] - Obvezno narediti 4/5
#### [[Dodatni izzivi]]  - Tekmovanje za bonus oceno
#### [[Literatura]] - Priporočeno

Pričetek vaj 9.10.2025
Predavanja
29.10 Odpade
3.12 Odpade?
24.12 Praznik
31.12 Praznik

#### Umetna inteligenca
Umetna inteligenca je nekaj kar glede na nabor vhodnih podatkov da neke izhodne. Je poskus ustvarjanja inteligence na umeten način. 
#### Vsebina predmeta:
1. [[Strojno učenje]]
2. Reševanje problemov
3. Igranje iger
4. Planiranje
5. Predstavitev negotovega znanja
6. Avtomatsko sklepanje
#### Kaj je umetna inteligenca?
Njen cilj je razumeti in zgraditi človeško razmišljanje, slediti človeško racionalizacijo. 
![[Turingov Test]]
Deep blue je prvi *ai* ki je premagal chess gm - Kasparov takratni world champion 1997. Pri 19 potezi že. Deloval je na brute force način z uporabo 20 paralelnih procesorjev. Kot predznanje je imel *book of openings*.     

#### Vrste strojnega učenja:
- [[Supervised learning]]
- [[Unsupervised learning]]
- [[Reinforcement learning]]

V sklopu predmeta se bomo učili Supervised in Unsupervised, v sklopu inteligentnih sistemov pa se Reinforcement.

#### Primer klasifikacije gobe, kateri izbor je pravilni?
Tisti h, ki pravilno izbere tudi vse gobe v prihodnosti?

>Točnost na vidnih primerih -> ==**Konsistentnost**==
>Točnost na nevidenih primerih -> ==**Splošnost**==

![[Pasted image 20251001161358.png]]

Vse prikazane so **Konsistentne**, vendar katere so tudi **Splošne**. **Splošnost** je izjemno pomembna, to bomo testirali tako, da bomo poskusili agenta na vhodnih podatkih, ki mu niso bili podani pri učenju.
Pomembno je tudi število parametrov, ki jih vsebujejo.
#### Princip Ockhamove britve
> *Entities should not be multiplied unnecessarily 
> Given two explanations of the data, all other things being equal, the simpler explanation is preferrable.*

**Prava hipoteza je najbolj preprosta hipoteza** 
#### Overfitting
Problem, ko hipotezo prekomerno prilagodimo vhodnim podatkom
![[Pasted image 20251001162621.png]]
#### Prostor hipotez
##### denimo, da imamo binarno klasifikacijo 
• 𝑛 binarnih atributov 
• sledi: 
→ 2^𝑛 različnih učnih primerov 
→ 2^2^𝑛 hipotez (denimo, da lahko hipotezo opišemo s tabelo napovedi za vse primere)
##### potrebujemo: 
• algoritme za gradnjo "dobrih" hipotez 
• metode za ocenjevanje hipotez / ocenjevanje učenja 
• zavedanje o pristranosti hipotez

#### Evalviranje hipotez
##### pomembni kriteriji: 
• konsistentnost hipotez s primeri (učnimi) 
• splošnost (točnost za nevidene primere) 
• razumljivost (interpretability, comprehensibility) hipotez

![[Pasted image 20251001163142.png]]

#### Izpitna naloga

![[Pasted image 20251001163254.png]]

**f** -> C = IF (AB^2) < (A + B) THEN 1 ELSE 0
##### a)
Nevideni primeri -> Splošnost
Dodamo primer A = 1, B = 1 -> C = 1
H1: 1
H2: 0

**H1 je bolj splošna**
##### b)
Klasificijska točnost je na vidnih primerih

**Oba imata enako, 100%**
##### c)

##### d)
neznamo še





