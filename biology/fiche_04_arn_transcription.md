# Fiche 04 : ARN et transcription

**Date de creation** : 14 novembre 2025  
**Sujet** : Structure de l'ARN, types d'ARN, processus de transcription

---

## ARN (Acide RiboNucleique)

### Composition

**Sucre** : Ribose (different de l'ADN qui a desoxyribose)

**4 bases azotees** :
- **A** : Adenine
- **C** : Cytosine
- **G** : Guanine
- **U** : Uracile (remplace la thymine !)

### Differences cles avec l'ADN

| Caracteristique | ADN | ARN |
|-----------------|-----|-----|
| **Sucre** | Desoxyribose | Ribose |
| **Bases** | A, C, G, **T** | A, C, G, **U** |
| **Structure** | Double brin (2 brins antiparalleles) | Simple brin (generalement) |
| **Forme 3D** | Double helice | Variable selon le type |
| **Unite de longueur** | Paire de bases (bp) | Nucleotides (nt) |
| **Appariement** | A-T, C-G | Peut former structures secondaires locales |
| **Localisation (eucaryotes)** | Noyau uniquement | Noyau + Cytoplasme |
| **Fonction** | Stockage information genetique | Execution des instructions |
| **Stabilite** | Tres stable (double helice) | Moins stable |
| **Duree de vie** | Permanente (sauf mutations) | Temporaire (degradation) |

### Pourquoi Uracile au lieu de Thymine ?

**Raisons chimiques** :
- Thymine = Uracile + groupe methyle (-CH3)
- Synthese de thymine coute plus d'energie
- ARN : molecules temporaires → pas besoin de stabilite maximale
- ADN : stockage permanent → thymine plus stable

**Avantage evolutif** :
- Cytosine peut se desaminer spontanement en Uracile
- Dans l'ADN : Uracile = erreur detectable
- Dans l'ARN : Uracile = normal
- Permet systeme de reparation de l'ADN

---

## Types d'ARN

### ARN messager (mRNA)

**Fonction** :
- Porte les instructions genetiques de l'ADN
- Intermediaire entre ADN (noyau) et proteines (cytoplasme)
- Traduit en proteine par les ribosomes

**Caracteristiques** :
- Simple brin
- Relativement long
- Duree de vie variable (minutes a heures)
- Peut sortir du noyau (eucaryotes)

**Structure (eucaryotes)** :
- 5' cap (coiffe)
- Sequence codante (CDS - Coding Sequence)
- 3' poly(A) tail (queue)

### ARN de transfert (tRNA)

**Fonction** :
- Transporte les acides amines vers le ribosome
- "Adaptateur" entre sequence ARN et acide amine
- Chaque tRNA reconnait un codon specifique

**Caracteristiques** :
- Tres court (~75-95 nucleotides)
- Structure en "feuille de trefle" (2D)
- Structure en "L" (3D)
- Contient des bases modifiees

**Parties importantes** :
- Anticodon : reconnait le codon du mRNA
- Site d'attachement de l'acide amine

### ARN ribosomal (rRNA)

**Fonction** :
- Composant structural des ribosomes
- Catalyse la formation des liaisons peptidiques
- Le plus abondant (~80% de l'ARN cellulaire)

**Caracteristiques** :
- Plusieurs types (18S, 28S, 5.8S, 5S chez eucaryotes)
- Structure secondaire et tertiaire complexe
- Tres stable
- Evolue lentement → utile pour phylogenie

### Autres types d'ARN

**ARN nucleaire petit (snRNA)** :
- Implique dans l'epissage
- Partie des spliceosomes
- ~100-300 nucleotides

**MicroARN (miRNA)** :
- Regulation de l'expression genique
- ~21-23 nucleotides
- Se lie au mRNA pour bloquer traduction

**ARN long non codant (lncRNA)** :
- >200 nucleotides
- Roles regulatoires varies
- Domaine de recherche actif

---

## La transcription

### Definition
Processus de creation d'un brin d'ARN messager a partir d'un brin d'ADN

### Vue d'ensemble

**Input** : ADN (gene)  
**Output** : ARN messager (mRNA)  
**Enzyme** : ARN polymerase  
**Lieu** : Noyau (eucaryotes), Cytoplasme (procaryotes)

### Mecanisme detaille

**Etape 1 : Initiation**
- ARN polymerase se lie au promoteur
- Double helice d'ADN se deroule localement
- Creation d'une "bulle de transcription"

**Etape 2 : Elongation**
- ARN polymerase lit l'ADN 3' → 5'
- Synthetise l'ARN 5' → 3'
- Copie nucleotide par nucleotide
- **Substitution** : Uracile (U) au lieu de Thymine (T)

**Etape 3 : Terminaison**
- ARN polymerase atteint sequence de terminaison
- ARN se detache
- ADN se referme

### Regles de correspondance

```
Brin template ADN → ARN transcrit
 A          →       U
 T          →       A
 G          →       C
 C          →       G
```

### Exemple de transcription

**ADN (brin template, 3'→5')** :
```
3' - TACGATCGATCG - 5'
```

**ARN (5'→3')** :
```
5' - AUGCUAGCUAGC - 3'
```

**Remarques** :
- Brin template : 3'→5' (sens de lecture)
- ARN synthetise : 5'→3' (sens de synthese)
- T remplace par U

### Notation importante

**Brin codant vs brin template** :
- **Brin template** (antisens) : lu par ARN polymerase
- **Brin codant** (sens) : meme sequence que l'ARN (sauf T→U)

**Exemple** :
```
Brin codant     : 5' - ATGCTAGCTAGC - 3'
Brin template   : 3' - TACGATCGATCG - 5'
ARN transcrit   : 5' - AUGCUAGCUAGC - 3'
```

L'ARN a la meme sequence que le brin codant (sauf T→U) !

---

## Differences procaryotes vs eucaryotes

### Chez les procaryotes

**Simplicite** :
- Transcription et traduction couplees
- Pas d'introns (generalement)
- mRNA utilise immediatement
- Pas de maturation

**Organisation** :
- Genes en operons (plusieurs genes sur un mRNA)
- Regulation simple
- ARN polymerase unique

### Chez les eucaryotes

**Complexite** :
- Transcription (noyau) separee de traduction (cytoplasme)
- Introns et exons
- Maturation du mRNA necessaire
- Epissage alternatif possible

**Maturation du mRNA** :
1. **Capping** : ajout de 5' cap
2. **Polyadenylation** : ajout de queue poly(A)
3. **Epissage** : elimination des introns

**Organisation** :
- Un gene = un mRNA (generalement)
- Regulation complexe
- 3 ARN polymerases (I, II, III)

---

## Epissage (Splicing)

### Definition
- Elimination des **introns** (sequences non codantes)
- Conservation des **exons** (sequences codantes)
- Produit mRNA mature

### Processus
```
Pre-mRNA :  Exon1 - Intron1 - Exon2 - Intron2 - Exon3
                ↓ epissage
mRNA mature :  Exon1 - Exon2 - Exon3
```

### Epissage alternatif
- Memes exons combines differemment
- Un gene → plusieurs proteines differentes
- Augmente la diversite proteique
- ~95% des genes humains utilisent l'epissage alternatif

**Exemple** :
```
Gene : Exon1 - Exon2 - Exon3 - Exon4

Variant 1 : Exon1 - Exon2 - Exon3 - Exon4
Variant 2 : Exon1 - Exon3 - Exon4
Variant 3 : Exon1 - Exon2 - Exon4
```

---

## Points cles a retenir

### ARN
- 4 bases : A, C, G, U (pas de T !)
- Sucre : ribose
- Peut sortir du noyau
- Execute les instructions
- Simple brin (generalement)

### Types d'ARN
- **mRNA** : messager (instructions)
- **tRNA** : transfert (transport acides amines)
- **rRNA** : ribosomal (catalyse)

### Transcription
- ADN → ARN messager
- Copie nucleotide par nucleotide
- T remplace par U
- ARN polymerase lit 3'→5', synthetise 5'→3'

### Differences ADN/ARN
- Sucre different (desoxy vs ribo)
- Bases differentes (T vs U)
- Structure (double vs simple)
- Localisation (noyau vs noyau+cytoplasme)

### Eucaryotes specifique
- Maturation du mRNA
- Epissage des introns
- Epissage alternatif

---

## Auto-evaluation

### Questions rapides

1. Quelle est la difference de sucre entre ADN et ARN ?
2. Quelle base de l'ADN est remplacee dans l'ARN ?
3. Qu'est-ce que la transcription ?
4. Quels sont les trois types principaux d'ARN ?
5. Quel type d'ARN peut sortir du noyau ?
6. Qu'est-ce que l'epissage ?
7. Dans quel sens l'ARN polymerase lit-elle l'ADN ?
8. Quelle est la fonction du mRNA ?
9. Pourquoi l'ARN utilise-t-il l'uracile au lieu de la thymine ?
10. Qu'est-ce que l'epissage alternatif ?

### Reponses

<details>
<summary>Cliquer pour voir les reponses</summary>

1. ADN = desoxyribose, ARN = ribose
2. Thymine (T) → Uracile (U)
3. Creation d'ARN messager a partir d'un modele ADN
4. mRNA (messager), tRNA (transfert), rRNA (ribosomal)
5. mRNA (chez les eucaryotes)
6. Elimination des introns et conservation des exons
7. 3' → 5' (et synthetise l'ARN 5' → 3')
8. Porter les instructions genetiques de l'ADN vers les ribosomes
9. Synthese plus simple, molecules temporaires, systeme de reparation ADN
10. Combinaison differente des exons pour produire plusieurs proteines a partir d'un gene
</details>

---

## Mnemoniques

**Bases ARN** : "**A** **C**T **G**rand **U**nivers"
- Adenine, Cytosine, Guanine, Uracile

**Sucre** :
- ARN = **R**ibose**R**NA
- ADN = **D**esoxy**D**NA

**Localisation** :
- ADN = **D**ans le noyau
- ARN = **R**ode dans la cellule

**Types d'ARN** : "**M**arie **T**ransforme **R**ien"
- **M**essager, **T**ransfert, **R**ibosomal

**Transcription** : "**T**hymine **U**sed, **U**racile **T**ranscrit"
- Dans l'ADN, T ; dans l'ARN transcrit, U

**Epissage** : "**E**xons **E**xprimes, **I**ntrons **I**gnores"

---

## Lien avec la bio-informatique

### Transcriptomique
- Sequencage de tous les ARN d'une cellule (RNA-seq)
- Mesure l'expression genique
- Identifie genes actifs vs inactifs
- Detecte epissage alternatif

### Prediction de structures
- Structure secondaire d'ARN
- Appariement de bases locaux
- Algorithmes : Nussinov, Zuker
- Calcul d'energie libre

### Annotation de genomes
- Identifier les genes (CDS)
- Predire les introns/exons
- Detecter les sites d'epissage
- Algorithmes : GeneMark, Augustus

### Alignement RNA-seq
- Mapper les reads sur le genome
- Gerer les jonctions d'epissage
- Outils : STAR, HISAT2, TopHat

### Quantification d'expression
- Compter les reads par gene
- Normalisation (RPKM, FPKM, TPM)
- Analyse differentielle
- Outils : DESeq2, edgeR

### Design de primers
- Creer sequences complementaires
- RT-PCR, qPCR
- Eviter structures secondaires
- Specificite base sur transcrit

---

## Exercices pratiques

### Exercice 1 : Transcription simple
Transcrire le brin template suivant en ARN :
```
ADN template : 3' - TACGATCG - 5'
```

**Indice** : L'ARN polymerase lit 3'->5' et synthetise 5'->3'. Remplace T par U.

### Exercice 2 : Identification brin codant
Soit l'ARN : 5' - AUGCUAGC - 3'
Quel est le brin codant de l'ADN ?

**Indice** : Le brin codant a la meme sequence que l'ARN, sauf U->T.

### Exercice 3 : Epissage
Pre-mRNA : Exon1(100nt) - Intron1(500nt) - Exon2(150nt) - Intron2(300nt) - Exon3(200nt)
Quelle est la longueur du mRNA mature ?

**Indice** : Les introns sont enleves, seuls les exons restent.

### Exercice 4 : Comparaison ADN/ARN
Sequence ADN (brin codant) : 5' - ATGCTAGCTAGC - 3'
Quelle est la sequence du mRNA transcrit ?

**Indice** : Identique au brin codant, mais remplace T par U.

### Cas de tests (avec reponses attendues)

**Test 1 - Transcription simple** :
- Input : ADN template : 3' - TACGATCG - 5'
- Output attendu : ARN : 5' - AUGCUAGC - 3'

**Test 2 - Brin codant** :
- Input : ARN : 5' - AUGCUAGC - 3'
- Output attendu : Brin codant : 5' - ATGCTAGC - 3'

**Test 3 - Longueur apres epissage** :
- Input : Exon1(100nt) + Intron1(500nt) + Exon2(150nt) + Intron2(300nt) + Exon3(200nt)
- Output attendu : 450 nucleotides (100+150+200)

**Test 4 - Conversion ADN->ARN** :
- Input : ADN codant : 5' - ATGCTAGCTAGC - 3'
- Output attendu : mRNA : 5' - AUGCUAGCUAGC - 3'

**Test 5 - Bases differentes** :
- Input : Sequence ADN : "ATCG"
- Output attendu : Nombre de T dans ADN = 1, Nombre de U dans ARN = 1

---

## Pour aller plus loin

### Lectures recommandees

**Livres** :
- "RNA Worlds" (Gesteland et al.) - Le monde de l'ARN
- "The RNA World" (Atkins et al.) - Theorie du monde a ARN
- "Molecular Biology" (Weaver) - Chapitres sur transcription
- "Genes" (Lewin) - Transcription et traduction

**Articles scientifiques** :
- Crick (1970) : "Central dogma of molecular biology"
- Gilbert (1986) : "The RNA World" - Hypothese monde a ARN
- Sharp (1993) : "Split genes and RNA splicing" - Prix Nobel
- Fire & Mello (1998) : "RNA interference" - Prix Nobel 2006

### Ressources en ligne

**Cours et videos** :
- Khan Academy : "Transcription and mRNA processing"
- MIT OpenCourseWare : 7.01SC - Transcription
- iBiology : "RNA processing and splicing"
- HHMI BioInteractive : "From DNA to RNA"

**Outils en ligne** :
- ExPASy Translate : Convertir ADN/ARN/Proteine
- NCBI ORF Finder : Trouver cadres de lecture
- RNAfold : Predire structure secondaire ARN
- SpliceAid : Base de donnees sites d'epissage

**Bases de donnees** :
- RNAcentral : Base de donnees ARN non-codants
- miRBase : Base de donnees microARN
- Rfam : Familles d'ARN
- ENCODE : Donnees transcriptomiques

**Tutoriels bio-informatique** :
- Rosalind.info : Probleme RNA (Transcribing DNA into RNA)
- BioPython Seq.transcribe() : Documentation
- RNA-seq tutorial : Analyse de donnees transcriptomiques

### Exercices pratiques

**Exercice bio-informatique 1 : Implementer transcription** :
Ecris une fonction Python pour transcrire ADN en ARN.
```python
def transcribe(dna):
    # A implementer
    # Remplace tous les T par des U
    pass

# Tests
print(transcribe("ATCG"))  # Devrait afficher "AUCG"
print(transcribe("TACG"))  # Devrait afficher "UACG"
```

**Exercice bio-informatique 2 : Transcription inverse** :
Ecris une fonction pour convertir ARN en ADN.
```python
def reverse_transcribe(rna):
    # A implementer
    # Remplace tous les U par des T
    pass

# Test
print(reverse_transcribe("AUCG"))  # Devrait afficher "ATCG"
```

**Exercice bio-informatique 3 : Detecter introns** :
Ecris une fonction qui detecte si une sequence contient des sites consensus d'epissage (GT...AG).
```python
def find_introns(dna):
    # A implementer
    # Trouve toutes les sequences qui commencent par GT et finissent par AG
    pass
```

**Exercice theorique 4 : Types d'ARN** :
Liste 5 differences entre mRNA, tRNA et rRNA en termes de fonction, structure et localisation.

**Exercice pratique 5 : Epissage alternatif** :
Soit un gene avec 4 exons. Combien de transcripts differents peut-on theoriquement generer par epissage alternatif ?

**Indice** : Chaque exon peut etre inclus ou exclu (sauf le premier et le dernier generalement).

**Exercice Rosalind 6** :
Resous les problemes suivants sur Rosalind.info :
1. RNA : Transcribing DNA into RNA
2. SPLC : RNA Splicing (plus avance)

**Exercice avance 7 : Structure secondaire** :
Pour la sequence ARN : 5' - GCGCAUGCGC - 3'
Dessine une structure secondaire possible (appariements de bases).

**Indice** : L'ARN peut se replier sur lui-meme avec appariements A-U et C-G.

**Exercice avance 8 : RNA-seq** :
Si tu sequences un transcriptome et obtiens 1000 reads pour le gene A et 100 reads pour le gene B, que peux-tu en deduire ?

**Indice** : Pense a l'expression genique relative.

---

## Problemes Rosalind associes

**Transcribing DNA into RNA (RNA)**
- Convertir sequence ADN en ARN
- Remplacer tous les T par des U
- Input : sequence ADN
- Output : sequence ARN

**Splicing out Introns (SPLC)**
- Simuler l'epissage
- Enlever les introns, garder les exons
- Input : sequence ADN + positions introns
- Output : sequence proteique apres traduction

---

## Prochaines etapes d'apprentissage

1. **Traduction** : ARN -> Proteine
2. **Code genetique** : codons et acides amines
3. **Structure des proteines** : primaire, secondaire, tertiaire
4. **Regulation de l'expression genique**
5. **Epigenetique** : regulation sans changement de sequence

---

**Felicitations !** Tu as maintenant une comprehension solide des bases de la biologie moleculaire necessaires pour la bio-informatique.
