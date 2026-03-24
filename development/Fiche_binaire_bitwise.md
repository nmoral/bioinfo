# Fiche de révision — Representation binaire et operations bit a bit

---

## 1. Representation binaire

### Principe

Un entier est stocke en memoire comme une suite de bits (0 ou 1).
Chaque bit vaut 2^position, la position 0 etant a droite.

```
Bit :     7    6    5    4    3    2    1    0
Valeur : 128   64   32   16    8    4    2    1
```

### Puissances de 2 a connaitre par coeur

```
2^0  =   1
2^1  =   2
2^2  =   4
2^3  =   8
2^4  =  16
2^5  =  32
2^6  =  64
2^7  = 128
2^8  = 256
2^16 = 65 536
2^32 = 4 294 967 296
2^62 = 4 611 686 018 427 387 904  ← taille max d'un k-mer 31
2^64 = 18 446 744 073 709 551 616 ← max uint64_t
```

---

## 2. Conversions

### Binaire → Decimal

Additionner les puissances de 2 la ou il y a un 1 :

```
1010
│││└─ 0 * 2^0 =  0
││└── 1 * 2^1 =  2
│└─── 0 * 2^2 =  0
└──── 1 * 2^3 =  8
              = 10
```

```
11001000
││││││││
│││││││└─ 0 * 1   =   0
││││││└── 0 * 2   =   0
│││││└─── 0 * 4   =   0
││││└──── 1 * 8   =   8
│││└───── 0 * 16  =   0
││└────── 0 * 32  =   0
│└─────── 1 * 64  =  64
└──────── 1 * 128 = 128
                  = 200
```

### Decimal → Binaire

Diviser par 2 successivement, lire les restes de bas en haut :

```
10 / 2 = 5  reste 0  ↑ lire dans ce sens
 5 / 2 = 2  reste 1  |
 2 / 2 = 1  reste 0  |
 1 / 2 = 0  reste 1  |

Resultat : 1010
```

---

## 3. Table des nibbles (4 bits)

A memoriser — indispensable pour les k-mers et les masques.

```
Binaire  Decimal  Hex
0000       0       0
0001       1       1
0010       2       2
0011       3       3
0100       4       4
0101       5       5
0110       6       6
0111       7       7
1000       8       8
1001       9       9
1010      10       A
1011      11       B
1100      12       C
1101      13       D
1110      14       E
1111      15       F
```

---

## 4. Operations bit a bit

### AND &

1 si les DEUX bits sont 1, sinon 0.
Utilisation : isoler des bits (masque).

```
  11001000  (200)
& 00001111  (masque 0b1111)
----------
  00001000  (8)
```

**Regle mentale** : le AND "efface" les bits la ou le masque est 0.

### OR |

1 si AU MOINS UN bit est 1, sinon 0.
Utilisation : mettre des bits a 1, combiner des valeurs.

```
  10000000  (128)
| 00001010  (10)
----------
  10001010  (138)
```

**Regle mentale** : le OR "allume" des bits sans toucher aux autres.

### XOR ^

1 si les bits sont DIFFERENTS, sinon 0.
Utilisation : inverser des bits specifiques, detecter des differences.

```
  11001010
^ 00001111
----------
  11000101
```

**Regle mentale** : le XOR "bascule" les bits la ou le masque est 1.

### NOT ~

Inverse tous les bits.

```
~ 00001010  (10)
----------
  11110101  (245 en uint8_t)
```

**Attention** : en C++ le NOT sur un int signe peut surprendre
a cause de la representation en complement a deux.

---

## 5. Decalages

### Decalage gauche <<

Decale tous les bits vers la gauche de N positions.
Equivalent a multiplier par 2^N.

```
00000011 << 2 = 00001100
    3    << 2 = 12  (3 * 4)
```

**Les bits qui "sortent" a gauche sont perdus.**

### Decalage droit >>

Decale tous les bits vers la droite de N positions.
Equivalent a diviser par 2^N (division entiere).

```
00001100 >> 2 = 00000011
    12   >> 2 = 3  (12 / 4)
```

**Les bits qui "sortent" a droite sont perdus.**

---

## 6. Masques courants

```
0b1          = 0x01  = 1    → isoler 1 bit
0b11         = 0x03  = 3    → isoler 2 bits (1 nucleotide)
0b1111       = 0x0F  = 15   → isoler 4 bits (2 nucleotides)
0b11111111   = 0xFF  = 255  → isoler 8 bits (1 octet)
0xFFFF       = 65535        → isoler 16 bits
0xFFFFFFFF   = 4294967295   → isoler 32 bits
```

---

## 7. Encodage des nucleotides

```
A = 00 = 0
C = 01 = 1
G = 10 = 2
T = 11 = 3
```

### Encoder un k-mer

```cpp
// Pour chaque nucleotide, decaler et ajouter
resultat = (resultat << 2) | encoder_nucleotide(c);
```

```
"ACGT" :
  A=00 → resultat = 00
  C=01 → resultat = 00 01  = 0001
  G=10 → resultat = 0001 10 = 000110
  T=11 → resultat = 000110 11 = 00011011 = 27
```

### Extraire un nucleotide a la position pos

```cpp
int nucleotide = (kmer >> (pos * 2)) & 0b11;
```

```
kmer = 00011011  (ACGT)
pos  = 1         (C, deuxieme depuis la droite)

kmer >> 2  = 00000110
& 0b11     = 00000010 = 2 = G ?
```

**Attention** : l'ordre depend de la convention d'encodage choisie.
Le premier nucleotide encode peut etre le plus a gauche ou le plus a droite.
Choisir une convention et s'y tenir.

### Pourquoi k=31 dans Kraken2

```
uint64_t = 64 bits
1 nucleotide = 2 bits
64 / 2 = 32 nucleotides maximum

Mais on reserve 2 bits pour des metadonnees
→ k = 31 est le maximum pratique
→ 4^31 ≈ 4,6 * 10^18 k-mers possibles
```

---

## 8. Patterns courants en C++

### Isoler N bits a la position pos

```cpp
(valeur >> pos) & masque
```

### Mettre un bit a 1 a la position pos

```cpp
valeur | (1 << pos)
```

### Mettre un bit a 0 a la position pos

```cpp
valeur & ~(1 << pos)
```

### Tester si le bit pos est a 1

```cpp
(valeur >> pos) & 1
```

### Placer une valeur de N bits a la position pos

```cpp
valeur | (bits << (pos * N))
```

---

## 9. Types entiers en C++

```cpp
#include <cstdint>

uint8_t   // 8 bits  non signe  0 a 255
uint16_t  // 16 bits non signe  0 a 65535
uint32_t  // 32 bits non signe  0 a ~4 milliards
uint64_t  // 64 bits non signe  0 a ~18 * 10^18

int8_t    // 8 bits  signe  -128 a 127
int16_t   // 16 bits signe
int32_t   // 32 bits signe  ~-2 milliards a ~2 milliards
int64_t   // 64 bits signe
```

**Pour les k-mers** : toujours utiliser `uint64_t`.
Les types non signes evitent les surprises avec les decalages.

---

## 10. Auto-evaluation

1. Convertir 42 en binaire
2. Convertir 0b10110101 en decimal
3. Resultat de 170 & 0b11110000 ?
4. Resultat de 12 << 3 ?
5. Resultat de 200 >> 4 ?
6. Quel masque pour isoler les bits 4 et 5 d'un entier ?
7. Encoder "ATCG" en uint64_t
8. Extraire le 3eme nucleotide de 0b00011011

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. 42 = 32+8+2 = 0b00101010
2. 0b10110101 = 128+32+16+4+1 = 181
3. 170 & 0b11110000 = 10101010 & 11110000 = 10100000 = 160
4. 12 << 3 = 12 * 8 = 96
5. 200 >> 4 = 200 / 16 = 12
6. 0b00110000 = 0x30 = 48
7. A=00, T=11, C=01, G=10 → 00 11 01 10 = 0b00110110 = 54
8. pos=2 → (0b00011011 >> 4) & 0b11 = 0b00000001 = 1 = C

</details>

---

## Pour aller plus loin

### Lectures
- *Hacker's Delight* (Warren) — la bible des operations bit a bit
- *Code* (Petzold) — comment les ordinateurs representent l'information

### Ressources en ligne
- `bits.stephan-brumme.com` — tricks bit a bit
- `visualgo.net` — visualisation des operations
- `bitwisecmd.com` — calculatrice bit a bit interactive

### Lien avec T2
- Encodage des k-mers → index metagenomique
- Masques → extraction rapide de nucleotides
- Decalages → construction et decodage de k-mers
- Bloom filter → structure probabiliste basee sur des hash bit a bit
- Minimizers → selection de k-mers par comparaison bit a bit
