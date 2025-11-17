# Fiche 08 : Theoreme de Bayes

**Date de creation** : 16 novembre 2025  
**Sujet** : Probabilites conditionnelles, theoreme de Bayes, applications en bio-informatique

---

## Pourquoi Bayes en bio-informatique ?

### Applications majeures

Le theoreme de Bayes est **fondamental** en bio-informatique moderne :

**Inference phylogenetique** :
- Reconstruction d'arbres evolutifs
- Methodes bayesiennes (BEAST, MrBayes)
- Estimation de temps de divergence

**Annotation de genomes** :
- Prediction de genes
- Classification de sequences
- Identification de motifs

**Tests diagnostiques** :
- Interpretation de tests genetiques
- Probabilite de maladie genetique
- Risque de mutation pathogene

**Machine Learning** :
- Classificateurs bayesiens naifs
- Reseaux bayesiens
- Filtres anti-spam (historiquement)

---

## Prerequis : Probabilites de base

### Notation

**P(A)** : Probabilite de l'evenement A
- Exemple : P(mutation) = 0.01 (1% de chance de mutation)

**P(A et B)** ou **P(A ∩ B)** : Probabilite que A ET B se produisent
- Exemple : P(mutation ET deletere) = probabilite d'une mutation deletere

**P(A ou B)** ou **P(A ∪ B)** : Probabilite que A OU B se produise
- Exemple : P(type A OU type B) = probabilite groupe sanguin A ou B

**P(non A)** ou **P(A')** : Probabilite que A ne se produise PAS
- Regle : P(A) + P(non A) = 1
- Exemple : P(non mutation) = 1 - P(mutation) = 0.99

### Evenements independants

**Definition** :
Deux evenements A et B sont independants si l'occurrence de l'un n'affecte pas la probabilite de l'autre.

**Regle de multiplication** :
```
P(A et B) = P(A) × P(B)
```

**Exemple genetique** :
- P(mutation gene 1) = 0.01
- P(mutation gene 2) = 0.01
- Si independants : P(mutation gene 1 ET gene 2) = 0.01 × 0.01 = 0.0001

**Contre-exemple (NON independants)** :
- P(avoir cheveux bruns) et P(avoir yeux bruns)
- Ces traits sont correles (genes lies)
- Ne PAS multiplier directement !

---

## Probabilites conditionnelles

### Definition

**P(A|B)** : Probabilite de A **sachant que** B s'est produit
- Se lit : "P de A sachant B" ou "P de A conditionnel a B"
- B est deja observe/connu

**Formule fondamentale** :
```
P(A|B) = P(A et B) / P(B)
```

(A condition que P(B) > 0)

### Interpretation

**Signification** :
- On restreint notre univers aux cas ou B est vrai
- On calcule la proportion de A parmi ces cas

**Exemple visuel** :
```
Tous les cas possibles :
[===== B =====][= non B =]
     |
 [A et B]
     
P(A|B) = zone "A et B" / zone "B"
```

### Exemples biologiques

**Exemple 1 : Mutations et phenotype**
- A = "phenotype anormal"
- B = "mutation presente"
- P(A|B) = probabilite d'avoir phenotype anormal SI mutation presente

**Exemple 2 : Tests genetiques**
- A = "vraiment malade"
- B = "test positif"
- P(A|B) = probabilite d'etre vraiment malade SI test positif
- **C'est ce qu'on veut savoir !**

**Exemple 3 : Sequencage**
- A = "vraie mutation (variant)"
- B = "variant appele par le logiciel"
- P(A|B) = probabilite que ce soit une vraie mutation SI detectee

### Regle de la chaine

**Pour 2 evenements** :
```
P(A et B) = P(A|B) × P(B)
         = P(B|A) × P(A)
```

**Pour 3 evenements** :
```
P(A et B et C) = P(A) × P(B|A) × P(C|A et B)
```

**Application genetique** :
Probabilite d'une sequence specifique d'evenements evolutifs.

---

## Le theoreme de Bayes

### Formulation

**Version simple** :
```
P(A|B) = P(B|A) × P(A) / P(B)
```

**Version avec complement** :
```
P(A|B) = P(B|A) × P(A) / [P(B|A) × P(A) + P(B|non A) × P(non A)]
```

### Vocabulaire

**P(A)** : **Probabilite a priori** (prior)
- Ce qu'on sait AVANT d'observer B
- Notre connaissance initiale
- Exemple : prevalence d'une maladie dans la population

**P(B|A)** : **Vraisemblance** (likelihood)
- Probabilite d'observer B si A est vrai
- Exemple : sensibilite d'un test (P(test+|malade))

**P(A|B)** : **Probabilite a posteriori** (posterior)
- Ce qu'on sait APRES avoir observe B
- Notre connaissance mise a jour
- Exemple : probabilite d'etre malade si test positif

**P(B)** : **Evidence** (ou probabilite marginale)
- Probabilite totale d'observer B
- Normalisation

### Interpretation intuitive

**Le theoreme de Bayes permet de "retourner" une probabilite conditionnelle** :
- On connait souvent P(B|A) (facile a mesurer)
- On veut connaitre P(A|B) (ce qui nous interesse vraiment)

**Exemple medical** :
- **Facile** : P(test+|malade) = "Si quelqu'un est malade, quelle est la chance que le test soit positif ?"
- **Difficile mais utile** : P(malade|test+) = "Si le test est positif, quelle est la chance d'etre vraiment malade ?"

Bayes nous permet de passer de l'un a l'autre !

---

## Exemple detaille : Test genetique

### Contexte

**Maladie genetique rare** :
- Prevalence : 1 personne sur 10,000
- P(malade) = 0.0001
- P(non malade) = 0.9999

**Test disponible** :
- Sensibilite : 99% (detecte 99% des malades)
  - P(test+|malade) = 0.99
- Specificite : 99% (99% des non-malades testent negatif)
  - P(test-|non malade) = 0.99
  - Donc P(test+|non malade) = 0.01 (1% de faux positifs)

### Question

**Une personne teste positive. Quelle est la probabilite qu'elle soit vraiment malade ?**

On cherche : P(malade|test+)

### Solution etape par etape

**Etape 1 : Identifier les donnees**
- P(malade) = 0.0001
- P(non malade) = 0.9999
- P(test+|malade) = 0.99
- P(test+|non malade) = 0.01

**Etape 2 : Appliquer Bayes**
```
P(malade|test+) = P(test+|malade) × P(malade) / P(test+)
```

**Etape 3 : Calculer P(test+)**
```
P(test+) = P(test+|malade) × P(malade) + P(test+|non malade) × P(non malade)
         = 0.99 × 0.0001 + 0.01 × 0.9999
         = 0.000099 + 0.009999
         = 0.010098
```

**Etape 4 : Calculer la reponse**
```
P(malade|test+) = (0.99 × 0.0001) / 0.010098
                = 0.000099 / 0.010098
                = 0.0098
                ≈ 0.98% ou environ 1%
```

### Resultat surprenant !

**Seulement ~1% de chance d'etre vraiment malade malgre un test positif !**

**Pourquoi ?**
- La maladie est tres rare (1/10,000)
- Meme avec 99% de specificite, il y a beaucoup de faux positifs dans une grande population
- Sur 10,000 personnes :
  - 1 malade → 0.99 teste positif (vrai positif)
  - 9,999 non malades → 99.99 testent positif (faux positifs)
  - Ratio vrai positifs / tous les positifs ≈ 1/100

**Lecon importante** :
La prevalence (probabilite a priori) compte enormement dans l'interpretation des tests !

---

## Calculs pratiques

### Tableau de contingence

**Outil utile pour visualiser et calculer** :

**Exemple du test genetique sur 10,000 personnes** :

|                  | Malade | Non malade | Total |
|------------------|--------|------------|-------|
| **Test +**       | 0.99   | 99.99      | 100.98 |
| **Test -**       | 0.01   | 9899.01    | 9899.02 |
| **Total**        | 1      | 9999       | 10000 |

**Lecture** :
- P(malade|test+) = 0.99 / 100.98 ≈ 0.0098

### Formule alternative

**Odds ratio (rapport de cotes)** :

**Avant le test** :
```
Odds(malade) = P(malade) / P(non malade) = 0.0001 / 0.9999 ≈ 1:10000
```

**Ratio de vraisemblance** :
```
LR+ = P(test+|malade) / P(test+|non malade) = 0.99 / 0.01 = 99
```

**Apres le test** :
```
Odds(malade|test+) = Odds(malade) × LR+ = (1/10000) × 99 = 99/10000 ≈ 1:101
```

**Conversion en probabilite** :
```
P(malade|test+) = 99 / (99 + 10000) ≈ 0.0098
```

---

## Applications en bio-informatique

### 1. Inference phylogenetique bayesienne

**Probleme** :
Reconstruire l'arbre evolutif le plus probable etant donnees des sequences.

**Approche bayesienne** :
```
P(Arbre|Sequences) = P(Sequences|Arbre) × P(Arbre) / P(Sequences)
```

**Elements** :
- **P(Arbre)** : prior sur les arbres (topologie, longueurs de branches)
- **P(Sequences|Arbre)** : vraisemblance (modeles d'evolution)
- **P(Arbre|Sequences)** : distribution a posteriori (ce qu'on cherche)

**Logiciels** :
- BEAST (Bayesian Evolutionary Analysis Sampling Trees)
- MrBayes
- PhyloBayes

**Avantages** :
- Incorporation de connaissances a priori
- Quantification de l'incertitude
- Estimation de parametres evolutifs

### 2. Annotation de genes

**Probleme** :
Determiner si une region d'ADN est un gene ou non.

**Approche bayesienne** :
```
P(gene|sequence) = P(sequence|gene) × P(gene) / P(sequence)
```

**Modeles** :
- HMM (Hidden Markov Models) bayesiens
- Prediction basee sur composition en codons
- Utilisation de bases de donnees de genes connus

**Logiciels** :
- GeneMark (approche bayesienne)
- Glimmer
- Prodigal

### 3. Variant calling

**Probleme** :
Determiner si une position du genome contient vraiment un variant.

**Approche bayesienne** :
```
P(variant|reads) = P(reads|variant) × P(variant) / P(reads)
```

**Prior** :
- Frequence des variants dans la population
- Taux de mutation connu

**Vraisemblance** :
- Qualite des reads
- Couverture
- Biais de sequencage

**Logiciels** :
- GATK (Genome Analysis Toolkit)
- FreeBayes
- SAMtools bcftools

### 4. Classificateurs bayesiens

**Naive Bayes classifier** :
Algorithme de classification simple et efficace.

**Applications** :
- Classification de sequences proteiques
- Prediction de structure secondaire
- Detection de spam (historique)
- Prediction de sites d'epissage

**Principe** :
```
P(Classe|Features) ∝ P(Features|Classe) × P(Classe)
```

Assume independence des features (d'ou "naive").

### 5. Alignement de sequences

**Approche probabiliste** :
Au lieu de scores fixes, on peut utiliser des probabilites.

**Pair HMM (Hidden Markov Model)** :
- Modele probabiliste d'alignement
- P(alignement|sequences) via Bayes
- Base de logiciels modernes (HMMER)

### 6. Tests de paternite

**Probleme** :
Determiner si un homme est le pere biologique d'un enfant.

**Approche** :
```
P(pere|genotypes) = P(genotypes|pere) × P(pere) / P(genotypes)
```

**Calcul** :
- Prior : 0.5 (suppose ou non)
- Vraisemblance : transmission des alleles
- Posterior : probabilite de paternite

**Utilise** :
- Tests ADN commerciaux
- Medecine legale
- Recherche de genealogie

---

## Reseaux bayesiens

### Definition

**Graphe oriente acyclique** representant des dependances probabilistes entre variables.

**Structure** :
- **Noeuds** : variables aleatoires
- **Aretes** : dependances causales
- **Probabilites conditionnelles** : P(enfant|parents)

### Exemple genetique simple

```
    [Genotype Parent 1]     [Genotype Parent 2]
              \                    /
               \                  /
                \                /
              [Genotype Enfant]
                      |
                      |
                [Phenotype Enfant]
```

**Calculs** :
- P(Enfant|Parent1, Parent2) : lois de Mendel
- P(Phenotype|Genotype) : dominance, penetrance

### Applications

**Genetique des populations** :
- Inference de structure de population
- Detection de selection
- Flux de genes

**Biologie des systemes** :
- Reseaux de regulation genetique
- Voies metaboliques
- Interactions proteines

**Medecine personnalisee** :
- Prediction de risque de maladie
- Reponse aux medicaments
- Diagnostic differentiel

---

## Statistiques bayesiennes vs frequentistes

### Approche frequentiste

**Philosophie** :
- Les parametres sont fixes (mais inconnus)
- Les donnees sont aleatoires
- Probabilite = frequence a long terme

**Methodes** :
- Tests d'hypotheses (p-value)
- Intervalles de confiance
- Maximum de vraisemblance

**Exemple** :
"Si on repete l'experience 100 fois, le vrai parametre sera dans l'intervalle 95 fois"

### Approche bayesienne

**Philosophie** :
- Les parametres sont aleatoires
- On a des croyances (prior) qu'on met a jour
- Probabilite = degre de certitude

**Methodes** :
- Inference posterieure
- Intervalles de credibilite
- MAP (Maximum a Posteriori)

**Exemple** :
"Il y a 95% de chance que le vrai parametre soit dans cet intervalle"

### Comparaison

| Aspect | Frequentiste | Bayesien |
|--------|--------------|----------|
| **Parametres** | Fixes | Aleatoires |
| **Prior** | Non | Oui |
| **Interpretation** | Frequence long terme | Degre de croyance |
| **Petits echantillons** | Problematique | Meilleur avec prior |
| **Calcul** | Souvent simple | Souvent complexe (MCMC) |
| **Incorporation connaissance** | Difficile | Naturel |

**En bio-informatique moderne** :
- Les deux approches sont utilisees
- Bayesien de plus en plus populaire
- Surtout pour problemes complexes (phylogenie, genomique)

---

## Points cles a retenir

### Probabilites conditionnelles
- P(A|B) = probabilite de A sachant B
- P(A|B) = P(A et B) / P(B)
- Permet de restreindre l'univers des possibles

### Theoreme de Bayes
- P(A|B) = P(B|A) × P(A) / P(B)
- Permet de "retourner" les conditionnelles
- Mise a jour de croyances avec nouvelles donnees

### Vocabulaire
- **Prior** : connaissance initiale P(A)
- **Vraisemblance** : P(B|A)
- **Posterior** : connaissance mise a jour P(A|B)
- **Evidence** : P(B)

### Pieges courants
- Ignorer la prevalence (prior)
- Confondre P(A|B) et P(B|A)
- Oublier le denominateur P(B)
- Supposer independence a tort

### Applications
- Tests diagnostiques
- Phylogenie bayesienne
- Annotation de genomes
- Variant calling
- Machine learning

---

## Auto-evaluation

### Questions rapides

1. Qu'est-ce qu'une probabilite conditionnelle ?
2. Quelle est la difference entre P(A|B) et P(B|A) ?
3. Qu'est-ce qu'un "prior" dans le theoreme de Bayes ?
4. Pourquoi un test positif ne signifie pas toujours qu'on est malade ?
5. Qu'est-ce que la vraisemblance ?
6. Comment calcule-t-on P(B) dans le theoreme de Bayes ?
7. Quand utilise-t-on des methodes bayesiennes en phylogenie ?
8. Qu'est-ce qu'un reseau bayesien ?
9. Quelle est la difference entre approche bayesienne et frequentiste ?
10. Cite 3 applications de Bayes en bio-informatique.

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. Probabilite d'un evenement sachant qu'un autre s'est produit
2. P(A|B) = A sachant B ; P(B|A) = B sachant A (conditionnelles inverses)
3. La probabilite initiale avant d'observer les donnees
4. Car la prevalence peut etre faible, creant beaucoup de faux positifs
5. P(donnees|hypothese) - probabilite d'observer les donnees si l'hypothese est vraie
6. P(B) = P(B|A)×P(A) + P(B|non A)×P(non A) (loi des probabilites totales)
7. Pour reconstruire des arbres evolutifs en incorporant incertitude et priors
8. Graphe representant dependances probabilistes entre variables
9. Bayesien : parametres aleatoires, use prior ; Frequentiste : parametres fixes
10. Phylogenie, annotation genes, variant calling, tests diagnostiques, classification
</details>

---

## Mnemoniques

**Theoreme de Bayes** : "**P**osterior = **L**ikelihood × **P**rior / **E**vidence"
- **P** - **L** - **P** - **E**

**Retourner conditionnel** : "**B**ayes **R**etourne" 
- P(A|B) → P(B|A)

**Elements de Bayes** : "**P**riere **V**oir **P**osterieurs **E**vidences"
- Prior, Vraisemblance, Posterior, Evidence

**Test diagnostique** : "**P**revalence **M**atte **P**lus" (Prevalence Matters a lot Plus)

**Faux positifs** : "**R**are maladie, **B**eaucoup faux **P**ositifs"

---

## Exercices pratiques

### Exercice 1 : Probabilite conditionnelle simple
Dans une population :
- 30% ont les yeux bleus
- 20% ont les cheveux blonds
- 10% ont les deux

Quelle est P(yeux bleus | cheveux blonds) ?

**Indice** : Utilise la formule P(A|B) = P(A et B) / P(B).

### Exercice 2 : Test medical
Un test detecte une maladie avec :
- Sensibilite : 95% (P(test+|malade) = 0.95)
- Specificite : 90% (P(test-|non malade) = 0.90)
- Prevalence : 2% (P(malade) = 0.02)

Si une personne teste positive, quelle est P(malade|test+) ?

**Indice** : Commence par calculer P(test+).

### Exercice 3 : Genes et traits
Pour un trait recessif rare :
- P(homozygote recessif) = 0.01
- P(trait | homozygote recessif) = 1.0
- P(trait | non homozygote recessif) = 0.0

Une personne a le trait. Quelle est P(homozygote recessif | trait) ?

**Indice** : Si le trait implique necessairement le genotype, pense aux probabilites.

### Exercice 4 : Sequencage
Un variant caller a :
- P(detect|vrai variant) = 0.98
- P(detect|faux positif) = 0.05
- P(vrai variant) = 0.001

Si un variant est detecte, quelle est P(vrai variant|detecte) ?

**Indice** : Application directe de Bayes avec un prior tres faible.

### Exercice 5 : Arbre bayesien
Soit le reseau :
```
[A] → [B]
```
Avec :
- P(A) = 0.3
- P(B|A) = 0.8
- P(B|non A) = 0.2

Calculer P(A|B).

**Indice** : Utilise Bayes. N'oublie pas de calculer P(B) d'abord.

### Cas de tests (avec reponses attendues)

**Test 1 - Exercice 1** :
- Input : P(yeux bleus) = 0.3, P(blonds) = 0.2, P(les deux) = 0.1
- Output attendu : P(yeux bleus|blonds) = 0.1 / 0.2 = 0.5

**Test 2 - Exercice 2** :
- Input : Sensibilite = 0.95, Specificite = 0.90, Prevalence = 0.02
- Output attendu : P(malade|test+) ≈ 0.162 (16.2%)

**Test 3 - Exercice 3** :
- Input : P(aa) = 0.01, P(trait|aa) = 1.0, P(trait|non aa) = 0.0
- Output attendu : P(aa|trait) = 1.0 (100%)

**Test 4 - Exercice 4** :
- Input : P(detect|vrai) = 0.98, P(detect|faux) = 0.05, P(vrai) = 0.001
- Output attendu : P(vrai|detect) ≈ 0.0193 (1.93%)

**Test 5 - Exercice 5** :
- Input : P(A) = 0.3, P(B|A) = 0.8, P(B|non A) = 0.2
- Output attendu : P(A|B) = 0.6

**Test 6 - Test genetique classique** :
- Input : Prevalence = 0.0001, Sensibilite = 0.99, Specificite = 0.99
- Output attendu : P(malade|test+) ≈ 0.0098 (environ 1%)

**Test 7 - Coin biaise** :
- Input : P(biaise) = 0.01, P(face|biaise) = 0.9, P(face|normal) = 0.5
- Observation : 3 faces consecutives
- Output attendu : P(biaise|3 faces) ≈ 0.014

---

## Pour aller plus loin

### Lectures recommandees

**Livres d'introduction** :
- "Bayesian Statistics the Fun Way" (Will Kurt)
  - Approche accessible et ludique
  - Pas de prerequis mathematiques lourds
  
- "Think Bayes" (Allen B. Downey)
  - Approche computationnelle avec Python
  - Gratuit en ligne
  - Exemples concrets
  
- "Bayes' Theorem Examples" (Daniel Lakens)
  - Court et pratique
  - Focus sur applications

**Livres avances** :
- "Bayesian Data Analysis" (Gelman et al.)
  - Reference academique
  - Tres complet
  - Mathematiquement rigoureux
  
- "Statistical Rethinking" (Richard McElreath)
  - Approche moderne
  - Code en R et Stan
  - Excellent pour sciences naturelles
  
- "Doing Bayesian Data Analysis" (John Kruschke)
  - Pedagogique
  - "Puppies book"
  - Pas de prerequis bayesiens

**Bio-informatique specifique** :
- "Biological Sequence Analysis" (Durbin et al.)
  - Chapitre sur methodes probabilistes
  - HMM et modeles bayesiens
  
- "Computational Phylogenetics" (Felsenstein)
  - Inference phylogenetique bayesienne
  - Modeles d'evolution
  
- "Bioinformatics: The Machine Learning Approach" (Baxevanis & Ouellette)
  - Classifieurs bayesiens
  - Applications pratiques

**Articles fondateurs** :
- Bayes, T. (1763) "An Essay towards solving a Problem in the Doctrine of Chances"
  - Article original (posthume)
  
- Zhu et al. (2001) "Bayesian adaptive sequence alignment algorithms"
  - Application a l'alignement
  
- Huelsenbeck & Ronquist (2001) "MrBayes: Bayesian inference of phylogenetic trees"
  - Introduction de MrBayes
  
- Nielsen & Wakeley (2001) "Distinguishing migration from isolation"
  - Inference bayesienne en genetique des populations

### Ressources en ligne

**Cours et tutoriels** :
- **3Blue1Brown - Bayes theorem** (YouTube)
  - Visualisation excellente
  - Intuition geometrique
  - https://www.youtube.com/watch?v=HZGCoVF3YvM
  
- **Khan Academy - Bayesian inference**
  - Serie de videos
  - Exercices interactifs
  
- **Seeing Theory - Bayesian inference**
  - Visualisations interactives
  - https://seeing-theory.brown.edu
  
- **Count Bayesie blog**
  - Articles accessibles
  - Exemples concrets
  - Intuition avant formalisme

**Cours universitaires** :
- **MIT 6.041 - Probabilistic Systems Analysis**
  - OCW gratuit
  - Videos et notes
  
- **Stanford CS228 - Probabilistic Graphical Models**
  - Reseaux bayesiens
  - Materiel en ligne

**Cours bio-informatique** :
- **Coursera - Bioinformatics Specialization**
  - Module sur probabilites
  - Applications pratiques
  
- **Molecular Evolution (Phylogenetics course)**
  - Workshop Woods Hole
  - Materiel gratuit

**Outils interactifs** :
- **Bayes Theorem Calculator** (plusieurs disponibles)
  - Calculs automatises
  - Visualisations
  
- **Probability distributions visualizer**
  - Comprendre distributions
  - Prior vs posterior

**Logiciels** :
- **BEAST** (Bayesian Evolutionary Analysis)
  - http://beast.community
  - Tutoriels extensifs
  
- **MrBayes**
  - http://nbisweden.github.io/MrBayes/
  - Documentation complete
  
- **Stan** (Statistiques bayesiennes)
  - https://mc-stan.org
  - Langage de programmation probabiliste
  
- **PyMC3** (Python)
  - Probabilistic programming
  - Notebooks Jupyter

**Bases de donnees et repositories** :
- **GitHub : awesome-bayes**
  - Collection de ressources
  - Livres, codes, articles
  
- **ArXiv : stat.AP (statistics applications)**
  - Papers recents
  - Applications biologiques

### Exercices pratiques

**Exercice bio-informatique 1 : Implementer Bayes** :
Ecris une fonction Python pour calculer P(A|B) avec le theoreme de Bayes.

```python
def bayes_theorem(p_b_given_a, p_a, p_b_given_not_a):
    """
    Calcule P(A|B) en utilisant le theoreme de Bayes.
    
    Args:
        p_b_given_a: P(B|A) - vraisemblance
        p_a: P(A) - prior
        p_b_given_not_a: P(B|non A)
    
    Returns:
        P(A|B) - posterior
    """
    # A implementer
    pass

# Test
print(bayes_theorem(0.99, 0.0001, 0.01))  # Test genetique
```

**Exercice bio-informatique 2 : Classificateur Naive Bayes** :
Implemente un classificateur simple pour predire si une sequence est codante ou non.

```python
def naive_bayes_classifier(sequence, codon_freqs_coding, codon_freqs_noncoding, prior_coding):
    """
    Classifie une sequence comme codante ou non.
    
    Args:
        sequence: Sequence ADN
        codon_freqs_coding: Frequences codons pour genes
        codon_freqs_noncoding: Frequences codons pour non-genes
        prior_coding: P(gene) a priori
    
    Returns:
        P(codante|sequence)
    """
    # A implementer
    # 1. Decoupe sequence en codons
    # 2. Calcule P(sequence|codante)
    # 3. Calcule P(sequence|non codante)
    # 4. Applique Bayes
    pass
```

**Exercice theorique 3 : Analyse de test**
Un nouveau test de depistage d'une mutation BRCA1 a :
- Sensibilite : 98%
- Specificite : 95%

La mutation est presente chez 0.1% de la population.

a) Calcule P(mutation|test+)
b) Combien de faux positifs pour 1 vrai positif ?
c) Comment ameliorer la precision ?

**Exercice pratique 4 : Simulation Monte Carlo**
Simule le probleme du test genetique avec Monte Carlo :

```python
import random

def simulate_test(n_simulations=100000, prevalence=0.0001, 
                  sensitivity=0.99, specificity=0.99):
    """
    Simule test genetique sur grande population.
    
    Returns:
        Proportion de vrais positifs parmi tous les positifs
    """
    # A implementer
    # 1. Genere population avec maladie selon prevalence
    # 2. Applique test selon sensibilite/specificite
    # 3. Compte vrais positifs / tous positifs
    pass
```

**Exercice avance 5 : Inference phylogenetique simple**
Implemente un calcul bayesien simple pour choisir entre deux arbres :

```python
def compare_trees(sequences, tree1, tree2, prior_tree1=0.5):
    """
    Compare deux topologies d'arbres pour des sequences.
    
    Args:
        sequences: Liste de sequences alignees
        tree1, tree2: Topologies d'arbres
        prior_tree1: P(tree1) a priori
    
    Returns:
        P(tree1|sequences), P(tree2|sequences)
    """
    # A implementer
    # 1. Calcule vraisemblance P(sequences|tree1)
    # 2. Calcule vraisemblance P(sequences|tree2)
    # 3. Applique Bayes pour chaque arbre
    pass
```

**Exercice avance 6 : Reseau bayesien genetique**
Construis un petit reseau bayesien pour la transmission mendelienne :

```python
class GeneticBayesianNetwork:
    """
    Reseau bayesien pour heredite mendelienne.
    
    Nodes: Parent1, Parent2, Child
    """
    
    def __init__(self):
        # Definir structure et probabilites conditionnelles
        pass
    
    def infer_child_genotype(self, parent1_genotype, parent2_genotype):
        """Calcule P(genotype enfant | genotypes parents)"""
        pass
    
    def infer_parent_genotype(self, child_genotype, other_parent_genotype):
        """Calcule P(genotype parent | enfant et autre parent)"""
        # Utilise Bayes !
        pass
```

**Projet 7 : Analyse de variants avec prior**
Implemente un variant caller bayesien simple :

```python
def bayesian_variant_caller(reads, position, prior_variant=0.001):
    """
    Determine si position contient un variant.
    
    Args:
        reads: Liste de reads couvrant la position
        position: Position genomique
        prior_variant: P(variant) a priori
    
    Returns:
        P(variant|reads), alleles, qualite
    """
    # A implementer
    # 1. Compte alleles dans reads
    # 2. Calcule vraisemblance P(reads|variant)
    # 3. Calcule vraisemblance P(reads|pas variant)
    # 4. Applique Bayes
    pass
```

**Projet 8 : Exploration BEAST**
- Telecharge BEAST
- Execute tutoriel basique
- Analyse trace files (Tracer)
- Visualise arbres posterieurs (FigTree)
- Compare prior vs posterior distributions

**Projet 9 : Comparaison methodes**
Compare inference bayesienne vs maximum de vraisemblance :
- Genere sequences simulees
- Reconstruit arbre avec MrBayes (bayesien)
- Reconstruit arbre avec RAxML (ML)
- Compare resultats et temps de calcul

---

## Problemes Rosalind associes

Bien que Rosalind n'ait pas de problemes explicitement "bayesiens", plusieurs problemes peuvent beneficier d'une approche probabiliste :

**PROB : Introduction to Random Strings**
- Calcul de probabilites de sequences
- Base pour vraisemblance

**MEME : Discovering Motifs**
- Peut utiliser approches bayesiennes
- Modeles probabilistes

**KMP : Speeding Up Motif Finding**
- Base algorithmique pour recherche probabiliste

**Liens avec phylogenie** :
Les problemes de phylogenie (NWCK, CUNR, etc.) peuvent etre abordes avec methodes bayesiennes, bien que Rosalind se concentre sur des methodes plus simples.

**Probabilites genetiques** :
Les problemes IPRB, LIA, IEV de la Fiche 06 peuvent aussi etre vus sous angle bayesien (mise a jour de croyances).

---

## Lien avec autres fiches

**Fiche 06 - Probabilites en genetique** :
- Base probabiliste necessaire pour Bayes
- Probabilites conditionnelles implicites dans carres de Punnett
- P(phenotype|genotype)

**Fiche 03 - Mutations et evolution** :
- Inference bayesienne pour phylogenie
- Modeles d'evolution probabilistes
- Calcul de parcimonie peut etre bayesien

**Applications futures** :
- Annotation de genomes (Fiches a venir)
- Structure de proteines (prediction bayesienne)
- Genomique des populations (inference parametres)

---

## Notes importantes

### MCMC (Markov Chain Monte Carlo)

**Probleme** :
Pour beaucoup de problemes bayesiens complexes (phylogenie, etc.), calculer le posterior exact est impossible.

**Solution** :
MCMC echantillonne la distribution posterieure.

**Algorithmes** :
- Metropolis-Hastings
- Gibbs sampling
- Hamiltonian Monte Carlo

**Logiciels** :
- BEAST, MrBayes (phylogenie)
- Stan, PyMC3 (general)
- JAGS (Just Another Gibbs Sampler)

**Concept** :
Au lieu de calculer P(parametres|donnees) exactement, on genere des echantillons de cette distribution.

### Convergence et diagnostics

**Problemes possibles** :
- Chaines qui n'ont pas converge
- Autocorrelation elevee
- Multimodalite

**Diagnostics** :
- Trace plots (visualisation)
- ESS (Effective Sample Size)
- Gelman-Rubin statistic
- Geweke diagnostic

**En pratique** :
Toujours verifier convergence avant d'interpreter resultats !

### Prior informatif vs non-informatif

**Prior non-informatif** :
- Exprime ignorance maximale
- Exemple : uniforme sur [0,1]
- "Laisse les donnees parler"

**Prior informatif** :
- Incorpore connaissances prealables
- Peut ameliorer inference
- Mais peut biaiser si faux

**En bio-informatique** :
- Souvent priors faibles mais informatifs
- Bases sur litterature, bases de donnees
- Sensitivity analysis importante

---

## Misconceptions courantes

### "Si test positif, je suis probablement malade"

**Faux !** Depend enormement de la prevalence (prior).
Avec maladie rare, beaucoup de faux positifs meme si test precis.

### "P(A|B) = P(B|A)"

**Faux !** Ce sont des probabilites tres differentes.
C'est tout le point du theoreme de Bayes de les relier.

### "Bayes est subjectif a cause du prior"

**Nuance** : Le choix du prior peut etre subjectif, mais :
- Souvent base sur connaissances solides
- Sensitivity analysis teste impact du prior
- Avec beaucoup de donnees, prior a peu d'impact

### "Methodes bayesiennes sont toujours meilleures"

**Faux** : Depends du probleme :
- Bayesien : meilleur avec prior informatif, petits echantillons
- Frequentiste : souvent plus simple, moins d'hypotheses
- Les deux ont leur place

---

**Felicitations !** Tu maitrises maintenant :
- Les probabilites conditionnelles
- Le theoreme de Bayes et son interpretation
- Les applications en tests diagnostiques
- L'utilisation en bio-informatique
- La difference entre approches bayesienne et frequentiste

**Ces concepts sont essentiels pour** :
- Phylogenie moleculaire moderne
- Annotation de genomes
- Variant calling
- Machine learning en biologie
- Interpretation de tests genetiques
- Recherche en bioinformatique

**Prochaines fiches suggerees** :
- **Fiche 09** : Alignement de sequences (utilise probabilites)
- **Fiche 10** : Hidden Markov Models (bases sur Bayes)
- **Fiche 11** : Phylogenie moleculaire (methodes bayesiennes)

---

**Note pedagogique** : Cette fiche introduit des concepts mathematiques importants. N'hesite pas a y revenir regulierement et a faire les exercices plusieurs fois. La comprehension intuitive du theoreme de Bayes est cruciale pour la bio-informatique moderne !
