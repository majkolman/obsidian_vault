15.10.2025

**Vaje niso obvezne**, na njih se delajo izpitne naloge.
!!!>=50% na kvizih

Naloge na koncu vaj niso obvezne.

Uporaba PyCharm kot IDE.

## Pandas library
`import pandas as pd`

---
#### Serija
`pd.Series([])`
- Naredi seznam, kjer so vsi elementi istega podatkovnega tipa
##### iloc
`serija.iloc[i]`
- Index location -- vrne element na mestu enako kot na seznamu
`serija.iloc[[i1,i2,i3]]`
 - Možnost izpisa večih elementov
##### loc
`serija.loc[i]`
- Za ne inicializirane indekse, torej lahko dodamo elemente
Pozor, *index* je ubistvu samo **ime elementa** (lahko bi bilo tudi `serija.loc['A']`), kjer iloc gleda fizično pozicijo (index)
##### drop
`serija.drop[i]`
- izbrise element
##### reset_index
`serija.reset_index()`
- ponovno oštevilči
##### Maske
`maksa = [True, False, True]`
`serija[maska]`
- Vrne samo elemente, kjer je **True**
`serija[serija > 50 | serija < 70]`
- Primer, kjer se vrnejo elementi, ki so večji od 50 in manjši od 70
##### mean
`serija.mean()`
- Vrne povprečno vrednost
##### min
`serija.min()`
- Vrne najmanjši element

---
#### DataFrame
`slovar = {"Ime" = "Maj", "Starost" = 22}`
`pd.DataFrame(slovar)`
Ustvari učno množico iz podanega slovarja. Iz slovarja vzame ključe in jih naredi v atribute (imena stolpcev), vrednosti pa vpiše v stolpce.

`df.shape`
- Vrne obliko učne množice npr. (1, 3)
`df.dtypes`
- Vrne tipe stolpcev
`df.columns`
- Vrne imena stolpcev
`df.index`
- Vrne imena vrstic
`df.head(n)`
- Vrne prvih n vrstic
`df.tail(n)`
- Vrne zadnjih n vrstic
##### iloc
`df.iloc[1:4,[0, 5]]`
- Lahko uporabljamo iloc po dveh dimenzijah hkrati
##### loc
Enako kot iloc lahko tudi loc uporablja dve dimenzije. Loc je uporabljen tudi za dodajanje novih vrstic v učno množico.
##### Dodajanje novega stolpca
`df["NovStolpec"] = [...]`
##### drop
`df.drop(columns=["Prenovljeno"])`
- Izbris stolpcev
`df.drop(index=["C"])`
- Izbris vrstic
##### unique
`df.Ime.unique`
- Vrne nabor možnih vrednosti za stolpec
##### value counts
`df.Ime.value_counts`
- Prešteje vsak pojav vrednosti
##### Grupiranje
`df.groupby("Tip_ogrevanja")["Kvadratura"].mean()`
- Združi stolpca in izbise možne vrednosti
![[vaje0.py]]