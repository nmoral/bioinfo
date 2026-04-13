# Fiche 08 : Vocabulaire fondamental du sequencage

**Date de creation** : 12 avril 2026
**Sujet** : Comprendre les termes cles du sequencage ADN

**Prerequis** : Fiche 02 (Structure de l'ADN)

---

## Pourquoi cette fiche ?

Quand tu lis un article de bioinformatique, tu tombes sur des phrases comme :
"l'hybridation d'une amorce qui sert de point de depart pour le sequencage"

Cette fiche te donne les definitions dans l'ordre logique pour que ces phrases deviennent lisibles.

---

## 1. Le probleme de depart : comment lire de l'ADN ?

L'ADN est une molecule chimique. Un sequenceur ne "lit" pas directement les bases comme on lit un texte. Il doit :

1. Preparer l'ADN (le couper, le copier, le marquer)
2. Detecter un signal physique (lumiere, courant electrique)
3. Convertir ce signal en lettres A, C, G, T

Chaque generation de sequenceurs resout ce probleme differemment.

---

## 2. Vocabulaire de preparation

### Fragment
**Ce que c'est** : un morceau d'ADN decoupes depuis le genome original.

Un genome est trop long pour etre lu en une seule fois. On le coupe en
milliers de petits morceaux : ce sont les fragments.

```
Genome original :
ATCGATCGATCGATCG...ATCGATCG  (milliards de bases)

Apres fragmentation :
[ATCGAT]  [CGATCG]  [ATCGAT]  ...  (centaines de bases chacun)
```

**Taille typique** :
- Illumina (short reads) : 150-300 bases par fragment
- Nanopore (long reads)  : 1000 a plusieurs millions de bases

---

### Amorce (primer)
**Ce que c'est** : un court brin d'ADN synthetique (fabrique en laboratoire)
qui se colle sur le fragment a sequencer pour servir de point de depart.

**Pourquoi c'est necessaire** : l'enzyme qui copie l'ADN (l'ADN polymerase)
ne peut pas commencer toute seule. Elle a besoin d'un point d'ancrage.
L'amorce est ce point d'ancrage.

**Analogie** : imagine que tu veux remplir un tunnel de voitures. Tu as besoin
d'une premiere voiture pour que les autres puissent s'accrocher derriere.
L'amorce, c'est cette premiere voiture.

```
Fragment a lire :
3' - TAGCTAGCTAGC - 5'

Amorce (courte, synthetique) :
        5' - ATCG - 3'
             ||||
3' - TAGCTAGCTAGC - 5'

L'enzyme continue a partir de la fleche -->
             5' - ATCGATCGATCG - 3'  (nouveau brin construit)
```

---

### Hybridation
**Ce que c'est** : le processus par lequel deux brins d'ADN complementaires
se collent ensemble.

Tu connais deja la complementarite : A s'apparie avec T, C avec G (Fiche 02).
L'hybridation, c'est ce collage qui se produit spontanement quand deux brins
complementaires se rencontrent en solution.

**C'est le mecanisme cle de presque toute la biologie moleculaire.**

```
Brin 1 :  5' - A T C G A T C G - 3'
               | | | | | | | |
Brin 2 :  3' - T A G C T A G C - 5'

Ces deux brins "s'hybrident" = se collent ensemble
```

**Dans le contexte du sequencage** :
"l'hybridation d'une amorce" = l'amorce synthetique se colle sur le fragment
d'ADN a l'endroit dont elle est le complement. Elle sert ensuite de point de
depart pour que l'enzyme commence a copier.

---

### Amplification / PCR
**Ce que c'est** : PCR = Polymerase Chain Reaction.
Processus qui permet de faire des millions de copies identiques d'un fragment.

**Pourquoi amplifier** : un seul fragment d'ADN ne genere pas assez de signal
pour etre detecte. Il faut des millions de copies identiques pour avoir un
signal lisible.

**Comment ca marche (simplifie)** :
```
Etape 1 : chauffer -> les deux brins se separent
Etape 2 : refroidir -> les amorces s'hybrident
Etape 3 : l'enzyme copie chaque brin
Etape 4 : recommencer -> les copies se dupliquent a leur tour

Cycle 1  : 1 fragment -> 2 copies
Cycle 2  : 2 copies   -> 4 copies
Cycle 10 : -> environ 1000 copies
Cycle 30 : -> plus d'un milliard de copies
```

**Note importante** :
Nanopore ne necessite PAS d'amplification. C'est un de ses avantages majeurs :
pas de biais introduit par la PCR, lecture directe du brin natif.

---

### Adaptateur
**Ce que c'est** : de courtes sequences d'ADN synthetiques que l'on colle aux
deux extremites de chaque fragment avant le sequencage.

**Pourquoi** : les adaptateurs permettent au sequenceur de "reconnaitre" les
fragments et de les fixer au bon endroit dans la machine. Ils servent aussi
de points d'ancrage pour les amorces.

```
Fragment original :   [ATCGATCG...]

Apres ajout d'adaptateurs :
[ADAPTATEUR_A][ATCGATCG...][ADAPTATEUR_B]
```

**Banque (library)**
= l'ensemble de tous les fragments d'un echantillon, auxquels on a ajoute
les adaptateurs. La banque est ce qu'on charge dans le sequenceur.

```
Echantillon de depart
        |
        | fragmentation
        v
Millions de fragments
        |
        | ajout d'adaptateurs
        v
Banque prete pour le sequencage
```

---

## 3. Vocabulaire de sequencage

### Read (lecture)
**Ce que c'est** : la sequence brute produite par le sequenceur pour un fragment.
Un read = la lecture d'un seul fragment.

**C'est CE que tu manipules dans ton prototype.**

```
Fragment reel dans l'echantillon :
5' - ATCGATCGATCGATCG - 3'

Read produit par le sequenceur :
ATCGATCGATCGATCG
(avec possiblement des erreurs selon la technologie)
```

**Short reads vs Long reads** :

| Technologie | Longueur typique | Taux d'erreur | Erreurs types |
|-------------|-----------------|---------------|---------------|
| Illumina    | 150-300 bases   | < 0.1%        | Substitutions |
| Nanopore    | 1 000 - 1 Mb    | 1-5%          | Insertions/deletions |
| PacBio      | 10 000 - 100 000| 0.1-1%        | Insertions/deletions |

---

### Qualite (Quality Score / Phred Score)
**Ce que c'est** : pour chaque base appelee dans un read, le sequenceur
attribue un score de confiance.

**Formule** : Q = -10 * log10(probabilite d'erreur)

```
Q10  -> 1 erreur sur 10      (10% d'erreur)
Q20  -> 1 erreur sur 100     (1% d'erreur)
Q30  -> 1 erreur sur 1000    (0.1% d'erreur)  <- standard Illumina
Q40  -> 1 erreur sur 10 000  (0.01% d'erreur)
```

---

### Basecalling
**Ce que c'est** : la conversion du signal brut du sequenceur en lettres A, C, G, T.

**Chaque technologie a son propre signal brut** :
- Illumina   -> signal fluorescent (couleur de lumiere)
- Nanopore   -> signal electrique (variation de courant ionique)

Le basecalling transforme ce signal physique en sequence nucleotidique.
C'est une etape algorithmique, souvent basee sur des modeles de deep learning
pour Nanopore (outil : Guppy, Dorado).

```
Signal Nanopore (courant en picoamperes) :
[120, 118, 95, 96, 140, 141, 80, 82, ...]

Apres basecalling :
ATCGATCG...
```

---

### Format FASTQ
**Ce que c'est** : le format de fichier standard pour stocker les reads
et leurs scores de qualite.

**Structure d'un read en FASTQ** (4 lignes par read) :

```
@identifiant_du_read [description optionnelle libre]
ATCGATCGATCGATCGATCG
+
IIIIIIIIHHHHGGGGFFFF
```

Ligne 1 : @ + identifiant unique du read + optionnellement une description
           apres le premier espace (texte libre, ignore par la plupart des outils)
Ligne 2 : la sequence nucleotidique (le read lui-meme)
Ligne 3 : + (separateur, parfois repete l'identifiant)
Ligne 4 : les scores de qualite encodes en ASCII, un caractere par base

**Decodage qualite ASCII** :
Chaque caractere correspond a un score Phred.
Le caractere 'I' = score 40, 'H' = 39, 'F' = 37, etc.
(valeur ASCII du caractere - 33 = score Phred)

**La description apres l'identifiant** :

Tout ce qui suit le premier espace sur la ligne 1 est du texte libre.
Les aligneurs (BWA, Minimap2) l'ignorent completement — ils ne lisent
que l'identifiant. Cela permet aux outils du pipeline de faire voyager
des metadonnees entre etapes sans casser la compatibilite.

```
Exemple Illumina (convention standardisee) :
@A00123:42:HXXXXXX:1:1101:3456:7890 1:N:0:ATCGAATT
 \___ identifiant ___/               \___ description ___/
                                     (run info, barcode...)

Exemple Kraken2 (classificateur) :
@read_00042|kraken:taxid|9606
(l'identifiant taxonomique encode directement)

Exemple possible pour T2 :
@read_00042 family=Lassavirus prob=0.87,Arenavirus prob=0.13
(les probabilites voyagent jusqu'a l'aligneur)
```

---

## 4. Vocabulaire d'analyse

### Couverture / Profondeur (Coverage / Depth)
**Ce que c'est** : le nombre moyen de reads qui couvrent chaque position
du genome de reference.

```
Position 1000 du genome :
Read 1 :   ---[ATCG]---
Read 2 :  --[ATCGATCG]-
Read 3 :    --[CGATCG]--
Read 4 :   ---[ATCGATC]-

Couverture en position 1000 : 4x
```

**Valeurs typiques** :
- 10x  : couverture minimale pour analyse
- 30x  : standard pour genome humain
- 100x : pour detection de variants rares

**Attention : "10x minimum" = une moyenne, pas un minimum par position**

La couverture est une valeur moyenne sur l'ensemble du genome.
Une couverture moyenne de 10x signifie que certaines positions ont 0x,
d'autres 20x, et que la moyenne est 10x.

```
Couverture moyenne 10x sur un genome de 5 positions :

Position 1 :  |||||||||||||||   15x
Position 2 :  ||||||||||        10x
Position 3 :  |||               3x
Position 4 :  |||||||||||||     13x
Position 5 :  |||||||           7x
                                -----
              Moyenne           9.6x ≈ 10x

La position 3 a une couverture faible mais la moyenne reste acceptable.
```

**Quand est-ce que la couverture est calculee dans le pipeline ?**

La couverture ne peut pas etre calculee par le classificateur.
Elle necessite deux etapes prealables :

```
1. Classification  : "ce read appartient a la famille X"
        |
        v
2. Binning FASTQ   : les reads de la famille X sont regroupes
                     dans un fichier FASTQ dedie
        |
        v
3. Alignement      : BWA ou Minimap2 colle chaque read sur le
                     genome de reference de la famille X
        |
        v
4. Couverture      : on peut maintenant compter combien de reads
                     couvrent chaque position -> 10x, 30x, etc.
```

Connaitre la famille d'un read (classification) ne suffit pas.
Il faut aussi savoir a quelle position exacte du genome il correspond
(alignement) pour calculer la couverture.

**En metagenomique** :

La couverture est calculee separement pour chaque famille identifiee.
Un echantillon avec 10 familles genere 10 calculs de couverture distincts.

```
Echantillon :
  -> LASV             : 4.26% des reads -> couverture X sur genome LASV
  -> bacterie humaine : 60%   des reads -> couverture Y sur genome bacterie
  -> ADN hote         : 35%   des reads -> couverture Z sur genome humain
```

Dans l'article LASV : "4.26% des reads en moyenne etaient du LASV".
= sur 1 million de reads, seulement 42 600 viennent du virus.
Le reste vient de l'hote humain et des bacteries.

**Ce que fait ton prototype (T2) dans ce pipeline** :

Ton classificateur repond a "a quelle famille ?" -> etape 1 et 2.
Il produit des fichiers FASTQ par famille (binning).
La couverture est calculee en aval, par un outil externe (BWA, Minimap2).

---

### Genome de reference
**Ce que c'est** : une sequence d'ADN de reference, connue et validee,
representant un organisme ou une espece.

**Alignement** : le processus de "coller" chaque read sur le genome
de reference a l'endroit dont il est le plus proche.

```
Genome de reference :
ATCGATCGATCGATCGATCGATCGATCG...

Reads alignes :
     ATCGATCG          <- read 1
          TCGATCGATCG  <- read 2
               ATCGATCG <- read 3
```

**Assemblage de novo** : quand on n'a PAS de genome de reference,
on reconstruit le genome uniquement a partir des reads, en cherchant
les chevauchements entre eux.

C'est plus difficile et plus couteux en ressources.
Dans l'article LASV, ils utilisent Canu pour l'assemblage de novo.

---

### HPC : Homopolymer Compression
**Ce que c'est** : une technique pour reduire les erreurs d'insertion/deletion
de Nanopore.

**Le probleme Nanopore** :
Le sequenceur Nanopore a du mal a compter les repetitions consecutives
de la meme base (homopolymeres).

```
Sequence reelle :    AAAA  (4 adenines)
Lu par Nanopore :    AAA   (3 adenines) ou AAAAA (5 adenines)
```

**La solution HPC** :
Compresser toutes les repetitions consecutives a 1.
```
Avant HPC :  AAATTTCCCGGG
Apres HPC :  ATCG
```

En travaillant sur la version compressee, les erreurs de comptage
disparaissent. C'est pour ca que le skip Boyer-Moore ne fonctionne pas
pour Nanopore : l'erreur n'est pas un "caractere exotique" mais
une repetition ou une suppression dans un contexte de bases valides.

---

## 5. Schema recapitulatif du pipeline complet

```
Echantillon (sang, eau, sol...)
        |
        | Extraction ADN/ARN
        v
ADN/ARN brut
        |
        | Fragmentation
        v
Fragments (tailles variables)
        |
        | Ajout d'adaptateurs -> banque (library)
        v
Banque prete
        |
        | Sequencage (Illumina / Nanopore / PacBio)
        v
Signal brut (fluorescence / courant electrique)
        |
        | Basecalling
        v
Fichiers FASTQ (reads + qualite)
        |
        | Controle qualite (filtrage des reads trop courts / mauvaise qualite)
        v
Reads filtres
        |
        | Classification (T2 / Kraken2 / ...)
        v
Reads classes par famille
        |
        | Binning : un FASTQ par famille identifiee
        v
FASTQ famille A   FASTQ famille B   FASTQ famille C ...
        |
        | Alignement (BWA / Minimap2) sur genome de reference de chaque famille
        v
Reads alignes
        |
        | Calcul de couverture
        v
Couverture X par famille
        |
        | Analyse (variants, resistances, phylogenie...)
        v
Resultats biologiques
```

---

## Points cles a retenir

1. **Fragment** = morceau d'ADN coupe depuis le genome
2. **Amorce** = brin synthetique court qui sert de point de depart a la copie
3. **Hybridation** = collage spontane de deux brins complementaires
4. **PCR** = amplification en chaine : 1 fragment -> des milliards de copies
5. **Adaptateur** = etiquette ajoutee aux extremites des fragments pour le sequenceur
6. **Banque** = l'ensemble des fragments prepares, prets a sequencer
7. **Read** = la sequence brute produite pour un fragment
8. **Basecalling** = conversion du signal physique en lettres ACGT
9. **FASTQ** = format fichier : sequence + score de qualite par base
10. **Couverture** = moyenne de reads couvrant chaque position du genome (calculee apres alignement)
11. **Binning** = regroupement des reads par famille dans des FASTQ dedies
12. **HPC** = compression des homopolymeres pour corriger les erreurs Nanopore

---

## Auto-evaluation

1. Quelle est la difference entre un fragment et un read ?
2. Pourquoi faut-il des amorces pour sequencer ?
3. Pourquoi Nanopore ne necessite pas d'amplification PCR ?
4. Qu'est-ce que le basecalling ?
5. Dans l'article LASV, 4.26% des reads sont du virus. Si tu as 1 million
   de reads en tout, combien viennent du LASV ?
6. Pourquoi le skip Boyer-Moore est inefficace pour les erreurs Nanopore ?
7. Une couverture moyenne de 10x garantit-elle que toutes les positions
   du genome sont couvertes a 10x ?
8. Cite les 4 etapes necessaires avant de pouvoir calculer la couverture
   en metagenomique.

---

## Mnemoniques

**Pipeline** : "Fragment Adapte Bien Sequence Correctement Analyse"
= Fragment -> Adaptateur -> Banque -> Sequencage -> Basecalling -> Classification -> Alignement

**Erreurs par technologie** :
- Illumina = Infimes substitutions
- Nanopore = Nombreuses insertions/deletions (homopolymeres)

**Q30** = "Qualite tres Bonne" : 1 erreur sur 1000

**Couverture** = metrique d'alignement, pas de classification

---

## Lien avec ton prototype

- Tes reads = fichiers FASTQ en entree de ton pipeline
- Tes k-mers = extraits depuis la ligne 2 de chaque read FASTQ
- Ta sortie = FASTQ bins par famille (+ probabilites dans l'en-tete)
- Tes "erreurs" (caracteres exotiques) != erreurs Nanopore reelles
- HPC = la vraie reponse au probleme que ton skip tentait de resoudre
- La couverture = calculee en aval par BWA/Minimap2, pas par ton outil

---

## Pour aller plus loin

### Lectures recommandees

**Livres** :
- "Biological Sequence Analysis" (Durbin et al.)
  - Chapitre 1 : introduction au sequencage
  
- "Bioinformatics Algorithms" (Compeau & Pevzner)
  - Chapitres sur l'assemblage et l'alignement
  - Version en ligne gratuite disponible

**Articles accessibles** :
- Shendure et al. (2017) "DNA sequencing at 40 : past, present and future"
  - Nature, 2017 - bilan complet des technologies
  
- Mardis (2008) "Next-generation DNA sequencing methods"
  - Annual Review of Genomics - introduction claire au NGS

### Ressources en ligne

**En francais** :
- Planet-Vie (ENS) : "La revolution de la genomique"
  - https://planet-vie.ens.fr/thematiques/manipulations-en-laboratoire/la-revolution-de-la-genomique-les-nouvelles-methodes-de
  
- INSERM medecine/sciences : "Sequencage de l'ADN par nanopores"
  - https://www.medecinesciences.org/en/articles/medsci/full_html/2018/02/medsci20183402p161/medsci20183402p161.html

**En anglais** :
- StatQuest : "Illumina sequencing" (YouTube)
- Oxford Nanopore : "How it works" (site officiel)
  - https://nanoporetech.com/how-it-works

**Outils pour pratiquer** :
- FastQC : outil de controle qualite de fichiers FASTQ
  - https://www.bioinformatics.babraham.ac.uk/projects/fastqc/
- Integrative Genomics Viewer (IGV)
  - Visualiser des reads alignes sur un genome de reference
  - https://igv.org/

### Exercices pratiques

**Niveau debutant** :

1. Telecharge un fichier FASTQ public sur NCBI SRA (Short Read Archive)
   et ouvre-le avec un editeur de texte. Compte les reads manuellement
   sur les 100 premieres lignes.

2. Calcule le score Phred a partir du code ASCII :
   - Caractere 'I' (ASCII 73) -> score = 73 - 33 = ?
   - Caractere '!' (ASCII 33) -> score = 33 - 33 = ?
   - Caractere '~' (ASCII 126) -> score = 126 - 33 = ?

3. Simule une amplification PCR sur papier :
   - Depart : 1 fragment double brin
   - Apres 3 cycles : combien de copies ?
   - Apres 10 cycles ?
   - Apres 30 cycles ?

**Niveau intermediaire** :

4. Ecris un parser FASTQ en Python qui lit un fichier FASTQ et retourne :
   - Le nombre de reads
   - La longueur moyenne des reads
   - Le score de qualite moyen

5. Implemente la compression HPC :
   - Input  : "AAATTTCCCGGG"
   - Output : "ATCG"
   Verifie avec : "AATCGGGATTT" -> ?

6. Calcule la couverture theorique :
   - Genome de 4 000 000 bases (E. coli)
   - 1 000 000 reads de 150 bases
   - Couverture moyenne = ?

**Niveau avance** :

7. Telecharge des donnees Nanopore publiques et applique HPC.
   Compare les k-mers avant et apres compression.

8. Utilise FastQC sur un fichier FASTQ reel.
   Identifie les regions de mauvaise qualite et explique pourquoi
   elles apparaissent souvent en debut ou fin de read.

---

**Prochaine fiche suggeree** : Fiche 09 - Replication de l'ADN
(pour comprendre comment la cellule duplique elle-meme son genome)

**Ou** : passer directement a la lecture de l'article Planet-Vie
avec ce vocabulaire acquis.
