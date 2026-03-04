5.11.2025

---
# Prejsn tedn
Prejsn tedn je blo treba sami it cez predavanje kr je odpadl
https://ucilnica.fri.uni-lj.si/mod/bigbluebuttonbn/view.php?id=35392
## Slides:
![[OUI-3 2025-26 Bayes, nomogrami, kNN.pdf]]

## Content
- k - nearest neighbor
- Regresijska drevesa
---
# Regresija, nevronske mreže, nenadzorovano
## Slides:
![[OUI-4 2025-26 regresija, nevronske mreže, nenadzorovano.pdf]]

## Content
### Linearni modeli
$h(x) = w_1x + w_0$
*Linearna regresija je iskanje funkcije (uteži $w_0$ in $w_1$), ki se najbolj prilega učnim podatkov*

Optimizacijo izvedemo z minimizacijo napake funkcije h

$napaka(h) = \sum(y_j - (w_1 x_j + w_0))^2$

![[Pasted image 20251105143219.png]]

#### Posplošitev v višje število dimenzij
$h(x) = w_0 + \sum_i w_i x_{j,i}$
 V praksi iščemo koeficiente w z **gradient spustom**
 
![[Pasted image 20251105144259.png]]