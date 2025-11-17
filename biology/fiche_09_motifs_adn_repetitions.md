# Fiche 09 : Motifs d'ADN et repetitions

**Date de creation** : 17 novembre 2025  
**Sujet** : Motifs biologiques, repetitions genomiques, elements Alu, recherche de motifs

---

## Contexte biologique

### Le probleme de la recherche

**Question fondamentale** :
- Comment identifier des sequences d'ADN qui apparaissent dans plusieurs organismes ?
- Pourquoi certaines sequences sont-elles si communes ?
- Que nous apprend la repetition d'une sequence ?

**Importance** :
- Trouver le meme intervalle d'ADN dans deux genomes differents suggere fortement que cet intervalle a la **meme fonction** dans les deux organismes
- Permet d'inferer la fonction de genes inconnus
- Base de la biologie comparative et de l'annotation de genomes

---

## Motifs d'ADN (DNA Motifs)

### Definition

**Motif (Motif)** :
- Intervalle d'ADN communement partage entre plusieurs organismes
- Sequence qui se repete, souvent avec une signification fonctionnelle
- Peut etre court (quelques bases) ou long (centaines de bases)

**Caracteristiques** :
- Conservation evolutive : present dans differentes especes
- Souvent lie a une fonction biologique specifique
- Peut tolerer des variations mineures

### Types de motifs

#### 1. Motifs regulateurs

**Fonction** : Controle de l'expression genique

**Exemples** :
- **TATA box** : TATAAA (site de liaison pour transcription)
- **CAAT box** : GGCCAATCT (enhancer de transcription)
- **GC box** : GGGCGG (promoteur)

**Localisation** : Generalement dans les regions promotrices (avant les genes)

#### 2. Motifs de liaison proteique

**Fonction** : Sites ou les proteines se lient a l'ADN

**Exemples** :
- Sites de liaison de facteurs de transcription
- Sites de restriction enzymatique (ex: EcoRI reconnait GAATTC)
- Origine de replication

**Caracteristiques** :
- Sequence specifique reconnue par une proteine
- Souvent palindromiques (pour enzymes de restriction)

#### 3. Motifs structuraux

**Fonction** : Organisation et structure de l'ADN

**Exemples** :
- Sequences riches en AT (regions flexibles)
- Sequences riches en GC (regions rigides)
- Z-DNA forming sequences

#### 4. Motifs fonctionnels

**Fonction** : Elements avec roles specifiques

**Exemples** :
- Codons start (ATG) et stop (TAA, TAG, TGA)
- Sites d'epissage (GT...AG)
- Polyadenylation signals (AATAAA)
- Sequences signal (pour export de proteines)

### Variabilite des motifs

**Motif exact** :
- Sequence identique a chaque occurrence
- Exemple : TATAAA

**Motif degenere** :
- Permet des variations a certaines positions
- Notation : N = n'importe quelle base, R = purine (A/G), Y = pyrimidine (C/T)
- Exemple : TATAWR (W = A ou T, R = A ou G)

**Motif consensus** :
- Represente la sequence la plus frequente
- Obtenu en alignant plusieurs occurrences

---

## Repetitions genomiques (Repeats)

### Definition

**Repetition (Repeat)** :
- Intervalle d'ADN qui apparait plusieurs fois dans un genome
- Peut etre exact ou avec des modifications mineures
- Beaucoup plus frequent que ce que le hasard dicterait

### Importance evolutive

**Observation cle** :
> Les genomes sont truffes de repetitions qui apparaissent bien plus souvent que ne le predit le hasard aleatoire

**Implications** :
- Les genomes ne sont pas aleatoires
- Le "langage de l'ADN" est tres puissant
- Compare au reutilisation frequente de mots communs dans les langues humaines

### Types de repetitions

#### 1. Repetitions en tandem

**Definition** :
- Sequences repetees cote a cote
- Pattern : ABABABAB...

**Types** :
- **Satellites** : tres longues repetitions (millions de bp)
- **Minisatellites** : 10-100 bp repetes
- **Microsatellites (STR)** : 2-6 bp repetes

**Exemple** :
```
Sequence : CAGCAGCAGCAGCAG
Motif : CAG (repete 5 fois)
```

**Applications** :
- Empreintes genetiques (forensique)
- Tests de paternite
- Etudes de populations

#### 2. Repetitions dispersees (Interspersed repeats)

**Definition** :
- Sequences repetees reparties dans tout le genome
- Non contigues

**Types principaux** :
- **SINE** (Short Interspersed Nuclear Elements) : <500 bp
- **LINE** (Long Interspersed Nuclear Elements) : >500 bp
- **Transposons** : elements mobiles

---

## Le cas des repetitions Alu

### Caracteristiques

**Definition** :
- Repetition la plus commune chez les humains
- Type : SINE (Short Interspersed Nuclear Element)
- Nomme d'apres l'enzyme de restriction AluI qui les coupe

**Proprietes** :
- **Longueur** : environ 300 paires de bases
- **Nombre** : environ 1 million de copies dans chaque genome humain
- **Proportion** : ~11% du genome humain total
- **Distribution** : present sur tous les chromosomes

### Structure d'Alu

**Organisation** :
```
[Promoteur interne] - [Region gauche] - [Region centrale A-rich] - [Region droite] - [Queue poly(A)]
     |                                                                                      |
  ~130 bp                                                                              ~170 bp
```

**Caracteristiques structurales** :
- Derive de l'ARN 7SL (composant du SRP - Signal Recognition Particle)
- Sequence dimere : deux moities similaires
- Queue poly(A) terminale
- Pas d'activite enzymatique propre

### Mecanisme de propagation

**Retrotransposition** :
1. Alu est transcrit en ARN
2. ARN est reverse-transcrit en ADN (par LINE-1 reverse transcriptase)
3. ADN est reinsere dans le genome a un nouvel endroit
4. "Copy-and-paste" via intermediaire ARN

**Consequence** :
- Multiplication au fil du temps
- Toujours plus de copies a chaque generation
- Impossible de se debarrasser d'Alu une fois insere

### Impact sur le genome humain

#### Aspects negatifs (parasitique)

**Insertions deleteres** :
- Nouvelle insertion peut perturber un gene
- Cause frequente de maladies genetiques
- ~0.1% des mutations humaines dues a Alu

**Exemples de maladies** :
- Hemophilie A (insertion Alu dans gene F8)
- Neurofibromatose type 1 (insertion Alu dans gene NF1)
- Dystrophie musculaire de Duchenne (insertion Alu dans gene DMD)
- Cancer du sein (insertion Alu dans gene BRCA2)

**Mecanisme pathogene** :
```
Gene normal : [Exon1] - [Intron] - [Exon2] - [Intron] - [Exon3]
                                        ↓ insertion Alu
Gene mute :   [Exon1] - [Intron] - [Exon2] - [Alu 300bp] - [Intron] - [Exon3]
                                              └─> Disruption
```

#### Aspects positifs potentiels

**Evolution genomique** :
- Cree variabilite genetique
- Source de materiel pour evolution
- Peut creer nouveaux exons (exonisation)

**Regulation genique** :
- Peut affecter epissage alternatif
- Peut creer sites de liaison pour facteurs de transcription
- Contribution a la diversite d'expression

**Reorganisation chromosomique** :
- Recombinaison entre Alu peut causer deletions/duplications
- Moteur de l'evolution structurale des chromosomes

### Alu comme horloge evolutive

**Datation** :
- Differentes familles d'Alu d'ages differents
- Vieilles sequences : plus de mutations accumulees
- Jeunes sequences : plus proches de la sequence consensus

**Applications** :
- Tracer l'histoire evolutive des primates
- Dater les evenements de speciation
- Comprendre l'evolution du genome humain

### Comparaison entre especes

**Chez les primates** :
- Humains : ~1.1 million copies
- Chimpanzes : ~1.0 million copies
- Singes : moins de copies

**Specifique aux primates** :
- Alu absent chez les non-primates
- Equivalent dans d'autres especes :
  - Souris : elements B1/B2
  - Rat : elements ID

---

## Recherche de motifs

### Probleme computationnel

**Definition** :
- Etant donne une sequence (genome) et un motif, trouver toutes les occurrences du motif
- Tache courante en biologie moleculaire

**Complexite** :
- Genome humain : 3 milliards de bases
- Recherche naive : tres lente
- Necessite algorithmes efficaces

### Algorithmes de base

#### 1. Recherche naive

**Principe** :
- Comparer le motif a chaque position du genome
- Avancer d'une position a la fois

**Complexite** :
- Temps : O(n*m) ou n = taille genome, m = taille motif
- Inefficace pour grandes sequences

**Pseudo-code** :
```
fonction recherche_naive(genome, motif):
    pour chaque position i dans genome:
        si genome[i:i+len(motif)] == motif:
            enregistrer position i
```

#### 2. Algorithmes optimises

**Boyer-Moore** :
- Utilise information sur le motif
- Saute plusieurs positions a la fois
- Tres efficace en pratique

**Knuth-Morris-Pratt (KMP)** :
- Preprocesse le motif
- Evite comparaisons inutiles
- Complexite : O(n+m)

**Algorithmes d'indexation** :
- Suffix arrays
- FM-index
- Permettent recherche ultra-rapide

### Recherche de motifs degeneres

**Probleme** :
- Motif avec variations (ex: TATAWR)
- Matching approche (avec erreurs)

**Expression reguliere** :
- Pattern flexible
- Exemple : TATA\[AT\]\[AG\] pour TATAWR

**Algorithme** :
- Utiliser automates finis
- Score de similarite (distance de Hamming)
- Seuil de tolerance

---

## Applications en bio-informatique

### 1. Annotation de genomes

**Identification de genes** :
- Recherche de codons start (ATG)
- Recherche de codons stop (TAA, TAG, TGA)
- Identification de cadres de lecture ouverts (ORF)

**Elements regulateurs** :
- Trouver promoteurs (TATA box)
- Identifier enhancers
- Localiser terminateurs

### 2. Biologie comparative

**Conservation evolutive** :
- Comparer motifs entre especes
- Inferer fonction par homologie
- Identifier regions fonctionnelles

**Exemple** :
```
Humain :    ATCG-TATA-CGTA
Souris :    ATCG-TATA-CGTA
Poulet :    ATCG-TATA-CGTA
              ↑  TATA  ↑
         Region conservee → fonction importante
```

### 3. Prediction de sites de liaison

**Facteurs de transcription** :
- Chercher motifs connus (matrices position-poids)
- Predire regulation genique
- Comprendre reseaux de regulation

**Enzymes de restriction** :
- Identifier sites de coupure
- Planifier clonage moleculaire
- Design d'experiences

### 4. Detection de repetitions

**Identification** :
- Trouver tous les Alu dans un genome
- Localiser microsatellites
- Detecter duplications

**Masquage** :
- "Masquer" les repetitions avant analyse
- Eviter faux positifs dans recherche d'homologie
- Outil : RepeatMasker

### 5. Analyse de sequences

**Profile HMM** :
- Model probabiliste pour motifs
- Permet variations
- Utilise pour familles de proteines

**MEME/MAST** :
- Decouverte automatique de motifs
- Analyse de sequences co-regulees
- Identification de motifs inconnus

### 6. Design moleculaire

**Primers PCR** :
- Eviter regions repetitives
- Specificite maximale
- Verification in silico

**Sondes** :
- Design de sondes hybridation
- Eviter Alu et autres repetitions
- Applications : puces a ADN, FISH

---

## Points cles a retenir

### Motifs d'ADN
- Intervalle d'ADN partage entre organismes
- Suggere fonction biologique commune
- Types : regulateurs, liaison proteique, structuraux, fonctionnels
- Peuvent etre exacts ou degeneres

### Repetitions genomiques
- Intervalles d'ADN apparaissant plusieurs fois
- Beaucoup plus frequent que le hasard
- Types : en tandem vs dispersees
- Genomes non aleatoires

### Repetitions Alu
- Repetition la plus commune chez humains (~300 bp)
- ~1 million de copies (~11% du genome)
- Propagation par retrotransposition
- Generalement parasitique (cause maladies)
- Aucune fonction positive identifiee
- Important pour evolution genomique

### Recherche de motifs
- Tache computationnelle fondamentale
- Algorithmes : naive, KMP, Boyer-Moore
- Applications : annotation, regulation, conservation

---

## Auto-evaluation

### Questions rapides

1. Qu'est-ce qu'un motif d'ADN ?
2. Pourquoi trouver le meme motif dans deux especes est-il significatif ?
3. Qu'est-ce qu'une repetition genomique ?
4. Quelle est la repetition la plus commune chez l'humain ?
5. Quelle est la longueur d'une repetition Alu ?
6. Combien de copies d'Alu dans le genome humain ?
7. Quel est le mecanisme de propagation d'Alu ?
8. Pourquoi Alu est-il considere comme parasitique ?
9. Qu'est-ce qu'un motif degenere ?
10. Quelle est la complexite de l'algorithme de recherche naive ?
11. Que signifie TATAWR en notation de motif ?
12. Quel pourcentage du genome humain est constitue d'Alu ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. Intervalle d'ADN communement partage entre plusieurs organismes
2. Suggere que l'intervalle a la meme fonction dans les deux organismes
3. Intervalle d'ADN qui apparait plusieurs fois dans un genome
4. La repetition Alu (SINE)
5. Environ 300 paires de bases
6. Environ 1 million de copies
7. Retrotransposition (transcription → ARN → reverse transcription → reinsertion)
8. Cause frequemment des maladies genetiques lors de nouvelles insertions
9. Motif qui permet des variations a certaines positions
10. O(n*m) ou n = taille genome, m = taille motif
11. TATA + W(A ou T) + R(A ou G)
12. Environ 11% du genome humain total
</details>

---

## Mnemoniques

**Motif** : "**M**eme **O**ccurrence, **T**oujours **I**dentique, **F**onction"

**Alu** : "**A** **L**ot of **U**nwanted copies" (Beaucoup de copies non desirees)

**SINE vs LINE** : "**S**hort vs **L**ong" (Court vs Long)

**Retrotransposition** : "**R**NA **R**everse **R**einsert" (ARN → Reverse → Reinserer)

**Types de motifs** : "**R**egulation, **L**iaison, **S**tructure, **F**onction"

**Repetitions** : "**T**andem (cote a cote) vs **D**ispersees (partout)"

**TATA box** : "**T**ranscription **A**ctivation **T**emplate **A**rea"

---

## Lien avec la bio-informatique

### Algorithmes de recherche

**Pattern matching** :
- Recherche exacte de sequences
- Matching approche (avec erreurs)
- Regular expressions

**Indexation** :
- Suffix trees
- Suffix arrays
- FM-index (Burrows-Wheeler)

**Applications** :
- Recherche de genes
- Identification d'elements repetitifs
- Localisation de sites regulateurs

### Outils bioinformatiques

**RepeatMasker** :
- Identification et masquage de repetitions
- Base de donnees Repbase
- Essentiel avant annotation

**Tandem Repeats Finder** :
- Detection de repetitions en tandem
- Microsatellites, minisatellites
- Applications forensiques

**BLAST** :
- Recherche de similarite
- Utilise heuristiques
- Peut detecter motifs conserves

**MEME Suite** :
- Decouverte de motifs
- Analyse statistique
- Recherche dans bases de donnees

### Bases de donnees

**Repbase** :
- Collection de sequences repetitives
- Elements transposables annotes
- Reference pour masquage

**JASPAR** :
- Matrices de motifs de facteurs de transcription
- Profils position-poids
- Prediction de sites de liaison

**Dfam** :
- Families de repetitions d'ADN
- Models HMM
- Classification evolutive

### Genomique comparative

**Conservation phylogenetique** :
- Aligner genomes multiples
- Identifier motifs conserves
- Inferer fonction

**Syntenie** :
- Conservation ordre des genes
- Blocs de conservation
- Histoire evolutive

---

## Exercices pratiques

### Exercice 1 : Comptage simple
Combien de fois le motif "ATG" apparait dans : "ATGATGATCGATG" ?

**Indice** : Parcours la sequence et compte les occurrences. Attention aux chevauchements possibles !

### Exercice 2 : Positions
Trouve toutes les positions (index 0) du motif "ATA" dans : "GATATATGCATA"

**Indice** : Note la position de debut de chaque occurrence. Deux occurrences peuvent se chevaucher.

### Exercice 3 : Motif degenere
Le motif est "ATN" (N = n'importe quelle base). Combien d'occurrences dans "ATAATCATGATG" ?

**Indice** : N peut etre A, T, C ou G. Compte toutes les sequences de 3 bases commencant par AT.

### Exercice 4 : Repetition en tandem
Identifie la repetition en tandem dans : "CAGCAGCAGCAG"

**Indice** : Cherche un pattern qui se repete immediatement cote a cote.

### Exercice 5 : Longueur d'Alu
Si le genome humain contient 1 million de copies d'Alu de 300 bp chacune, combien de bases au total ?

**Indice** : Multiplication simple. Puis calcule le pourcentage sur 3 milliards de bases.

### Exercice 6 : Recherche de TATA box
Une TATA box est le motif "TATAAA". Trouve sa position dans la sequence promotrice : "GCGCTATAAATGC"

**Indice** : Cherche la sequence exacte TATAAA.

### Cas de tests (avec reponses attendues)

**Test 1 - Comptage simple** :
- Input : Sequence = "ATGATGATCGATG", Motif = "ATG"
- Output attendu : 4 occurrences

**Test 2 - Positions** :
- Input : Sequence = "GATATATGCATA", Motif = "ATA"
- Output attendu : Positions [1, 3, 9]

**Test 3 - Motif degenere** :
- Input : Sequence = "ATAATCATGATG", Motif = "ATN"
- Output attendu : 4 occurrences (ATA, ATC, ATG, ATG)

**Test 4 - Repetition en tandem** :
- Input : Sequence = "CAGCAGCAGCAG"
- Output attendu : Motif "CAG", repete 4 fois

**Test 5 - Calcul Alu** :
- Input : 1,000,000 copies × 300 bp
- Output attendu : 300,000,000 bp (300 Mb), soit 10% du genome (3 Gb)

**Test 6 - TATA box** :
- Input : Sequence = "GCGCTATAAATGC", Motif = "TATAAA"
- Output attendu : Position 4

**Test 7 - Pas de match** :
- Input : Sequence = "GCGCGCGC", Motif = "ATG"
- Output attendu : 0 occurrences

**Test 8 - Chevauchement** :
- Input : Sequence = "AAAA", Motif = "AA"
- Output attendu : 3 occurrences (positions 0, 1, 2)

---

## Pour aller plus loin

### Lectures recommandees

**Livres** :
- "Bioinformatics Algorithms" (Compeau & Pevzner)
  - Chapitre sur pattern matching
  - Algorithmes de recherche de motifs
  - Applications pratiques
  
- "Biological Sequence Analysis" (Durbin et al.)
  - Chapitre 4 : Pairwise alignment
  - Hidden Markov Models pour motifs
  - Methodes statistiques
  
- "Mobile DNA III" (Craig et al.)
  - Bible sur elements transposables
  - Chapitre detaille sur Alu
  - Mecanismes moleculaires
  
- "Algorithms on Strings, Trees, and Sequences" (Gusfield)
  - Algorithmes de recherche de motifs
  - Suffix trees et applications
  - Reference technique

**Articles scientifiques** :

**Sur Alu** :
- Batzer & Deininger (2002) : "Alu repeats and human genomic diversity"
- Cordaux & Batzer (2009) : "The impact of retrotransposons on human genome evolution"
- Lander et al. (2001) : Human Genome Paper - section sur repetitions

**Sur motifs** :
- Stormo (2000) : "DNA binding sites: representation and discovery"
- Bailey et al. (2009) : "MEME Suite: tools for motif discovery"
- D'haeseleer (2006) : "How does DNA sequence motif discovery work?"

**Sur algorithmes** :
- Boyer & Moore (1977) : "A fast string searching algorithm"
- Knuth, Morris & Pratt (1977) : "Fast pattern matching in strings"
- Aho & Corasick (1975) : "Efficient string matching"

### Ressources en ligne

**Cours et tutoriels** :

- **Rosalind.info** : Problemes SUBS, CONS
  - Finding a Motif in DNA
  - Consensus and Profile
  
- **Coursera : Bioinformatics Algorithms**
  - Module sur pattern matching
  - Algorithmes de recherche
  
- **MIT OpenCourseWare : Computational Biology**
  - Lecture sur motif finding
  - Applications genomiques

**Outils en ligne** :

- **NCBI BLAST** : blast.ncbi.nlm.nih.gov
  - Recherche de similarite
  - Detection de motifs conserves
  
- **RepeatMasker** : repeatmasker.org
  - Masquage de repetitions
  - Visualisation Alu
  
- **MEME Suite** : meme-suite.org
  - Decouverte de motifs
  - Analyse statistique
  - MAST pour recherche
  
- **JASPAR** : jaspar.genereg.net
  - Base de donnees motifs TF
  - Matrices position-poids
  - Prediction sites de liaison
  
- **Dfam** : dfam.org
  - Base donnees families repetitions
  - Annotations Alu
  - Models HMM

**Bases de donnees** :

- **Repbase** : girinst.org/repbase
  - Collection repetitions
  - Sequences Alu annotees
  
- **UCSC Genome Browser** : genome.ucsc.edu
  - Track RepeatMasker
  - Visualisation Alu in situ
  - Annotations genomiques

**Visualisation** :

- **IGV (Integrative Genomics Viewer)**
  - Visualiser repetitions dans genomes
  - Track Alu
  
- **Genome browsers**
  - Ensembl, UCSC
  - Tracks de repetitions

### Exercices pratiques

**Exercice bio-informatique 1 : Recherche naive** :
Implemente un algorithme de recherche naive de motif.

```python
def find_motif_naive(genome, motif):
    """
    Trouve toutes les positions du motif dans le genome.
    
    Args:
        genome: sequence d'ADN (string)
        motif: motif a chercher (string)
    
    Returns:
        Liste des positions (index 0)
    """
    # A implementer
    pass

# Test
print(find_motif_naive("GATATATGCATA", "ATA"))
# Devrait afficher [1, 3, 9]
```

**Exercice bio-informatique 2 : Comptage avec chevauchement** :
Compte les occurrences d'un motif en gerant les chevauchements.

```python
def count_motif_overlapping(genome, motif):
    """
    Compte le nombre d'occurrences (avec chevauchement).
    """
    # A implementer
    pass

# Test
print(count_motif_overlapping("AAAA", "AA"))
# Devrait afficher 3
```

**Exercice bio-informatique 3 : Motif degenere** :
Implemente la recherche d'un motif avec caracteres jokers.

```python
def find_degenerate_motif(genome, pattern):
    """
    Recherche motif avec N (any base), R (A/G), Y (C/T).
    """
    # A implementer
    # Convertir pattern en expression reguliere
    pass

# Test
print(find_degenerate_motif("ATAATCATG", "ATN"))
# Devrait trouver ATA, ATC, ATG
```

**Exercice bio-informatique 4 : Detection repetitions en tandem** :
Trouve les repetitions en tandem dans une sequence.

```python
def find_tandem_repeats(sequence, min_length=2, min_copies=2):
    """
    Detecte repetitions en tandem.
    
    Args:
        sequence: sequence d'ADN
        min_length: longueur minimale du motif
        min_copies: nombre minimum de repetitions
    
    Returns:
        Liste de (motif, position, nombre_copies)
    """
    # A implementer
    pass

# Test
print(find_tandem_repeats("CAGCAGCAGCAG"))
# Devrait trouver: ("CAG", 0, 4)
```

**Exercice bio-informatique 5 : Profile matrix** :
Cree une matrice de profil a partir d'alignement de sequences.

```python
def create_profile_matrix(sequences):
    """
    Cree matrice de frequences pour chaque position.
    
    Args:
        sequences: liste de sequences alignees (meme longueur)
    
    Returns:
        Dictionnaire {base: [frequences par position]}
    """
    # A implementer
    pass

# Test
seqs = ["ATCG", "ATCG", "TTCG"]
print(create_profile_matrix(seqs))
# A: [2, 0, 0, 0]
# T: [1, 3, 0, 0]
# C: [0, 0, 3, 0]
# G: [0, 0, 0, 3]
```

**Exercice theorique 6 : Analyse Alu** :

Questions :
1. Pourquoi Alu est-il considere comme "parasitique" ?
2. Comment Alu se propage-t-il dans le genome ?
3. Quels sont les risques d'une nouvelle insertion Alu ?
4. Pourquoi ne peut-on pas eliminer Alu du genome ?

**Exercice pratique 7 : Visualisation** :

Telecharge une sequence genomique humaine depuis NCBI et :
1. Utilise RepeatMasker online pour identifier les Alu
2. Compte le nombre d'Alu dans ta sequence
3. Calcule le pourcentage d'Alu
4. Compare avec la moyenne genomique (11%)

**Exercice Rosalind 8** :

Resous les problemes suivants sur Rosalind.info :
1. **SUBS** : Finding a Motif in DNA
2. **CONS** : Consensus and Profile
3. **KMP** : Speeding Up Motif Finding (avance)
4. **LCSM** : Finding a Shared Motif (avance)

**Exercice avance 9 : KMP algorithm** :

Implemente l'algorithme Knuth-Morris-Pratt pour recherche efficace.

```python
def compute_lps(pattern):
    """Calcule Longest Prefix Suffix array."""
    # A implementer
    pass

def kmp_search(text, pattern):
    """Recherche KMP - O(n+m)."""
    # A implementer
    pass
```

**Exercice avance 10 : Consensus sequence** :

A partir d'un alignement multiple, trouve :
1. La sequence consensus (base la plus frequente)
2. La matrice de profil complete
3. Le logo de sequence (visualisation)

### Projets pratiques

**Projet 1 : Alu detector** :
Cree un outil qui :
- Prend une sequence d'ADN en entree
- Identifie toutes les sequences similaires a Alu
- Permet une distance de Hamming jusqu'a 10%
- Visualise les positions sur un graphique

**Projet 2 : Motif discovery** :
Implemente un algorithme simple de decouverte de motifs :
- Prend plusieurs sequences en entree
- Trouve les motifs communs (k-mers)
- Classe par frequence
- Genere sequence consensus

**Projet 3 : Regulatory elements finder** :
Cree un outil qui cherche :
- TATA box
- CAAT box
- Sites d'epissage (GT-AG)
- Codons start/stop
Dans une sequence promotrice/gene

**Projet 4 : RepeatMasker lite** :
Version simplifiee de RepeatMasker :
- Base de donnees de repetitions courantes
- Recherche et masquage
- Output en format standard (lowercase ou X)
- Statistiques sur types de repetitions

---

## Problemes Rosalind associes

**Finding a Motif in DNA (SUBS)** :
- Trouver toutes les positions d'un motif
- Gerer les chevauchements
- Input : sequence + motif
- Output : liste de positions (1-indexed)

**Consensus and Profile (CONS)** :
- Creer matrice de profil
- Deduire sequence consensus
- Input : sequences alignees (FASTA)
- Output : matrice + consensus

**Speeding Up Motif Finding (KMP)** :
- Implementer algorithme KMP
- Preprocesser le motif
- Recherche efficace O(n+m)

**Finding a Shared Motif (LCSM)** :
- Plus long motif commun
- Entre plusieurs sequences
- Probleme classique LCS

---

## Perspectives historiques

### Decouverte d'Alu (1980)

**Carl Schmid** :
- Identifie sequences repetees coupees par AluI
- ~300 bp, tres abondantes
- Nomme "Alu family"

**Realisation** :
- Plus de 1 million de copies
- 11% du genome humain
- Phenomene inattendu

### Impact scientifique

**Comprehension du genome** :
- Genomes non-codants fonctionnels
- Elements mobiles majeurs
- Evolution par transposition

**Medecine** :
- Nouvelles causes de maladies
- Diagnostic genetique
- Therapie genique (precautions)

---

## Notes importantes

### Considerations pratiques

**Masquage avant analyse** :
- Repetitions peuvent creer faux positifs
- Toujours masquer avant BLAST
- Utiliser RepeatMasker

**Interpretation resultats** :
- Motifs dans repetitions = suspect
- Verifier conservation evolutive
- Valider experimentalement

### Limites

**Prediction vs realite** :
- Motif predit ≠ fonction garantie
- Validation experimentale necessaire
- Contexte genomique important

**Variabilite** :
- Motifs peuvent varier
- Distance evolutive
- Pression selective

---

## Connexions avec autres fiches

**Fiche 02 (Structure ADN)** :
- Base pour comprendre sequences
- Appariement de bases

**Fiche 03 (Mutations)** :
- Mutations creent variabilite motifs
- Evolution des repetitions

**Fiche 04 (Transcription)** :
- Motifs regulateurs (TATA box)
- Sites d'epissage

**Fiche 07 (Code genetique)** :
- Codons comme motifs
- Start/stop codons

**Fiche 08 (Bayes)** :
- Modeles probabilistes pour motifs
- HMM pour detection

---

**Felicitations !** Tu maitrises maintenant :
- Les motifs d'ADN et leur importance
- Les repetitions genomiques
- Le cas special des repetitions Alu
- Les algorithmes de recherche de motifs
- Les applications en bio-informatique

**Ces concepts sont essentiels pour** :
- Annotation de genomes
- Biologie comparative
- Prediction de sites regulateurs
- Comprehension de l'evolution genomique
- Detection d'elements mobiles
- Design moleculaire (primers, sondes)

**Prochaine fiche suggeree** : Alignement de sequences (algorithmes Needleman-Wunsch et Smith-Waterman)
