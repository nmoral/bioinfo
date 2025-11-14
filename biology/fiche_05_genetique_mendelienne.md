# Fiche 05 : Genetique mendelienne et heredite

**Date de creation** : 14 novembre 2025  
**Sujet** : Lois de Mendel, alleles, genotype, phenotype, carre de Punnett

---

## Contexte historique

### Avant Mendel : "Blending inheritance"

**Modele dominant (avant 1865)**
- Theorie de l'heredite par melange
- Un organisme doit exhiber un **melange** des traits de ses parents
- Vision des traits comme un processus continu

**Problemes du modele**
1. **Violations empiriques** :
   - Nombreuses personnes plus grandes que leurs deux parents
   - Traits qui "sautent" des generations
   - Reapparition de traits des grands-parents

2. **Problemes statistiques** :
   - Avec le temps, tous les traits se melangeraient vers la moyenne
   - Limitation severe de la variation
   - Contradiction avec la diversite observee

### Revolution mendelienne (1865)

**Gregor Mendel**
- Moine augustinien
- Experimenta avec des milliers de plants de pois
- Publication : 1865 (mais reconnue seulement en 1900)

**Nouveau paradigme**
- Traits = blocs de construction **discrets** appeles **facteurs**
- Chaque facteur possede des **formes distinctes** : les alleles
- Vision particulaire de l'heredite

---

## Concepts fondamentaux

### Facteur (Factor)
**Definition**
- Unite hereditaire discrete
- Correspond aujourd'hui au concept de **gene**
- Controle un trait specifique

**Exemples chez les pois de Mendel**
- Couleur de la fleur (violet vs blanc)
- Forme de la graine (lisse vs ridee)
- Hauteur de la plante (grande vs petite)
- Couleur de la graine (jaune vs verte)

### Allele (Allele)
**Definition**
- Forme distincte d'un facteur/gene
- Versions alternatives du meme gene
- Chaque individu possede 2 alleles pour chaque facteur

**Notation**
- **Allele dominant** : lettre MAJUSCULE (ex: A, B, T)
- **Allele recessif** : lettre minuscule (ex: a, b, t)

**Exemple**
```
Facteur : Couleur de la fleur
Allele dominant (A) : Violet
Allele recessif (a) : Blanc
```

### Alleles dominants et recessifs

**Allele dominant**
- S'exprime meme en **une seule copie**
- Masque l'allele recessif
- Note en majuscule

**Allele recessif**
- S'exprime seulement en **deux copies**
- Masque par l'allele dominant
- Note en minuscule

**Regle cle**
> Un organisme n'a besoin que d'**une seule copie** de l'allele dominant pour afficher le trait dominant.

> Un organisme doit etre **homozygote recessif** (deux copies) pour afficher le trait recessif.

---

## Zygotie : Homozygote vs Heterozygote

### Homozygote
**Definition**
- Les deux alleles pour un facteur sont **identiques**
- Peut etre homozygote dominant ou recessif

**Types**
- **Homozygote dominant** : AA
  - Deux alleles dominants
  - Affiche le trait dominant
  
- **Homozygote recessif** : aa
  - Deux alleles recessifs
  - Affiche le trait recessif
  - **Seule facon** d'afficher le trait recessif

**Exemple**
```
AA : Fleur violette (homozygote dominant)
aa : Fleur blanche (homozygote recessif)
```

### Heterozygote
**Definition**
- Les deux alleles pour un facteur sont **differents**
- Un allele dominant + un allele recessif
- Notation : Aa

**Caracteristiques**
- Affiche le trait **dominant**
- Porte l'allele recessif **sans l'exprimer**
- Aussi appele "porteur" de l'allele recessif

**Exemple**
```
Aa : Fleur violette (heterozygote)
     Apparence identique a AA
     Mais genotype different !
```

---

## Genotype vs Phenotype

### Genotype
**Definition**
- Constitution genetique **precise** d'un organisme
- Ensemble des alleles possedes
- Information au niveau de l'ADN

**Notation**
- AA, Aa, aa (pour un facteur)
- Plus complexe pour plusieurs facteurs

**Important**
- Le genotype est la "recette"
- Invisible a l'oeil nu
- Necessite analyse genetique

### Phenotype
**Definition**
- Manifestation **physique** des traits
- Apparence observable
- Resultat de l'expression du genotype

**Caracteristiques**
- Ce qu'on voit, mesure, observe
- Influence par l'environnement aussi
- Peut etre identique pour genotypes differents

### Relation Genotype â†' Phenotype

**Tableau de correspondance** (exemple : couleur de fleur)

| Genotype | Zygotie | Phenotype |
|----------|---------|-----------|
| **AA** | Homozygote dominant | Violet |
| **Aa** | Heterozygote | Violet |
| **aa** | Homozygote recessif | Blanc |

**Observation cle**
- AA et Aa â†' **meme phenotype** (violet)
- Mais **genotypes differents**
- Impossible de distinguer AA de Aa par simple observation
- Necessite de croiser avec aa pour determiner

---

## Premiere loi de Mendel : Loi de segregation

### Enonce
> Chaque organisme possede une **paire d'alleles** pour un facteur donne. Lors de la formation des gametes, ces alleles se **separent** (segregent) de facon aleatoire, et chaque gamete recoit **un seul allele**. Un individu recoit donc **un allele de chaque parent**.

### Principes cles

**1. Paire d'alleles**
- Chaque individu : 2 alleles par facteur
- Un allele du pere, un de la mere

**2. Segregation lors de la meiose**
- Les deux alleles se separent
- Chaque gamete recoit 1 seul allele
- Processus aleatoire (50/50)

**3. Reunion lors de la fecondation**
- Gamete du pere (1 allele) + Gamete de la mere (1 allele)
- â†' Descendant (2 alleles)

### Illustration

```
Parent 1 (Aa) :  A | a
                  â†"   â†"
              Gametes : 50% A, 50% a

Parent 2 (Aa) :  A | a
                  â†"   â†"
              Gametes : 50% A, 50% a

Fecondation :
   A (parent 1) + A (parent 2) â†' AA (25%)
   A (parent 1) + a (parent 2) â†' Aa (25%)
   a (parent 1) + A (parent 2) â†' Aa (25%)
   a (parent 1) + a (parent 2) â†' aa (25%)
```

---

## Carre de Punnett

### Definition
- Diagramme representant les combinaisons possibles d'alleles
- Outil pour predire les genotypes de la descendance
- Nomme d'apres Reginald Punnett (1905)

### Construction

**Etape 1** : Identifier les genotypes parentaux
```
Parent 1 : Aa
Parent 2 : Aa
```

**Etape 2** : Determiner les gametes possibles
```
Parent 1 gametes : A ou a
Parent 2 gametes : A ou a
```

**Etape 3** : Construire le tableau
```
           Parent 2
         |  A  |  a  |
    -----+-----+-----+
    A    | AA  | Aa  |
P   -----+-----+-----+
a   a    | Aa  | aa  |
r   -----+-----+-----+
e
n
t
1
```

**Etape 4** : Analyser les resultats
```
Genotypes descendance :
- 1 AA (25%) : homozygote dominant
- 2 Aa (50%) : heterozygote
- 1 aa (25%) : homozygote recessif

Phenotypes descendance :
- 3 dominants (75%) : AA + Aa
- 1 recessif (25%) : aa

Ratio genotypique : 1:2:1 (AA:Aa:aa)
Ratio phenotypique : 3:1 (dominant:recessif)
```

### Exemples de croisements

#### Croisement 1 : Homozygote dominant x Homozygote recessif
```
Parent 1 (AA) x Parent 2 (aa)

       |  a  |  a  |
    ---+-----+-----+
    A  | Aa  | Aa  |
    ---+-----+-----+
    A  | Aa  | Aa  |
    ---+-----+-----+

Resultat : 100% Aa (heterozygotes)
Phenotype : 100% dominant
```

#### Croisement 2 : Heterozygote x Heterozygote
```
Parent 1 (Aa) x Parent 2 (Aa)

       |  A  |  a  |
    ---+-----+-----+
    A  | AA  | Aa  |
    ---+-----+-----+
    a  | Aa  | aa  |
    ---+-----+-----+

Resultat : 25% AA, 50% Aa, 25% aa
Ratio genotypique : 1:2:1
Ratio phenotypique : 3:1 (dominant:recessif)
```

#### Croisement 3 : Heterozygote x Homozygote recessif (test cross)
```
Parent 1 (Aa) x Parent 2 (aa)

       |  a  |  a  |
    ---+-----+-----+
    A  | Aa  | Aa  |
    ---+-----+-----+
    a  | aa  | aa  |
    ---+-----+-----+

Resultat : 50% Aa, 50% aa
Ratio : 1:1 (heterozygote:homozygote recessif)
Phenotype : 50% dominant, 50% recessif
```

**Utilite du test cross**
- Permet de determiner le genotype d'un individu dominant
- Si descendance = 100% dominant â†' parent est AA
- Si descendance = 50/50 â†' parent est Aa

---

## Croisements avec plusieurs facteurs

### Loi de l'assortiment independant (2e loi de Mendel)

**Enonce**
> Les alleles de facteurs differents segregent **independamment** les uns des autres lors de la formation des gametes.

**Exemple** : 2 facteurs chez les pois
- Facteur 1 : Couleur (Y=jaune dominant, y=vert recessif)
- Facteur 2 : Forme (R=lisse dominant, r=ride recessif)

**Parents** : YyRr x YyRr (dihybrides)

**Gametes possibles** (par parent)
- YR (25%)
- Yr (25%)
- yR (25%)
- yr (25%)

**Carre de Punnett 4x4**
```
         |  YR  |  Yr  |  yR  |  yr  |
    -----+------+------+------+------+
    YR   | YYRR | YYRr | YyRR | YyRr |
    -----+------+------+------+------+
    Yr   | YYRr | YYrr | YyRr | Yyrr |
    -----+------+------+------+------+
    yR   | YyRR | YyRr | yyRR | yyRr |
    -----+------+------+------+------+
    yr   | YyRr | Yyrr | yyRr | yyrr |
    -----+------+------+------+------+
```

**Ratio phenotypique** : 9:3:3:1
- 9 jaune-lisse
- 3 jaune-ride
- 3 vert-lisse
- 1 vert-ride

---

## Applications et exemples

### Exemple 1 : Couleur des yeux (simplifie)

**Facteur** : Couleur des yeux
- B (brun) : dominant
- b (bleu) : recessif

**Cas 1** : Deux parents aux yeux bruns (Bb x Bb)
```
Descendants possibles :
- 25% BB (bruns)
- 50% Bb (bruns)
- 25% bb (bleus)

Surprise : enfant aux yeux bleus possible !
```

**Cas 2** : Parent yeux bruns (Bb) x Parent yeux bleus (bb)
```
Descendants possibles :
- 50% Bb (bruns)
- 50% bb (bleus)

Ratio 1:1
```

### Exemple 2 : Groupe sanguin ABO (plus complexe)

**3 alleles possibles** : A, B, O
- A et B : co-dominants
- O : recessif

**Genotypes possibles**
| Genotype | Phenotype |
|----------|-----------|
| AA ou AO | Groupe A |
| BB ou BO | Groupe B |
| AB | Groupe AB |
| OO | Groupe O |

**Croisement** : Parent A (AO) x Parent B (BO)
```
       |  B  |  O  |
    ---+-----+-----+
    A  | AB  | AO  |
    ---+-----+-----+
    O  | BO  | OO  |
    ---+-----+-----+

Descendants possibles :
- 25% AB (groupe AB)
- 25% AO (groupe A)
- 25% BO (groupe B)
- 25% OO (groupe O)

Tous les 4 groupes possibles !
```

---

## Points cles a retenir

### Concepts fondamentaux
- **Facteur** = gene (unite hereditaire)
- **Allele** = version d'un gene
- **Dominant** = s'exprime avec 1 copie
- **Recessif** = necessite 2 copies

### Zygotie
- **Homozygote** : 2 alleles identiques (AA ou aa)
- **Heterozygote** : 2 alleles differents (Aa)

### Genotype vs Phenotype
- **Genotype** : constitution genetique (AA, Aa, aa)
- **Phenotype** : manifestation physique (violet, blanc)
- Meme phenotype peut avoir differents genotypes (AA = Aa en apparence)

### Loi de segregation
- 2 alleles par facteur
- Segregation aleatoire dans les gametes
- 1 allele de chaque parent

### Carre de Punnett
- Outil de prediction
- Visualise toutes les combinaisons
- Calcule probabilites
- Ratios : 3:1 (monohybride), 9:3:3:1 (dihybride)

---

## Auto-evaluation

### Questions rapides

1. Quelle etait la theorie de l'heredite avant Mendel ?
2. Qu'est-ce qu'un allele ?
3. Quelle est la difference entre homozygote et heterozygote ?
4. Peut-on distinguer AA de Aa par simple observation ?
5. Qu'est-ce que le phenotype ?
6. Combien d'alleles recoit un individu de chaque parent ?
7. Qu'est-ce qu'un carre de Punnett ?
8. Quel est le ratio phenotypique d'un croisement Aa x Aa ?
9. Comment s'exprime un allele recessif ?
10. Qu'est-ce qu'un test cross ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. Blending inheritance (heredite par melange)
2. Une forme distincte d'un facteur/gene
3. Homozygote = 2 alleles identiques ; Heterozygote = 2 alleles differents
4. Non, ils ont le meme phenotype (tous deux dominants)
5. La manifestation physique observable des traits
6. 1 allele de chaque parent (total = 2 alleles)
7. Diagramme representant les combinaisons d'alleles possibles
8. 3:1 (75% dominant, 25% recessif)
9. Seulement en deux copies (homozygote recessif aa)
10. Croisement avec homozygote recessif pour determiner le genotype
</details>

---

## Mnemoniques

**Dominant vs Recessif** :
- **D**ominant = **D**emonstrateur (se montre facilement)
- **R**ecessif = **R**eserve (se cache, timide)

**Genotype vs Phenotype** :
- **Geno**type = **Genes** (ADN, invisible)
- **Pheno**type = **Phenomene** (observable)

**Homozygote** : "**Homo** = **Meme**" (2 alleles identiques)

**Heterozygote** : "**Hetero** = **Different**" (2 alleles differents)

**Mendel** : "**M**oines **E**tudient **N**os **D**escendances **E**xperimentalement **L**ogiquement"

**Loi de segregation** : "**S**eparer **E**galement, **G**ametes **R**ecoivent **E**galement, **G**ene **A**leatoirement **T**ransmis, **I**ndividuellement **O**btenu, **N**aissances"

**Ratios** :
- Monohybride (Aa x Aa) : "**3** dominants, **1** recessif"
- Dihybride : "**9**-**3**-**3**-**1**" (comme un numero de telephone : 93-31)

---

## Lien avec la bio-informatique

### Genetique des populations

**Frequences alleliques**
- Calculer la frequence de chaque allele dans une population
- Equilibre de Hardy-Weinberg
- Modelisation de l'evolution

**Formule Hardy-Weinberg**
```
p^2 + 2pq + q^2 = 1

ou :
- p = frequence allele dominant (A)
- q = frequence allele recessif (a)
- p^2 = frequence AA
- 2pq = frequence Aa
- q^2 = frequence aa
```

### Analyse de pedigrees

**Construction d'arbres genealogiques**
- Tracer la transmission des traits
- Identifier les modes d'heredite
- Predire les risques genetiques

**Algorithmes**
- Parcours d'arbres
- Calcul de probabilites
- Inference de genotypes

### GWAS (Genome-Wide Association Studies)

**Principe**
- Associer variants genetiques (SNPs) avec traits/maladies
- Comparer frequences alleliques
- Identifier facteurs de risque

**Bioinformatique**
- Traitement de millions de SNPs
- Tests statistiques (chi-squared)
- Correction tests multiples

### Genetique quantitative

**Traits complexes**
- Influences par plusieurs genes
- Effets additifs
- Modelisation statistique

**Methodes**
- QTL mapping (Quantitative Trait Loci)
- Polygenic risk scores
- Machine learning pour prediction

### Simulation genetique

**Outils**
- Simuler croisements
- Predire distributions phenotypiques
- Modeliser selection naturelle

**Applications**
- Amelioration des plantes/animaux
- Conservation d'especes
- Etude de l'evolution

---

## Exercices pratiques

### Exercice 1 : Carre de Punnett simple
Parents : Aa x Aa
Calculer les proportions de genotypes et phenotypes.

<details>
<summary>Solution</summary>

```
       |  A  |  a  |
    ---+-----+-----+
    A  | AA  | Aa  |
    ---+-----+-----+
    a  | Aa  | aa  |
    ---+-----+-----+
```

Genotypes :
- 25% AA (1/4)
- 50% Aa (2/4)
- 25% aa (1/4)

Phenotypes :
- 75% dominant (AA + Aa)
- 25% recessif (aa)

Ratio genotypique : 1:2:1
Ratio phenotypique : 3:1
</details>

### Exercice 2 : Test cross
Un pois a fleurs violettes. On le croise avec un pois a fleurs blanches (aa).
Resultat : 50% violet, 50% blanc.
Quel est le genotype du pois violet ?

<details>
<summary>Solution</summary>

Le pois violet doit etre **Aa** (heterozygote).

Si c'etait AA :
```
AA x aa â†' 100% Aa (tous violets)
```

Comme on obtient 50/50, c'est :
```
Aa x aa â†' 50% Aa (violet), 50% aa (blanc)
```
</details>

### Exercice 3 : Probabilite
Deux parents heterozygotes (Aa) ont 3 enfants.
Quelle est la probabilite que les 3 soient phenotype dominant ?

<details>
<summary>Solution</summary>

Probabilite d'un enfant dominant : 3/4 (75%)

Probabilite de 3 enfants dominants :
(3/4) × (3/4) × (3/4) = 27/64 ≈ 42%
</details>

### Exercice 4 : Dihybride
Parents : YyRr x YyRr
Quelle proportion de descendants sera vert-lisse (y_R_) ?

<details>
<summary>Solution</summary>

Methode des probabilites independantes :

Vert (yy) : Yy x Yy â†' 1/4 yy
Lisse (R_) : Rr x Rr â†' 3/4 (RR ou Rr)

Vert ET lisse : 1/4 × 3/4 = 3/16

Ou directement dans le ratio 9:3:3:1 :
3/16 (le deuxieme "3")
</details>

### Exercice 5 : Groupe sanguin
Deux parents de groupe A ont un enfant de groupe O.
Quels sont leurs genotypes ?

<details>
<summary>Solution</summary>

Les deux parents doivent etre **AO** (heterozygotes).

Si l'un etait AA, impossible d'avoir enfant OO.

Croisement AO x AO :
```
       |  A  |  O  |
    ---+-----+-----+
    A  | AA  | AO  |
    ---+-----+-----+
    O  | AO  | OO  |
    ---+-----+-----+
```

25% de chance d'avoir un enfant groupe O (OO).
</details>

---

## Problemes Rosalind associes

**Mendel's First Law (IPRB)**
- Calculer probabilites avec loi de Mendel
- Carre de Punnett
- Croisements aleatoires dans une population

**Recurrence Relations (FIB, FIBD)**
- Modeliser croissance de populations
- Avec mutations/mortalite
- Lien avec genetique des populations

**Independent Alleles (LIA)**
- Loi de l'assortiment independant
- Probabilites avec plusieurs facteurs
- Distributions binomiales

---

## Extensions et approfondissements

### Genetique non-mendelienne

**Dominance incomplete**
- Heterozygote = phenotype intermediaire
- Exemple : fleurs roses (RR rouge, rr blanc, Rr rose)
- Ratio 1:2:1 pour phenotypes aussi

**Co-dominance**
- Les deux alleles s'expriment
- Exemple : groupe sanguin AB
- Phenotype distinct pour heterozygote

**Alleles multiples**
- Plus de 2 alleles pour un gene
- Exemple : groupes sanguins ABO (3 alleles)
- Complexifie les croisements

**Genes lies**
- Sur le meme chromosome
- Ne segregent pas independamment
- Necessite carte genetique

**Heredite liee au sexe**
- Genes sur chromosomes X ou Y
- Patterns d'heredite differents
- Exemple : daltonisme, hemophilie

### Genetique moderne

**Epigenetique**
- Modifications sans changement d'ADN
- Methylation, acetylation
- Heritable mais reversible

**Genetique quantitative**
- Traits continus (taille, poids)
- Influences polygenetiques
- Distribution normale

**Genomique**
- Sequencage complet
- Identification de tous les genes
- Analyse a grande echelle

---

## Pour aller plus loin

### Lectures recommandees
- "The Monk in the Garden" (Robin Marantz Henig) - Histoire de Mendel
- "The Gene" (Siddhartha Mukherjee) - Histoire de la genetique
- Papers originaux de Mendel (traduits)

### Ressources en ligne
- PhET Interactive Simulations (genetique)
- Genetic Science Learning Center (Utah)
- Khan Academy (genetique mendelienne)

### Pratique
- Rosalind.info (problemes IPRB, LIA)
- Construire carres de Punnett
- Analyser pedigrees reels

---

**Prochaine fiche** : Code genetique et traduction (ARN â†' Proteine)

---

**Felicitations !** Tu maitrises maintenant :
- Les bases de l'heredite
- Les lois de Mendel
- Le carre de Punnett
- Les concepts de genotype et phenotype

**Ces concepts sont essentiels pour** :
- Genetique des populations
- Analyse de variants
- GWAS et etudes d'association
- Amelioration genetique
- Comprehension de l'evolution
