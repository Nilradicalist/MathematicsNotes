# Algebra Lineare — Index

> Fonte principale: `1. AL Journal.md`  
> Corso: Algebra Lineare, A.A. 2025–2026  
> Funzione di questo file: orientare la revisione e indicare dove collocare le note.

## Posizione attuale

**Blocco attuale:** 02 — Sistemi lineari ed eliminazione di Gauss

**Compito attuale:** prova del 23 giugno 2026, Esercizio 1

**Conoscenze già utilizzate:**

- matrice dei coefficienti e matrice completa;
- eliminazione di Gauss;
- pivot e rango;
- compatibilità;
- determinante e invertibilità;
- soluzione unica, infinite soluzioni, sistema incompatibile.

**Ponte ancora mancante per il punto (iii):**

- spazio generato dalle colonne;
- immagine dell'applicazione lineare associata a una matrice;
- equivalenza
  $$
  Ax=b 	ext{ è compatibile}
  \iff
  b\in\operatorname{Im}(L_A).
  $$

Questo ponte appartiene soprattutto ai blocchi 03 e 04. Il punto (iii) resta quindi registrato come diagnosi di conoscenza mancante e verrà ripreso dopo questi concetti.

---

## 01 — Fondamenti algebrici, polinomi e numeri complessi

**Dal diario:** argomenti 1–33.

- numeri naturali e assiomi di Peano;
- relazioni, funzioni e relazioni di equivalenza;
- anelli e campi;
- interi modulo $n$ e campi finiti;
- polinomi, divisione con resto, radici e molteplicità;
- numeri complessi, coniugio, modulo e forma polare.

**Ruolo nell'esame:** fondamenti e strumenti di supporto.

**File suggeriti:**

- `01-algebraic-foundations.md`
- `02-polynomials.md`
- `03-complex-numbers.md`

---

## 02 — Sistemi lineari ed eliminazione di Gauss

**Dal diario:** argomenti 12–20, con collegamenti agli argomenti 54, 74, 76, 80, 97–111.

- matrice dei coefficienti e matrice completa;
- sistemi omogenei e non omogenei;
- sistemi equivalenti;
- matrici a scala e pivot;
- eliminazione di Gauss;
- compatibilità e numero di soluzioni;
- teorema di Rouché–Capelli;
- sistemi con parametro;
- determinante, rango e matrice inversa;
- struttura delle soluzioni:
  $$
  x=x_p+x_h.
  $$

**Ruolo nell'esame:** blocco ad altissima priorità; base tipica dell'Esercizio 1.

**File suggeriti:**

- `04-linear-systems.md`
- `05-gaussian-elimination.md`
- `06-rank-compatibility-and-solutions.md`
- `07-inverse-matrices.md`

---

## 03 — Spazi vettoriali, sottospazi, basi e dimensione

**Dal diario:** argomenti 34–65.

- spazio vettoriale e sottospazio;
- combinazione lineare e spazio generato;
- somma e intersezione di sottospazi;
- dipendenza e indipendenza lineare;
- generatori e basi;
- completamento ed estrazione di una base;
- dimensione;
- formula di Grassmann;
- somma diretta;
- equazioni cartesiane e descrizioni parametriche.

**Ruolo nell'esame:** blocco ad altissima priorità; ricorre soprattutto negli Esercizi 2 e 3.

**File suggeriti:**

- `08-vector-spaces-and-subspaces.md`
- `09-span-linear-independence-and-bases.md`
- `10-dimension-grassmann-and-direct-sums.md`

---

## 04 — Applicazioni lineari, nucleo, immagine e rango

**Dal diario:** argomenti 66–77.

- definizione di applicazione lineare;
- nucleo e immagine;
- rango e nullità;
- iniettività e suriettività;
- teorema della dimensione;
- endomorfismi, isomorfismi e automorfismi;
- applicazione lineare associata a una matrice;
- spazio delle colonne;
- compatibilità di $Ax=b$ come appartenenza all'immagine.

**Ruolo nell'esame:** blocco ad altissima priorità; collega sistemi, matrici, polinomi e spazi di matrici.

**File suggeriti:**

- `11-linear-maps.md`
- `12-kernel-image-rank-nullity.md`
- `13-matrix-associated-linear-map.md`

---

## 05 — Matrici, coordinate, cambio di base e determinante

**Dal diario:** argomenti 78–91 e 96–111.

- prodotto tra matrici;
- matrici invertibili e gruppo $GL(n,k)$;
- matrice rappresentativa di un'applicazione lineare;
- coordinate rispetto a una base;
- matrici di cambio di base;
- coniugio di matrici;
- permutazioni e determinante;
- teorema di Binet;
- cofattori, matrice aggiunta e sviluppo di Laplace;
- teorema di Cramer;
- minori e teorema degli orlati.

**Ruolo nell'esame:** strumenti trasversali per tutti i blocchi.

**File suggeriti:**

- `14-matrices-and-coordinate-representations.md`
- `15-change-of-basis.md`
- `16-determinant-and-invertibility.md`

---

## 06 — Autovalori, polinomio caratteristico e diagonalizzazione

**Dal diario:** argomenti 92–95 e 112–123.

- autovalori, autovettori e spettro;
- autospazi;
- polinomio caratteristico;
- teorema di Cayley–Hamilton;
- molteplicità algebrica e geometrica;
- criteri di diagonalizzabilità;
- base di autovettori;
- decomposizione spettrale;
- potenze di matrici diagonalizzabili;
- diagonalizzazione simultanea;
- proiettori commutanti.

**Ruolo nell'esame:** blocco ad altissima priorità; base tipica dell'Esercizio 4.

**File suggeriti:**

- `17-eigenvalues-and-eigenspaces.md`
- `18-characteristic-polynomial-and-cayley-hamilton.md`
- `19-diagonalization.md`

---

## 07 — Spazio duale e annullatori

**Dal diario:** argomenti 124–136.

- spazio duale e base duale;
- coordinate mediante la base duale;
- biduale;
- applicazione duale e matrice trasposta;
- annullatore e insieme degli zeri;
- dualità tra dimensione e codimensione;
- equazioni cartesiane tramite funzionali lineari.

**Ruolo nell'esame:** priorità inferiore rispetto ai blocchi 02–06, ma utile per comprendere equazioni cartesiane e trasposte.

**File suggeriti:**

- `20-dual-spaces.md`
- `21-annihilators-and-cartesian-equations.md`

---

## Fuori programma d'esame

La lezione del 12 gennaio 2026 sugli **spazi vettoriali quoziente** è indicata nel diario come fuori programma d'esame.

Non creare una priorità di revisione per questo argomento durante la preparazione di agosto.

---

## Ordine di revisione per l'esame

```text
02 Sistemi lineari e Gauss
    ↓
03 Spazi vettoriali, basi e dimensione
    ↓
04 Applicazioni lineari, nucleo e immagine
    ↓
05 Matrici, coordinate e determinante
    ↓
06 Autovalori e diagonalizzazione
    ↓
07 Duale e annullatori
```

Il blocco 01 viene richiamato solo quando serve come prerequisito.

---

## Mappa rapida delle prove scritte

```text
Esercizio 1
└── 02 Sistemi lineari e Gauss
    └── supporto da 05 Determinante e inversa

Esercizio 2
├── 04 Applicazioni lineari
└── 05 Matrici e rappresentazioni

Esercizio 3
├── 03 Sottospazi, basi, dimensione e Grassmann
└── 04 Nucleo, immagine e rango

Esercizio 4
└── 06 Autovalori e diagonalizzazione
```
