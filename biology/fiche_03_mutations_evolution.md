# Fiche 03 : Mutations et evolution

**Date de creation** : 14 novembre 2025  
**Sujet** : Mutations ponctuelles, brins homologues, principe de parcimonie, distance de Hamming

---

## Qu'est-ce qu'une mutation ?

### Definition
- Une mutation est une **erreur** qui se produit lors de la creation ou de la copie d'un acide nucleique (en particulier l'ADN)
- Ces "erreurs" sont des **changements dans la sequence de bases**

### Impact cellulaire
- Les acides nucleiques sont vitaux pour les fonctions cellulaires
- Une mutation a tendance a creer un **effet en cascade** dans toute la cellule
- Bien que les mutations soient techniquement des erreurs, une mutation tres rare peut donner a la cellule un **attribut benefique**

### Lien avec l'evolution
- Les effets macroscopiques de l'evolution sont attribuables a l'**accumulation de mutations microscopiques benefiques** sur de nombreuses generations
- L'evolution = une sequence d'erreurs qui ont ete conservees
- Slogan : **"Evolution as a Sequence of Mistakes"**

---

## Mutations ponctuelles (Point Mutations)

### Definition
- Type de mutation d'acide nucleique le plus **simple** et le plus **courant**
- Remplace **une seule base** par une autre a un seul nucleotide
- Aussi appelee SNP (Single Nucleotide Polymorphism) dans certains contextes

### Cas de l'ADN double brin
- Une mutation ponctuelle doit changer la base complementaire en consequence
- Les deux brins doivent rester complementaires

**Exemple de mutation C→A** :
```
Avant mutation :     Apres mutation :
5' - ...C... - 3'    5' - ...A... - 3'
3' - ...G... - 5'    3' - ...T... - 5'

Paire C-G → Paire A-T
```

### Representation visuelle complete
```
ADN original :   5' - ATCGATCG - 3'
                 3' - TAGCTAGC - 5'
                           ↓ mutation ponctuelle (G→T sur brin superieur)
ADN mute :       5' - ATCTATCG - 3'
                 3' - TAGATAGC - 5'
                        ↑
                    (C→A sur brin inferieur, pour maintenir complementarite)
```

### Causes des mutations ponctuelles
- **Erreurs de replication** : ADN polymerase se trompe (~1 erreur sur 10^10 bases)
- **Dommages chimiques** : oxydation, alkylation
- **Radiations** : UV, rayons X
- **Agents mutagenes** : produits chimiques, certains virus

---

## Types de mutations ponctuelles

### Selon l'effet sur les proteines

**1. Mutation silencieuse (silent)**
- Change la base mais ne change pas l'acide amine produit
- Grace a la redondance du code genetique
- Exemple : GAA → GAG (tous deux codent pour Glutamate)
- Pas d'effet phenotypique

**2. Mutation faux-sens (missense)**
- Change la base et produit un acide amine different
- Peut avoir un effet mineur ou majeur selon :
  - Position dans la proteine
  - Similarite des acides amines
- Exemple : GAA (Glu) → GUA (Val) - drepanocytose

**3. Mutation non-sens (nonsense)**
- Transforme un codon en codon stop
- Arrete prematurement la production de proteine
- Generalement deletere
- Exemple : UAC (Tyr) → UAA (Stop)

### Selon la transition/transversion

**Transition** (plus frequente) :
- Purine → Purine (A ↔ G)
- Pyrimidine → Pyrimidine (C ↔ T)

**Transversion** (moins frequente) :
- Purine ↔ Pyrimidine
- A ou G ↔ C ou T

---

## Brins homologues

### Definition
- Deux brins d'ADN provenant de genomes d'organismes ou d'especes differents sont **homologues** s'ils partagent un **ancetre recent commun**
- Les sequences homologues ont evolue a partir d'une meme sequence ancestrale

### Utilite en evolution
- Compter le nombre de bases ou les brins homologues different nous donne le **nombre minimum de mutations ponctuelles** qui ont pu se produire sur le chemin evolutif entre les deux brins

### Exemple simple
```
Espece A :  5' - ATCGATCG - 3'
Espece B :  5' - ATCTATCG - 3'
                    ↑
             1 difference

Conclusion : minimum 1 mutation ponctuelle entre A et B
```

### Types d'homologie

**Orthologues** :
- Genes homologues dans differentes especes
- Resultent de la speciation
- Generalement meme fonction

**Paralogues** :
- Genes homologues dans le meme genome
- Resultent de duplication genique
- Souvent fonctions differentes

---

## Principe de parcimonie

### Definition
- Principe biologique qui stipule que les **histoires evolutives doivent etre expliquees de la maniere la plus simple possible**
- Aussi appele "Occam's Razor" en biologie evolutive
- En latin : "Lex parsimoniae"

### Application en evolution
- On cherche a **minimiser le nombre de mutations** separant deux especes
- Si on observe une difference entre deux sequences homologues, on suppose qu'elle resulte du **minimum de changements** necessaires
- L'hypothese la plus simple (moins de mutations) est preferee

### Pourquoi c'est important
- Plus le nombre de mutations est faible, plus il est **probable** que ce soit le chemin evolutif reel
- Aide a reconstruire les **arbres phylogenetiques**
- Fondement des algorithmes d'alignement de sequences
- Reduit la complexite computationnelle

### Exemple d'analyse evolutive
```
Espece A :  ATCGATCG
Espece B :  ATCTATCG
Espece C :  ATCGATCG

A et B : 1 difference → 1 mutation minimum
A et C : 0 difference → meme sequence, pas de mutation
B et C : 1 difference → 1 mutation minimum

Conclusion par parcimonie : A et C sont plus proches evolutivement que A-B ou B-C
```

### Arbre phylogenetique simple
```
        A -------- C (meme sequence)
         \
          \
           B (1 mutation)
```

### Limites du principe
- Ne compte pas les mutations multiples au meme site
- Ne considere pas les reversions (mutation puis retour)
- Simplification de la realite evolutive
- Peut etre inexact pour sequences tres divergentes

---

## Distance de Hamming

### Definition
- Nombre de positions ou deux sequences de **meme longueur** different
- Mesure de la **distance genetique** entre deux brins d'ADN
- Approximation du nombre minimum de mutations ponctuelles
- Nommee d'apres Richard Hamming (1950)

### Prerequis important
- Les sequences doivent avoir la **meme longueur**
- Pas de gaps (insertions/deletions)
- Comparaison position par position

### Calcul
```
Sequence 1 : G A G C C T A C T A A C G G G A T
Sequence 2 : C A T C G T A A T G A C G G C C T
             ↑   ↑   ↑   ↑     ↑       ↑   ↑

Distance de Hamming = 7 differences
```

### Algorithme (pseudo-code)
```
fonction hamming_distance(seq1, seq2):
    distance = 0
    pour i de 0 a longueur(seq1) - 1:
        si seq1[i] != seq2[i]:
            distance = distance + 1
    retourner distance
```

### Interpretation
- Distance = 0 : sequences identiques
- Distance faible : sequences proches evolutivement
- Distance elevee : sequences eloignees evolutivement
- Distance maximale theorique = longueur de la sequence

### Distance normalisee
- Pour comparer des sequences de longueurs differentes
- Formule : distance / longueur
- Varie de 0 (identique) a 1 (totalement different)

### Exemple calcule
```
Seq1 : ATCGATCG (longueur = 8)
Seq2 : ATCTATCG
          ↑
Distance de Hamming = 1
Distance normalisee = 1/8 = 0.125 (12.5% de differences)
```

---

## Lien avec la bio-informatique

### Applications pratiques

**1. Comptage de mutations**
- Probleme algorithmique fondamental
- Premier probleme en bio-informatique
- Base de nombreux algorithmes plus complexes

**2. Alignement de sequences**
- Comparer deux sequences pour trouver les differences
- Algorithmes : Needleman-Wunsch, Smith-Waterman
- Detecter regions conservees vs variables

**3. Phylogenie**
- Reconstruire les arbres evolutifs en minimisant le nombre de mutations
- Methode du maximum de parcimonie
- UPGMA, Neighbor-Joining

**4. Variant calling**
- Identifier les mutations dans un genome sequence
- Comparer genome individuel vs genome reference
- Detection de SNPs, indels

**5. Analyse comparative**
- Comparer des genomes entre especes
- Identifier genes conserves (orthologues)
- Etudier evolution moleculaire

**6. Codes correcteurs d'erreurs**
- Distance de Hamming utilisee en informatique
- Detection et correction d'erreurs
- Applications en sequencage (error correction)

### Algorithmes lies

**Simples** :
- Distance de Hamming (simple comptage)
- Recherche de motifs exacts
- Consensus sequences

**Intermediaires** :
- Alignement global (Needleman-Wunsch)
- Alignement local (Smith-Waterman)
- Construction d'arbres phylogenetiques

**Avances** :
- Assemblage de genomes
- Detection de variants complexes
- Phylogenomique

---

## Points cles a retenir

### Mutations
- Erreurs lors de la copie d'ADN
- Mutation ponctuelle = changement d'une seule base
- Types : silencieuse, faux-sens, non-sens
- Cause de la variabilite genetique

### Evolution
- Accumulation de mutations benefiques
- Selection naturelle favorise mutations avantageuses
- Derive genetique pour mutations neutres

### Brins homologues
- Partagent un ancetre commun
- Permettent de tracer l'evolution
- Base de la phylogenie moleculaire

### Principe de parcimonie
- Minimiser le nombre de mutations
- L'explication la plus simple est preferee
- Fondement des methodes phylogenetiques

### Distance de Hamming
- Compte les differences position par position
- Mesure de distance genetique
- Base de nombreux algorithmes

---

## Auto-evaluation

### Questions rapides

1. Qu'est-ce qu'une mutation ponctuelle ?
2. Les mutations sont-elles toujours deleteres ?
3. Que signifie le principe de parcimonie en evolution ?
4. Comment calcule-t-on la distance de Hamming entre deux sequences ?
5. Qu'est-ce que des brins homologues ?
6. Pourquoi les mutations sont importantes pour l'evolution ?
7. Quelle est la difference entre une mutation silencieuse et faux-sens ?
8. Que signifie "evolution as a sequence of mistakes" ?
9. Combien de mutations minimum entre ATCG et TTCG ?
10. Peut-on utiliser la distance de Hamming pour sequences de longueurs differentes ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. Remplacement d'une seule base par une autre a un seul nucleotide
2. Non, certaines sont benefiques ou neutres
3. Les histoires evolutives doivent etre expliquees de la maniere la plus simple possible (minimum de mutations)
4. Compter le nombre de positions ou deux sequences different
5. Brins d'ADN de differents organismes qui partagent un ancetre commun
6. Accumulation de mutations benefiques sur de nombreuses generations = evolution
7. Silencieuse : pas de changement d'acide amine ; Faux-sens : changement d'acide amine
8. L'evolution resulte de l'accumulation d'erreurs (mutations) qui ont ete conservees
9. 1 mutation minimum (position 1 : A→T)
10. Non, elles doivent avoir la meme longueur (sinon utiliser alignement)
</details>

---

## Mnemoniques

**Types de mutations** : "**S**arah **F**ait **N**ager" (Silencieuse, Faux-sens, Non-sens)

**Principe de parcimonie** : "Le **P**lus **S**imple" (Parcimonie = Simple)

**Distance de Hamming** : "**H**amming = **C**ompte les differences" 

**Homologues** : "Meme **O**rigine, meme **H**istoire" (Homologie)

---

## Exercices pratiques

### Exercice 1 : Distance de Hamming simple
Calculer la distance de Hamming entre :
- Seq1 : ATCGATCG
- Seq2 : ATCTATCG

<details>
<summary>Solution</summary>
Position 4 : G vs T → 1 difference
Distance de Hamming = 1
</details>

### Exercice 2 : Distance de Hamming multiple
Calculer la distance de Hamming entre :
- Seq1 : GAGCCTACTAACGGGAT
- Seq2 : CATCGTAATGACGGCCT

<details>
<summary>Solution</summary>
Differences aux positions : 1, 3, 6, 10, 15, 16, 17
Distance de Hamming = 7
</details>

### Exercice 3 : Parcimonie
Trois especes avec sequences :
- A : ATCG
- B : ATCG  
- C : TTCG

Lesquelles sont les plus proches evolutivement ?

<details>
<summary>Solution</summary>
A et B : 0 difference
A et C : 1 difference
B et C : 1 difference
→ A et B sont les plus proches (sequences identiques)
</details>

### Exercice 4 : Type de mutation
Une mutation change GAA en GUA dans un gene.
Quel type de mutation ?

<details>
<summary>Solution</summary>
GAA code pour Glutamate (Glu)
GUA code pour Valine (Val)
→ Mutation faux-sens (missense) car change l'acide amine
</details>

---

## Probleme Rosalind associe

**Counting Point Mutations (HAMM)**
- Calculer la distance de Hamming entre deux sequences d'ADN
- Input : deux sequences de meme longueur
- Output : nombre de positions differentes

**Conseil** : Simple comptage, mais attention aux :
- Longueurs differentes (erreur)
- Majuscules vs minuscules
- Espaces ou caracteres speciaux

---

**Prochaine fiche** : ARN et transcription
