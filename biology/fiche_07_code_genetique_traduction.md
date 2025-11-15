# Fiche 07 : Code genetique et traduction

**Date de creation** : 15 novembre 2025  
**Sujet** : Acides amines, proteines, code genetique, codons, traduction ARN → Proteine

---

## Du gene a la proteine

### Vue d'ensemble

**Le flux de l'information genetique** :
```
ADN → ARN → Proteine
```

**Roles** :
- **ADN** : stockage de l'information (bibliotheque)
- **ARN** : intermediaire, messager (copie de travail)
- **Proteine** : execution des fonctions cellulaires (ouvriers)

### Importance des proteines

**Fonctions cellulaires** :
- Les proteines executent **toutes** les fonctions pratiques de la cellule
- Enzymes, transporteurs, recepteurs, structure, defense
- La cle pour comprendre la vie = comprendre la relation entre sequence d'acides amines et fonction de la proteine

**Proteomique** :
- Champ d'etude dedie aux proteines
- Analyse de toutes les proteines d'une cellule/organisme
- Complementaire a la genomique

---

## Les acides amines et les proteines

### Structure des proteines

**Definition** :
- Les proteines sont des **polymeres d'acides amines**
- Comme les acides nucleiques sont des polymeres de nucleotides
- Chaine lineaire qui se replie en structure 3D complexe

**20 acides amines standards** :
- Apparaissent dans toutes les especes
- Chacun a des proprietes chimiques uniques
- Determines par le code genetique

### Structure primaire

**Definition** :
- Ordre des acides amines dans la chaine
- Equivalent a l'ordre des bases pour l'ADN/ARN
- Determine par la sequence de l'ARNm

**Notation** :
- Code a 3 lettres : Met, Ala, Gly, etc.
- Code a 1 lettre : M, A, G, etc.
- Exemple : Met-Ala-Gly-Trp ou MAGW

### Polypeptides

**Terminologie** :
- **Polypeptide** : chaine d'acides amines
- **Proteine** : un ou plusieurs polypeptides fonctionnels

**Types** :
- Proteines monomeres : 1 seul polypeptide
- Proteines oligomeres : plusieurs polypeptides (sous-unites)

**Exemple** :
- Hemoglobine : 4 polypeptides (2 alpha + 2 beta)
- Insuline : 2 polypeptides relies par ponts disulfure

### Les 20 acides amines

**Classification par proprietes** :

**Non polaires (hydrophobes)** :
- Alanine (Ala, A)
- Valine (Val, V)
- Leucine (Leu, L)
- Isoleucine (Ile, I)
- Methionine (Met, M)
- Phenylalanine (Phe, F)
- Tryptophane (Trp, W)
- Proline (Pro, P)
- Glycine (Gly, G)

**Polaires (hydrophiles)** :
- Serine (Ser, S)
- Threonine (Thr, T)
- Cysteine (Cys, C)
- Tyrosine (Tyr, Y)
- Asparagine (Asn, N)
- Glutamine (Gln, Q)

**Charges** :
- Acides (charges -) : Aspartate (Asp, D), Glutamate (Glu, E)
- Basiques (charges +) : Lysine (Lys, K), Arginine (Arg, R), Histidine (His, H)

---

## Le code genetique

### Le probleme de la traduction

**Difficulte** :
- 4 bases ARN (A, U, G, C)
- 20 acides amines a coder
- 4 bases ne suffisent pas : 4^1 = 4 possibilites seulement
- 2 bases ne suffisent pas : 4^2 = 16 possibilites

**Solution** :
- 3 bases = 1 codon
- 4^3 = 64 codons possibles
- Largement suffisant pour 20 acides amines !

### Codon

**Definition** :
- Sequence de **3 nucleotides** d'ARN
- Unite de base du code genetique
- Chaque codon specifie un acide amine

**Exemple** :
```
ARNm : 5' - AUG GCA UGG UAA - 3'
       
Codons :     AUG GCA UGG UAA
             |   |   |   |
            Met Ala Trp Stop
```

### Redondance du code (degenerescence)

**Observation** :
- 64 codons pour 20 acides amines
- Plusieurs codons peuvent coder le meme acide amine
- Aussi appele "degenerescence" du code

**Avantages** :
- Protection contre les mutations
- Mutation silencieuse possible (meme acide amine)
- Flexibilite evolutive

**Exemple** :
```
Leucine (Leu) : UUA, UUG, CUU, CUC, CUA, CUG (6 codons)
Methionine (Met) : AUG (1 seul codon)
```

### Universalite du code

**Principe** :
- Le code genetique est quasi-universel
- Meme codons → memes acides amines dans presque toutes les especes
- Preuve d'un ancetre commun

**Exceptions** :
- Mitochondries (quelques variations)
- Certains protozoaires
- Variations tres rares

---

## Les codons speciaux

### Codon start (initiation)

**Codon AUG** :
- Seul codon de start (initiation)
- Code pour la Methionine (Met)
- **Indique toujours le debut de la traduction**
- Premier acide amine de toute proteine

**Particularite** :
- AUG a double role :
  - Codon start en debut de sequence
  - Code pour Met a l'interieur de la sequence

**Exemple** :
```
5' - AUG GCA AUG UGG UAA - 3'
     ↑       ↑
   Start    Met interne
```

### Codons stop (terminaison)

**3 codons stop** :
- **UAA** (ochre)
- **UAG** (amber)
- **UGA** (opal)

**Caracteristiques** :
- Ne codent pour **aucun** acide amine
- Signalent la fin de la traduction
- Appelés aussi "codons non-sens"
- Provoquent la liberation du polypeptide

**Exemple** :
```
5' - AUG GCA UGG UAA - 3'
     ↑           ↑
   Start       Stop
   
Proteine : Met-Ala-Trp
```

---

## Le processus de traduction

### Vue d'ensemble

**Acteurs principaux** :
1. **ARNm** (messager) : porte le message genetique
2. **Ribosome** : organelle qui realise la traduction
3. **ARNt** (transfert) : apporte les acides amines

### Structure de l'ARN de transfert (tRNA)

**Caracteristiques** :
- Petite molecule d'ARN (~75-95 nucleotides)
- Structure en "feuille de trefle" (2D)
- Structure en "L" (3D)

**Deux extremites importantes** :

**1. Anticodon (une extremite)** :
- Sequence de 3 nucleotides
- Complementaire au codon de l'ARNm
- Permet reconnaissance specifique

**2. Site d'attachement de l'acide amine (autre extremite)** :
- Attache l'acide amine correspondant
- Liaison covalente acide amine-tRNA

**Exemple** :
```
tRNA pour Alanine (Ala) :
- Anticodon : CGU (lit codon GCA)
- Acide amine attache : Alanine
```

### Appariement codon-anticodon

**Regles** :
- Complementarite de bases (comme ADN)
- Mais antiparallele !
- Codon (5'→3') s'apparie avec anticodon (3'→5')

**Exemple** :
```
ARNm (codon) :     5' - GCA - 3'
                        |||
tRNA (anticodon) : 3' - CGU - 5'
                        ↑
                     Alanine attachee
```

### Etapes de la traduction

**1. Initiation**
- Ribosome se fixe sur l'ARNm
- Recherche du codon start (AUG)
- Premier tRNA (Met) se positionne
- Formation du complexe ribosome-ARNm-tRNA

**2. Elongation**
- Ribosome avance codon par codon (5' → 3')
- Pour chaque codon :
  - tRNA avec anticodon complementaire se lie
  - Acide amine est ajoute a la chaine
  - tRNA libere est ejecte
- Formation progressive de la chaine polypeptidique

**3. Terminaison**
- Ribosome rencontre un codon stop
- Aucun tRNA ne correspond aux codons stop
- Facteurs de liberation reconnaissent le stop
- Polypeptide est libere
- Ribosome se dissocie de l'ARNm

### Illustration du processus

```
Etape 1 : Initiation
ARNm : 5' - [AUG] GCA UGG UAA - 3'
              ↑
         Ribosome + tRNA(Met)

Etape 2 : Elongation (codon 2)
ARNm : 5' - AUG [GCA] UGG UAA - 3'
                  ↑
            tRNA(Ala) arrive
Chaine : Met-Ala

Etape 3 : Elongation (codon 3)
ARNm : 5' - AUG GCA [UGG] UAA - 3'
                      ↑
                tRNA(Trp) arrive
Chaine : Met-Ala-Trp

Etape 4 : Terminaison
ARNm : 5' - AUG GCA UGG [UAA] - 3'
                          ↑
                     Codon stop
Proteine finale : Met-Ala-Trp
```

### Vitesse de traduction

**Chez les procaryotes** :
- 15-20 acides amines par seconde
- Traduction tres rapide
- Peut commencer avant fin de transcription

**Chez les eucaryotes** :
- 5-10 acides amines par seconde
- Plus lent (controle qualite)
- Separation transcription/traduction (noyau/cytoplasme)

---

## Le dogme central de la biologie moleculaire

### Enonce

> L'information genetique circule toujours dans le meme sens :
> ADN → ARN → Proteine

**Formule par Francis Crick (1958)**

### Les flux d'information

**Flux normal** :
```
ADN ─(transcription)→ ARN ─(traduction)→ Proteine
```

**Details** :
- **Transcription** : ADN → ARN (dans le noyau, eucaryotes)
- **Traduction** : ARN → Proteine (dans le cytoplasme)
- Sens unique : proteine ne peut pas redevenir ADN/ARN

### Le dogme est-il toujours vrai ?

**Exceptions connues** :

**1. Transcription inverse** :
- Certains virus (retrovirus) : ARN → ADN
- Enzyme : transcriptase inverse
- Exemple : VIH

**2. Replication de l'ARN** :
- Certains virus a ARN : ARN → ARN
- Sans passer par ADN

**3. ARN non traduits** :
- rRNA, tRNA, miRNA, etc.
- Ne deviennent pas des proteines
- Mais ont des fonctions importantes

**Conclusion** :
- Le dogme reste une excellente approximation
- Couvre la vaste majorite des cas
- Base fondamentale de la biologie moleculaire

---

## Definition d'un gene

### Concept moderne de gene

**Definition** :
- **Intervalle d'ADN (ou d'ARN)** qui code pour une proteine
- Ou plus largement : sequence qui code pour un produit fonctionnel (proteine ou ARN)
- Unite de l'heredite

### Caracteristiques

**Structure d'un gene (eucaryotes)** :
```
Promoteur - [Exon1 - Intron1 - Exon2 - Intron2 - Exon3] - Terminateur
            └────────────────┬──────────────────┘
                    Sequence codante (CDS)
```

**Elements importants** :
- **Promoteur** : region de regulation (ou commence la transcription)
- **Exons** : sequences codantes (gardees apres epissage)
- **Introns** : sequences non codantes (enlevees par epissage)
- **Terminateur** : signal de fin de transcription

### Pourquoi les genes sont importants

**Creation de proteines** :
- Les proteines dirigent tous les processus cellulaires
- Genes differents → proteines differentes → fonctions differentes

**Differenciation des organismes** :
- Differences genetiques entre especes
- Differences entre individus d'une meme espece
- Base moleculaire de la biodiversite

**Heredite** :
- Les genes se transmettent de parents a descendants
- Base moleculaire des traits hereditaires
- Variation et selection evolutive

### Genes vs Genome

**Gene** :
- Une unite fonctionnelle
- Code pour une proteine (ou ARN fonctionnel)
- Taille variable (centaines a millions de bases)

**Genome** :
- Ensemble de TOUS les genes d'un organisme
- + sequences non codantes
- Genome humain : ~20000-25000 genes

---

## La table du code genetique

### Organisation

**64 codons au total** :
- 61 codent pour des acides amines
- 3 codons stop (UAA, UAG, UGA)
- 1 codon start/Met (AUG)

### Lecture de la table

**Format standard** :
```
Premiere base (5') | Deuxieme base | Troisieme base (3')
```

**Exemple : GCA = Alanine**
- G (premiere position)
- C (deuxieme position)
- A (troisieme position)
- → Ala (A)

### Proprietes du code

**Wobble (vacillement)** :
- Troisieme position moins critique
- Plusieurs codons avec memes 2 premieres bases → meme acide amine
- Exemple : GCU, GCC, GCA, GCG → tous Alanine

**Codons preferentiels** :
- Certains organismes preferent certains codons
- "Codon usage bias"
- Important pour expression de proteines recombinantes

**Conservation** :
- Codons pour acides amines similaires souvent proches
- Mutations moins deleteres
- Exemple : UUU et UUC (tous deux Phe)

---

## Points cles a retenir

### Proteines et acides amines
- Proteines = polymeres d'acides amines
- 20 acides amines standards
- Structure primaire = ordre des acides amines
- Polypeptide = chaine d'acides amines

### Code genetique
- 3 bases ARN (codon) = 1 acide amine
- 64 codons possibles (4^3)
- Code degenere (redondant)
- Quasi-universel

### Codons speciaux
- Start : AUG (Met)
- Stop : UAA, UAG, UGA
- Debut et fin de traduction

### Traduction
- ARNm + Ribosome + tRNA → Proteine
- tRNA : anticodon + acide amine
- Initiation → Elongation → Terminaison
- Direction : 5' → 3' de l'ARNm

### Dogme central
- ADN → ARN → Proteine
- Flux unidirectionnel (generalement)
- Transcription puis traduction

### Gene
- Intervalle d'ADN codant pour proteine
- Base de l'heredite
- Differentie les organismes

---

## Auto-evaluation

### Questions rapides

1. Combien d'acides amines standards existe-t-il ?
2. Qu'est-ce qu'un codon ?
3. Pourquoi le code genetique est-il degenere ?
4. Quel est le codon start ?
5. Combien de codons stop existent ?
6. Qu'est-ce qu'un tRNA ?
7. Quel est le role du ribosome ?
8. Dans quel sens le ribosome lit-il l'ARNm ?
9. Qu'est-ce que le dogme central ?
10. Qu'est-ce qu'un gene ?
11. Combien de codons differents existent ?
12. Que signifie "codon non-sens" ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. 20 acides amines standards
2. Sequence de 3 nucleotides d'ARN qui code pour un acide amine
3. 64 codons pour 20 acides amines → plusieurs codons par acide amine
4. AUG (code aussi pour Methionine)
5. 3 codons stop : UAA, UAG, UGA
6. ARN de transfert : apporte les acides amines, possede un anticodon
7. Realise la traduction (ARNm → proteine)
8. 5' → 3' (sens de synthese de la proteine)
9. ADN → ARN → Proteine (flux unidirectionnel de l'information)
10. Intervalle d'ADN (ou ARN) qui code pour une proteine ou un ARN fonctionnel
11. 64 codons (4^3)
12. Codon stop (UAA, UAG, UGA) qui ne code pas pour un acide amine
</details>

---

## Mnemoniques

**Nombre d'acides amines** : "**V**ingt **A**cides **A**menes" (20)

**Codon** : "**T**rois **B**ases **U**nies" (3 bases = 1 codon)

**Codon start** : "**A**lways **U**se **M**ethionine" (AUG)

**Codons stop** : "**U** **A**rrete **A**vec **U**A**A**, **U**A**G**, **U**G**A**"
- Ou : "**U** **A**lways **S**tops" (tous commencent par U, ont un A)

**tRNA** : "**T**ransporte, **R**econnait avec **A**nticodon"

**Dogme central** : "**D**e l'**A**DN a l'**A**RN a l'**A**cide amine" (D-A-A-A)

**Traduction** : "**R**ibosome **L**it, **T**ransfert **A**pporte" (Ribosome + tRNA)

**Redondance** : "**P**lusieurs **C**odons, **M**eme **A**cide" (PCMA)

**Direction** : "**C**inq vers **T**rois" (5' → 3')

---

## Lien avec la bio-informatique

### Applications pratiques

**1. Traduction in silico**
- Convertir sequence nucleotidique en sequence proteique
- Identifier cadres de lecture (ORF - Open Reading Frame)
- 6 cadres possibles (3 sens + 3 sens complementaire)

**2. Annotation de genomes**
- Predire les genes dans un genome sequence
- Identifier start (ATG/AUG) et stop
- Algorithmes : GeneMark, Glimmer, Prodigal

**3. Analyse de sequences proteiques**
- Recherche de similarite (BLAST proteique)
- Alignement de sequences proteiques
- Prediction de fonction

**4. Codon usage bias**
- Analyser preferences de codons d'un organisme
- Optimiser sequences pour expression heterologue
- Outils : CodonW, GCUA

**5. Prediction de structure proteique**
- Structure secondaire (helices, feuillets)
- Structure tertiaire (repliement 3D)
- AlphaFold, Rosetta

**6. Proteomique computationnelle**
- Identification de proteines par spectrometrie de masse
- Matching peptides observes vs sequences predites
- Quantification d'expression proteique

**7. Biologie synthetique**
- Design de genes synthetiques
- Optimisation de codons
- Construction de circuits genetiques

### Algorithmes lies

**Simples** :
- Traduction d'ARN en proteine
- Recherche de motifs proteiques
- Comptage de codons

**Intermediaires** :
- Identification d'ORF
- Alignement de sequences proteiques
- Prediction de domaines

**Avances** :
- Annotation automatique de genomes
- Prediction de structure 3D
- Phylogenie basee sur proteines

---

## Exercices pratiques

### Exercice 1 : Traduction simple
Traduire l'ARNm suivant en proteine :
```
5' - AUGUGGCAUUGA - 3'
```

<details>
<summary>Indice</summary>
Decoupe en codons de 3 bases. Cherche chaque codon dans la table. AUG est le start.
</details>

### Exercice 2 : Identification des codons
Dans la sequence suivante, identifier :
- Le codon start
- Les codons stop potentiels
```
5' - GCAUGCUAGUGAUAAGCUGA - 3'
```

<details>
<summary>Indice</summary>
AUG = start. UAA, UAG, UGA = stop. Scanne la sequence.
</details>

### Exercice 3 : Cadres de lecture (ORF)
Combien de cadres de lecture possibles pour une sequence d'ADN double brin ?

<details>
<summary>Indice</summary>
3 cadres par brin (debut position 1, 2, ou 3). Combien de brins ?
</details>

### Exercice 4 : Anticodon
Quel est l'anticodon du tRNA qui reconnait le codon 5'-GCA-3' ?

<details>
<summary>Indice</summary>
Anticodon est antiparallele et complementaire. G↔C, A↔U. Inverse la direction.
</details>

### Exercice 5 : Redondance du code
Combien de codons differents peuvent coder pour la Leucine ?

<details>
<summary>Indice</summary>
Consulte la table du code genetique (lien Rosalind fourni). Compte tous les codons → Leu.
</details>

### Exercice 6 : Mutation et consequence
Une mutation change AUG en AUA dans un ARNm. Quel est l'effet ?

<details>
<summary>Indice</summary>
AUG = start (Met). AUA = Ile. Que se passe-t-il si le start disparait ?
</details>

---

## Problemes Rosalind associes

### Proteines

**Translating RNA into Protein (PROT)**
- Traduire une sequence ARN en sequence proteique
- Utiliser la table du code genetique
- S'arreter au premier codon stop

**Conseils** :
- Decoupe l'ARN en codons de 3 bases
- Utilise un dictionnaire codon → acide amine
- Gere les codons stop correctement

### Cadres de lecture

**Open Reading Frames (ORF)**
- Trouver tous les ORF dans une sequence ADN
- 6 cadres de lecture possibles
- Identifier start (ATG) et stop

**Conseils** :
- Genere les 6 sequences (3 sens + 3 reverse complement)
- Pour chaque cadre, cherche ATG puis stop
- Retourne sequences proteiques uniques

### Autres problemes lies

**Finding a Protein Motif (MPRT)**
- Rechercher motifs dans sequences proteiques
- Utilise bases de donnees (UniProt)
- Expressions regulieres pour motifs

**Inferring mRNA from Protein (MRNA)**
- Nombre d'ARN possibles pour une proteine donnee
- Compte les codons possibles par acide amine
- Multiplication des possibilites

---

## Pour aller plus loin

### Lectures recommandees

**Livres** :
- "The Eighth Day of Creation" (Horace Freeland Judson)
  - Histoire de la decouverte du code genetique
  - Recits des scientifiques impliques
  
- "Life's Greatest Secret" (Matthew Cobb)
  - Histoire du code genetique
  - Decouvertes cles et controverses
  
- "Molecular Biology of the Cell" (Alberts et al.)
  - Chapitre 6 : "How Cells Read the Genome"
  - Reference academique complete
  
- "The Genetic Code" (Brian F.C. Clark)
  - Livre specialise sur le code genetique
  - Aspects historiques et moleculaires

**Articles scientifiques classiques** :
- Crick, F. (1958) "On Protein Synthesis"
  - Article fondateur sur le dogme central
  
- Nirenberg & Matthaei (1961) "The dependence of cell-free protein synthesis in E. coli upon naturally occurring or synthetic polyribonucleotides"
  - Premier dechiffrage du code genetique
  
- Crick et al. (1961) "General nature of the genetic code for proteins"
  - Nature triplet du code

### Ressources en ligne

**Cours et tutoriels** :
- Khan Academy : "Translation" et "Genetic Code"
  - Videos explicatives claires
  - Exercices interactifs
  
- MIT OpenCourseWare : 7.01 Introduction to Biology
  - Cours complets avec notes
  - Focus sur biologie moleculaire
  
- NCBI Genetic Code Tables
  - Tables officielles avec toutes les variations
  - https://www.ncbi.nlm.nih.gov/Taxonomy/Utils/wprintgc.cgi
  
- Rosalind.info : RNA Codon Table
  - https://rosalind.info/glossary/rna-codon-table/
  - Table interactive pour exercices

**Outils interactifs** :
- ExPASy Translate Tool
  - Traduction en ligne de sequences
  - Visualisation des 6 cadres de lecture
  
- DNA to Protein Translation (biologydatabase.com)
  - Outil pedagogique simple
  
- 3D Molecular Designs : Genetic Code Kit
  - Simulation interactive du code genetique

**Videos educatives** :
- DNA Learning Center (Cold Spring Harbor)
  - Animations 3D du processus de traduction
  
- iBiology : "The Genetic Code" par Venki Ramakrishnan
  - Seminaire par Prix Nobel
  
- Crash Course Biology : "Protein Synthesis"
  - Vulgarisation accessible

### Bases de donnees

**Sequences proteiques** :
- **UniProt** (www.uniprot.org)
  - Base mondiale de sequences proteiques
  - Annotations fonctionnelles
  
- **PDB** (Protein Data Bank)
  - Structures 3D de proteines
  - Visualisation interactive
  
- **Pfam**
  - Familles de domaines proteiques
  - Motifs conserves

**Code genetique** :
- **NCBI Genetic Codes**
  - Toutes les variations du code
  - Codes mitochondriaux, etc.

### Exercices pratiques

**Niveau debutant** :
1. Traduire manuellement 10 sequences ARN courtes
2. Identifier tous les ORF dans une petite sequence
3. Compter les codons pour chaque acide amine dans un gene
4. Trouver mutations silencieuses vs faux-sens

**Niveau intermediaire** :
1. Implemente un traducteur ARN → Proteine en Python
2. Ecris un detecteur d'ORF (6 cadres de lecture)
3. Analyse le codon usage d'un genome bacterien
4. Compare sequences proteiques orthologues

**Niveau avance** :
1. Optimise une sequence pour expression dans E. coli
2. Predis l'effet de mutations sur la proteine
3. Analyse proteomique : identifie proteines par masse
4. Simule evolution de sequences proteiques

**Projets Rosalind** :
- PROT : Translating RNA into Protein
- ORF : Open Reading Frames
- MPRT : Finding a Protein Motif
- MRNA : Inferring mRNA from Protein
- SPLC : RNA Splicing (combine transcription + traduction)

### Concepts avances a explorer

**Epigenetique de la traduction** :
- Modifications post-traductionnelles
- Controle de l'initiation
- Regulation par miRNA

**Evolution du code genetique** :
- Pourquoi ce code et pas un autre ?
- Robustesse aux mutations
- Codes genetiques alternatifs

**Biologie synthetique** :
- Expansion du code genetique
- Acides amines non naturels
- Ribosomes orthogonaux

**Proteomique** :
- Spectrometrie de masse
- Quantification d'expression
- Interactions proteine-proteine

---

## Perspectives historiques

### Decouverte du code genetique (1950-1966)

**Questions fondamentales** :
- Comment 4 bases codent-elles pour 20 acides amines ?
- Le code est-il universel ?
- Comment les cellules lisent-elles le code ?

**Experiences cles** :

**1. Nirenberg & Matthaei (1961)** :
- Systeme de synthese proteique in vitro
- ARN synthetique poly-U → polypeptide Phe
- Premier codon dechiffre : UUU = Phenylalanine
- "The experiment that broke the genetic code"

**2. Khorana (1960s)** :
- Synthese d'ARN avec sequences repetees
- Confirmation de la nature triplet
- Dechiffrage de nombreux codons

**3. Crick et al. (1961)** :
- Mutations frameshift dans bacteriophage
- Preuve que le code est lu par triplets
- Pas de virgules entre codons

**4. Completude (1966)** :
- Dechiffrage complet des 64 codons
- Identification des codons stop
- Universalite demontree

**Prix Nobel associes** :
- 1968 : Nirenberg, Khorana, Holley
  - "For their interpretation of the genetic code"

---

## Notes importantes

### Differences procaryotes vs eucaryotes

**Procaryotes** :
- Traduction commence pendant transcription
- Pas de maturation d'ARN
- Premier acide amine : formyl-methionine (fMet)
- Ribosomes 70S

**Eucaryotes** :
- Traduction separee (cytoplasme)
- Maturation d'ARN (cap, queue poly-A, epissage)
- Premier acide amine : methionine (Met)
- Ribosomes 80S

### Modifications post-traductionnelles

**Apres traduction** :
- Proteines peuvent etre modifiees
- Phosphorylation, acetylation, methylation
- Clivage de sequences signal
- Repliement assiste (chaperones)
- Ces modifications changent la fonction

**Importance** :
- Meme sequence → differentes formes actives
- Regulation fine de l'activite
- Augmente diversite fonctionnelle

---

**Felicitations !** Tu maitrises maintenant :
- Le code genetique et les codons
- Le processus de traduction
- Le role des proteines
- Le dogme central de la biologie moleculaire

**Ces concepts sont essentiels pour** :
- Annotation de genomes
- Analyse de sequences proteiques
- Proteomique
- Biologie synthetique
- Comprehension des mutations genetiques

**Prochaine fiche suggeree** : Structure des proteines (secondaire, tertiaire, quaternaire)
