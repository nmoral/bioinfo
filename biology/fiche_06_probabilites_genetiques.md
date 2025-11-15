# Fiche 06 : Probabilites en genetique

**Date de creation** : 15 novembre 2025  
**Sujet** : Probabilites avancees, tirage sans remise, calculs de croisements

---

## Contexte

Cette fiche approfondit les aspects **mathematiques et probabilistes** de la genetique mendelienne (voir Fiche 05). Elle est essentielle pour resoudre des problemes comme **IPRB** (Mendel's First Law) sur Rosalind.info.

**Prerequis** :
- Fiche 05 : Genetique mendelienne (carre de Punnett, genotypes, phenotypes)
- Notions de probabilites de base

---

## Rappel : Structure d'un probleme de genetique probabiliste

### Question type
> Dans une population de k individus AA, m individus Aa, et n individus aa, si on tire 2 individus au hasard pour les croiser, quelle est la probabilite que leur descendant affiche le phenotype dominant ?

### Decomposition de la solution
```
P(phenotype dominant) = Σ [P(tirer couple i) × P(dominant | couple i)]
                        pour tous les couples possibles
```

**Deux composantes a calculer** :
1. **P(tirer couple i)** : Probabilite de tirer cette paire dans la population
2. **P(dominant | couple i)** : Probabilite que ce croisement donne un dominant (carre de Punnett)

---

## Partie 1 : Probabilites de croisement (Carre de Punnett)

### Rappel des 6 croisements possibles

| Croisement | Genotypes descendants | Phenotypes | P(dominant\|croisement) |
|------------|----------------------|------------|------------------------|
| **AA × AA** | 100% AA | 100% dominant | **1.0** |
| **AA × Aa** | 50% AA, 50% Aa | 100% dominant | **1.0** |
| **AA × aa** | 100% Aa | 100% dominant | **1.0** |
| **Aa × Aa** | 25% AA, 50% Aa, 25% aa | 75% dominant | **0.75** |
| **Aa × aa** | 50% Aa, 50% aa | 50% dominant | **0.5** |
| **aa × aa** | 100% aa | 0% dominant | **0.0** |

### Demonstration : Aa × Aa

**Carre de Punnett** :
```
       |  A  |  a  |
    ---+-----+-----+
    A  | AA  | Aa  |
    ---+-----+-----+
    a  | Aa  | aa  |
    ---+-----+-----+
```

**Comptage** :
- 1 AA (dominant)
- 2 Aa (dominant)
- 1 aa (recessif)

**Probabilite** : 3/4 = 0.75 de phenotype dominant

---

## Partie 2 : Probabilites de tirage (sans remise)

### Principe du tirage sans remise

**Population** :
- k individus AA
- m individus Aa
- n individus aa
- **N = k + m + n** (total)

**Tirage de 2 individus** :
1. **Premier tirage** : N individus disponibles
2. **Deuxieme tirage** : **N-1** individus disponibles (on a retire le premier)

### Regle generale

#### Cas 1 : Tirer 2 individus du MEME genotype

Pour tirer **2 individus de genotype G** parmi nb_G disponibles :

```
P(couple G×G) = (nb_G / N) × ((nb_G - 1) / (N-1))
```

**Explication** :
- Premier tirage : nb_G individus G sur N total → nb_G/N
- Deuxieme tirage : nb_G-1 individus G restants sur N-1 total → (nb_G-1)/(N-1)
- Produit des deux (evenements successifs)

**Exemples** :
- P(AA×AA) = (k/N) × ((k-1)/(N-1))
- P(Aa×Aa) = (m/N) × ((m-1)/(N-1))
- P(aa×aa) = (n/N) × ((n-1)/(N-1))

**Pourquoi pas de ×2 ?**
- Il n'y a qu'une seule facon de tirer "un G puis un autre G"

#### Cas 2 : Tirer 2 individus de genotypes DIFFERENTS

Pour tirer **1 individu G1 et 1 individu G2** (avec G1 ≠ G2) :

```
P(couple G1×G2) = 2 × (nb_G1 × nb_G2) / (N × (N-1))
```

**Explication** :
- **Facon 1** : Tirer G1 en premier, puis G2 → (nb_G1/N) × (nb_G2/(N-1))
- **Facon 2** : Tirer G2 en premier, puis G1 → (nb_G2/N) × (nb_G1/(N-1))
- Les deux facons donnent le meme couple pour la descendance !
- Donc on **additionne** : facon1 + facon2 = 2 × (nb_G1 × nb_G2) / (N × (N-1))

**Exemples** :
- P(AA×Aa) = 2 × (k×m) / (N×(N-1))
- P(AA×aa) = 2 × (k×n) / (N×(N-1))
- P(Aa×aa) = 2 × (m×n) / (N×(N-1))

**Pourquoi ×2 ?**
- Il y a DEUX facons de tirer "un G1 et un G2" (ordre compte pour le tirage)
- Mais pour la descendance, G1×G2 = G2×G1 (meme carre de Punnett)

### Tableau recapitulatif des formules

| Type de couple | Formule P(tirer ce couple) | Facteur ×2 ? |
|----------------|---------------------------|-------------|
| **G × G** (meme) | (nb_G / N) × ((nb_G-1) / (N-1)) | **Non** |
| **G1 × G2** (differents) | 2 × (nb_G1 × nb_G2) / (N × (N-1)) | **Oui** |

---

## Partie 3 : Resolution complete d'un probleme

### Exemple : k=2, m=2, n=2 (N=6)

**Etape 1 : Lister tous les couples possibles**

| # | Croisement | P(dominant\|croisement) | Formule P(tirage) | P(tirage) |
|---|------------|------------------------|-------------------|-----------|
| 1 | AA × AA | 1.0 | (2/6) × (1/5) | 2/30 |
| 2 | AA × Aa | 1.0 | 2 × (2×2) / (6×5) | 8/30 |
| 3 | AA × aa | 1.0 | 2 × (2×2) / (6×5) | 8/30 |
| 4 | Aa × Aa | 0.75 | (2/6) × (1/5) | 2/30 |
| 5 | Aa × aa | 0.5 | 2 × (2×2) / (6×5) | 8/30 |
| 6 | aa × aa | 0.0 | (2/6) × (1/5) | 2/30 |

**Etape 2 : Verifier que Σ P(tirage) = 1**
```
2/30 + 8/30 + 8/30 + 2/30 + 8/30 + 2/30 = 30/30 = 1.0 ✓
```

**Etape 3 : Calculer la somme ponderee**
```
P(dominant) = (2/30 × 1.0) + (8/30 × 1.0) + (8/30 × 1.0) 
            + (2/30 × 0.75) + (8/30 × 0.5) + (2/30 × 0.0)
            
            = 2/30 + 8/30 + 8/30 + 1.5/30 + 4/30 + 0
            
            = 23.5/30
            
            = 0.78333...
```

**Reponse** : 0.78333 (ou 0.783333...)

---

## Partie 4 : Cas particuliers et pieges

### Piege 1 : Oublier le ×2 pour couples differents

**Erreur courante** :
```
P(AA×Aa) = (k/N) × (m/(N-1))  ❌ FAUX
```

**Correct** :
```
P(AA×Aa) = 2 × (k×m) / (N×(N-1))  ✓
```

**Pourquoi ?** Tu peux tirer AA puis Aa OU Aa puis AA !

### Piege 2 : Mettre ×2 pour couples identiques

**Erreur courante** :
```
P(AA×AA) = 2 × (k/N) × ((k-1)/(N-1))  ❌ FAUX
```

**Correct** :
```
P(AA×AA) = (k/N) × ((k-1)/(N-1))  ✓
```

**Pourquoi ?** Il n'y a qu'une seule facon de tirer "2 individus AA"

### Piege 3 : Ne pas soustraire 1 au deuxieme tirage

**Erreur courante** :
```
P(AA×AA) = (k/N) × (k/N)  ❌ FAUX
```

**Correct** :
```
P(AA×AA) = (k/N) × ((k-1)/(N-1))  ✓
```

**Pourquoi ?** Tirage SANS remise ! Le premier individu n'est plus disponible.

### Cas limite : Population homogene

**Exemple 1** : Que des AA (k>0, m=0, n=0)
```
Seul couple possible : AA × AA
P(dominant) = 1.0 (toujours dominant)
```

**Exemple 2** : Que des aa (k=0, m=0, n>0)
```
Seul couple possible : aa × aa
P(dominant) = 0.0 (jamais dominant)
```

**Exemple 3** : Que des Aa (k=0, m>0, n=0)
```
Seul couple possible : Aa × Aa
P(dominant) = 0.75 (ratio 3:1)
```

---

## Partie 5 : Algorithme de resolution

### Pseudo-code

```
fonction probabilite_dominant(k, m, n):
    N = k + m + n
    
    # Initialiser resultat
    prob_total = 0.0
    
    # Cas 1 : AA × AA
    prob_tirage = (k/N) × ((k-1)/(N-1))
    prob_dominant = 1.0
    prob_total += prob_tirage × prob_dominant
    
    # Cas 2 : AA × Aa
    prob_tirage = 2 × (k×m) / (N×(N-1))
    prob_dominant = 1.0
    prob_total += prob_tirage × prob_dominant
    
    # Cas 3 : AA × aa
    prob_tirage = 2 × (k×n) / (N×(N-1))
    prob_dominant = 1.0
    prob_total += prob_tirage × prob_dominant
    
    # Cas 4 : Aa × Aa
    prob_tirage = (m/N) × ((m-1)/(N-1))
    prob_dominant = 0.75
    prob_total += prob_tirage × prob_dominant
    
    # Cas 5 : Aa × aa
    prob_tirage = 2 × (m×n) / (N×(N-1))
    prob_dominant = 0.5
    prob_total += prob_tirage × prob_dominant
    
    # Cas 6 : aa × aa
    prob_tirage = (n/N) × ((n-1)/(N-1))
    prob_dominant = 0.0
    prob_total += prob_tirage × prob_dominant
    
    retourner prob_total
```

### Optimisation : Simplification algebrique

Tu peux factoriser pour eviter de repeter N×(N-1) :

```
P(dominant) = 1/(N×(N-1)) × [
    k(k-1)×1.0 + 2km×1.0 + 2kn×1.0 + m(m-1)×0.75 + 2mn×0.5 + n(n-1)×0.0
]
```

Simplifie encore :
```
P(dominant) = [k(k-1) + 2km + 2kn + 0.75m(m-1) + mn] / (N×(N-1))
```

---

## Partie 6 : Verification et tests

### Strategie de verification

**1. Verification des probabilites de tirage**
```
Σ P(tirer couple i) doit = 1.0
```

Si ce n'est pas le cas, tu as oublie un couple ou mal compte !

**2. Tests de coherence**

**Test A** : Que des dominants (k>0, m=0, n=0)
```
P(dominant) doit = 1.0
```

**Test B** : Que des recessifs (k=0, m=0, n>0)
```
P(dominant) doit = 0.0
```

**Test C** : Que des heterozygotes (k=0, m>0, n=0)
```
P(dominant) doit = 0.75
```

### Cas de tests IPRB

| k | m | n | N | P(dominant) | Note |
|---|---|---|---|-------------|------|
| 2 | 2 | 2 | 6 | 0.78333 | Exemple Rosalind |
| 2 | 0 | 0 | 2 | 1.0 | Que des AA |
| 0 | 0 | 2 | 2 | 0.0 | Que des aa |
| 0 | 2 | 0 | 2 | 0.75 | Que des Aa |
| 1 | 1 | 1 | 3 | 0.66667 | Un de chaque |
| 2 | 0 | 3 | 5 | 0.7 | AA et aa |
| 0 | 3 | 2 | 5 | 0.6 | Aa et aa |

---

## Partie 7 : Generalisation et extensions

### Extension 1 : Plus de 2 individus

**Question** : Si on croise 3 individus (plantes simultanement), quelle est la probabilite ?

**Approche** :
- Meme principe mais plus de combinaisons
- Tirage sans remise sur 3 positions
- Calcul plus complexe

### Extension 2 : Plusieurs generations

**Question** : Quelle est la probabilite qu'un arriere-petit-enfant soit dominant ?

**Approche** :
- Probabilites conditionnelles enchainees
- Arbre de probabilites
- Chaque generation depend de la precedente

### Extension 3 : Selection naturelle

**Question** : Si les recessifs ont un desavantage de survie, comment evolue la population ?

**Approche** :
- Equations de Hardy-Weinberg modifiees
- Coefficients de selection
- Dynamique des populations

---

## Points cles a retenir

### Formules essentielles

**Meme genotype** :
```
P(G×G) = (nb_G / N) × ((nb_G-1) / (N-1))
```

**Genotypes differents** :
```
P(G1×G2) = 2 × (nb_G1 × nb_G2) / (N × (N-1))
```

**Probabilite totale** :
```
P(dominant) = Σ [P(tirer couple) × P(dominant|couple)]
```

### Checklist de resolution

- [ ] Identifier k, m, n et calculer N
- [ ] Lister les 6 couples possibles
- [ ] Pour chaque couple :
  - [ ] Calculer P(tirer ce couple)
  - [ ] Determiner P(dominant|couple) avec carre de Punnett
  - [ ] Calculer la contribution
- [ ] Verifier que Σ P(tirage) = 1.0
- [ ] Sommer toutes les contributions
- [ ] Verifier avec cas limites

### Pieges a eviter

- ❌ Oublier le ×2 pour couples differents
- ❌ Mettre ×2 pour couples identiques
- ❌ Oublier le -1 au denominateur (tirage sans remise)
- ❌ Oublier le -1 au numerateur (meme genotype)
- ❌ Ne pas verifier que Σ P(tirage) = 1.0

---

## Auto-evaluation

### Questions rapides

1. Quelle est la formule pour P(AA×AA) avec k individus AA et N total ?
2. Pourquoi y a-t-il un facteur 2 pour P(AA×Aa) ?
3. Quelle est la probabilite qu'un croisement Aa×Aa donne un dominant ?
4. Comment verifier que ton calcul de probabilites de tirage est correct ?
5. Si k=0, m=0, n=5, quelle est P(dominant) ?
6. Si k=3, m=0, n=0, quelle est P(dominant) ?
7. Combien y a-t-il de types de couples possibles avec 3 genotypes ?
8. Que signifie "tirage sans remise" ?
9. Pourquoi P(AA×Aa) ≠ P(AA×AA) meme si les deux donnent 100% dominant ?
10. Quelle est la contribution du couple aa×aa ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. P(AA×AA) = (k/N) × ((k-1)/(N-1))
2. Car on peut tirer AA puis Aa OU Aa puis AA (deux ordres possibles)
3. 0.75 (ratio 3:1 du carre de Punnett)
4. Verifier que la somme de toutes les P(tirage) = 1.0
5. 0.0 (que des recessifs)
6. 1.0 (que des dominants)
7. 6 types (AA×AA, AA×Aa, AA×aa, Aa×Aa, Aa×aa, aa×aa)
8. Le premier individu tire n'est pas remis dans la population
9. Parce que la probabilite de TIRER ces couples est differente
10. 0 (car aa×aa donne 0% de dominants)
</details>

---

## Mnemoniques

**Meme genotype** : "**M**oins **U**n" (nb_G - 1 au numerateur)

**Genotypes differents** : "**D**ouble **O**rdre" (×2 car deux ordres possibles)

**Tirage sans remise** : "**S**ans **R**etour, **M**oins **U**n" (N-1)

**Verification** : "**S**omme = **U**n" (toutes les probabilites = 1.0)

**6 couples** : "**3** au carre moins **3**" (3×3 - 3 = 6, car on enleve les doublons)

---

## Lien avec la bio-informatique

### GWAS (Genome-Wide Association Studies)

**Application** :
- Calculer la frequence attendue de genotypes dans une population
- Comparer frequences observees vs attendues (test chi-squared)
- Identifier deviations de l'equilibre de Hardy-Weinberg

### Genetique des populations

**Modeles mathematiques** :
- Evolution des frequences alleliques
- Effet de la selection, derive, migration
- Predictions a long terme

### Algorithmes d'inference

**Problemes** :
- Deduire genotypes parentaux a partir de descendants
- Calculer probabilites de pedigrees
- Maximum de vraisemblance (likelihood)

### Simulation genetique

**Outils** :
- Simuler croisements a grande echelle
- Modeliser populations avec regles mendeliennes
- Valider hypotheses evolutives

---

## Exercices pratiques

### Exercice 1 : Calcul simple
k=1, m=2, n=1 (N=4)
Calculer P(dominant).

<details>
<summary>Solution</summary>

| Couple | P(tirage) | P(dom\|couple) | Contribution |
|--------|-----------|----------------|--------------|
| AA×AA | 0 | 1.0 | 0 |
| AA×Aa | 2×(1×2)/(4×3) = 4/12 | 1.0 | 4/12 |
| AA×aa | 2×(1×1)/(4×3) = 2/12 | 1.0 | 2/12 |
| Aa×Aa | (2/4)×(1/3) = 2/12 | 0.75 | 1.5/12 |
| Aa×aa | 2×(2×1)/(4×3) = 4/12 | 0.5 | 2/12 |
| aa×aa | 0 | 0.0 | 0 |

Total = (4+2+1.5+2)/12 = 9.5/12 ≈ 0.79167
</details>

### Exercice 2 : Verification
k=3, m=2, n=1 (N=6)
Calculer Σ P(tirage) et verifier = 1.0

<details>
<summary>Solution</summary>

| Couple | P(tirage) |
|--------|-----------|
| AA×AA | (3/6)×(2/5) = 6/30 |
| AA×Aa | 2×(3×2)/(6×5) = 12/30 |
| AA×aa | 2×(3×1)/(6×5) = 6/30 |
| Aa×Aa | (2/6)×(1/5) = 2/30 |
| Aa×aa | 2×(2×1)/(6×5) = 4/30 |
| aa×aa | 0 |

Somme = (6+12+6+2+4+0)/30 = 30/30 = 1.0 ✓
</details>

### Exercice 3 : Cas limite
k=0, m=5, n=0
Que vaut P(dominant) ?

<details>
<summary>Solution</summary>

Seul couple possible : Aa × Aa
P(tirage) = 1.0
P(dominant|Aa×Aa) = 0.75

Reponse : 0.75
</details>

---

## Problemes Rosalind associes

**Mendel's First Law (IPRB)**
- Calculer probabilite de phenotype dominant
- Input : k m n (nombre de chaque genotype)
- Output : probabilite (5+ decimales)

**Independent Alleles (LIA)**
- Extension avec plusieurs genes
- Loi de l'assortiment independant
- Distributions binomiales

**Calculating Expected Offspring (IEV)**
- Nombre attendu de descendants dominants
- Esperance mathematique
- Ponderation par probabilites

---

## Pour aller plus loin

### Lectures recommandees
- "Introduction to Probability" (Grinstead & Snell) - Chapitre sur les probabilites conditionnelles
- "Population Genetics: A Concise Guide" (Gillespie) - Modeles mathematiques
- "Bioinformatics Algorithms" (Compeau & Pevzner) - Chapitre sur la genetique

### Ressources en ligne
- Khan Academy : Probabilites et genetique
- MIT OpenCourseWare : Genetics and Probability
- Rosalind.info : Problemes IPRB, LIA, IEV
- Wolfram MathWorld : Conditional Probability

### Exercices pratiques
- Resoudre tous les variants de IPRB
- Creer son propre generateur de cas de test
- Implementer le solver en Python
- Visualiser les probabilites avec matplotlib
- Simuler des croisements avec Monte Carlo

### Approfondissements mathematiques
- Chaînes de Markov pour generations successives
- Esperance et variance du nombre de descendants
- Tests statistiques (chi-squared, exacte de Fisher)
- Modelisation stochastique de populations

---

**Prochaine fiche** : Code genetique et traduction (ARN → Proteine)

---

**Felicitations !** Tu maitrises maintenant :
- Les probabilites de tirage sans remise
- Le calcul de probabilites de croisements
- La resolution complete de problemes IPRB
- Les pieges courants et comment les eviter

**Ces competences sont essentielles pour** :
- Resoudre les problemes Rosalind de genetique
- Comprendre la genetique des populations
- Modeliser l'evolution des frequences alleliques
- Analyser des donnees GWAS
- Developper des outils de simulation genetique
