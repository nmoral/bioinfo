# Index des fiches de revision - Biologie moleculaire

**Date de creation** : 14 novembre 2025  
**Version** : 1.3
**Derniere mise a jour** : 16 novembre 2025

---

## Vue d'ensemble

Ce dossier contient 8 fiches de revision thematiques couvrant les bases de la biologie moleculaire et des probabilites necessaires pour la bio-informatique. Les fiches sont organisees de maniere progressive et peuvent etre etudiees dans l'ordre.

---

## Liste des fiches

### Fiche 01 : Structure cellulaire et domaines du vivant
**Fichier** : `fiche_01_structure_cellulaire.md`

**Contenu** :
- Hierarchie d'organisation cellulaire
- Definitions : cellule, noyau, chromatine, chromosomes
- Les trois domaines du vivant : Eukaryota, Bacteria, Archaea
- Comparaison eucaryotes vs procaryotes
- Organisation du materiel genetique

**Concepts cles** :
- Cellule comme unite de base
- Noyau et organelles (eucaryotes)
- Absence de noyau (procaryotes)
- Differences fondamentales entre domaines

**Pour qui** :
- Debutants en biologie cellulaire
- Comprehension de l'organisation du vivant
- Base pour comprendre ou se trouve l'ADN

---

### Fiche 02 : Structure et composition de l'ADN
**Fichier** : `fiche_02_structure_adn.md`

**Contenu** :
- Structure d'un nucleotide (sucre, phosphate, base)
- Les 4 bases de l'ADN : A, C, G, T
- Structure primaire : ordre des bases
- Structure secondaire : double brin, appariement complementaire
- Structure tertiaire : double helice
- Complement reverse

**Concepts cles** :
- Nucleotide = unite de base
- Appariement A-T et C-G
- Double helice antiparallele
- Complementarite des brins
- Direction 5' → 3'

**Pour qui** :
- Comprehension de la molecule d'ADN
- Base pour sequencage et assemblage
- Essentiel pour algorithmes d'alignement

---

### Fiche 03 : Mutations et evolution
**Fichier** : `fiche_03_mutations_evolution.md`

**Contenu** :
- Definition d'une mutation
- Mutations ponctuelles (point mutations)
- Types : silencieuse, faux-sens, non-sens
- Brins homologues et ancetre commun
- Principe de parcimonie
- Distance de Hamming

**Concepts cles** :
- Mutation = erreur dans la copie
- Evolution = accumulation de mutations benefiques
- Distance genetique entre sequences
- Minimisation du nombre de mutations
- Phylogenie moleculaire

**Pour qui** :
- Comprendre variabilite genetique
- Base pour phylogenie
- Premier algorithme : distance de Hamming
- Probleme Rosalind : HAMM

---

### Fiche 04 : ARN et transcription
**Fichier** : `fiche_04_arn_transcription.md`

**Contenu** :
- Structure de l'ARN (ribose, uracile)
- Differences ADN vs ARN
- Types d'ARN : mRNA, tRNA, rRNA
- Processus de transcription
- Regles de correspondance (T→U)
- Epissage et epissage alternatif

**Concepts cles** :
- Uracile remplace thymine
- ARN simple brin
- Transcription : ADN → ARN
- mRNA sort du noyau
- Maturation chez eucaryotes

**Pour qui** :
- Comprendre expression genique
- Base pour transcriptomique (RNA-seq)
- Annotation de genomes
- Probleme Rosalind : RNA

---

### Fiche 05 : Genetique mendelienne et heredite
**Fichier** : `fiche_05_genetique_mendelienne.md`

**Contenu** :
- Histoire : blending inheritance vs Mendel
- Concepts : facteurs, alleles, dominant/recessif
- Homozygote vs heterozygote
- Genotype vs phenotype
- Loi de segregation (1ere loi de Mendel)
- Carre de Punnett et predictions
- Loi de l'assortiment independant (2e loi)
- Applications et exemples (yeux, groupes sanguins)

**Concepts cles** :
- Allele = version d'un gene
- Dominant s'exprime avec 1 copie, recessif avec 2
- Genotype = genes, Phenotype = apparence
- Carre de Punnett pour predictions
- Ratios 3:1 (monohybride), 9:3:3:1 (dihybride)

**Pour qui** :
- Comprendre l'heredite et la transmission des traits
- Base pour genetique des populations
- Essentiel pour GWAS et variant analysis
- Probleme Rosalind : IPRB, LIA

---

### Fiche 06 : Probabilites en genetique
**Fichier** : `fiche_06_probabilites_genetiques.md`

**Contenu** :
- Probabilites avancees et tirage sans remise
- Calculs de croisements genetiques
- Formules pour couples de meme genotype
- Formules pour couples de genotypes differents
- Resolution complete de problemes IPRB
- Verification et tests de coherence

**Concepts cles** :
- Tirage sans remise : (nb_G/N) × ((nb_G-1)/(N-1))
- Couples differents : facteur ×2
- Probabilite totale = somme des contributions
- Verification : somme des probabilites = 1.0

**Pour qui** :
- Applications mathematiques de la genetique mendelienne
- Resolution de problemes complexes de probabilites
- Comprendre IPRB et problemes similaires
- Base pour modelisation genetique

---

### Fiche 07 : Code genetique et traduction
**Fichier** : `fiche_07_code_genetique_traduction.md`

**Contenu** :
- Acides amines et proteines (20 acides amines standards)
- Structure primaire des proteines
- Code genetique : codons (3 bases → 1 acide amine)
- Redondance du code (64 codons, 20 AA)
- Codons speciaux : start (AUG), stop (UAA, UAG, UGA)
- Processus de traduction (ribosome, tRNA, mRNA)
- Structure et role du tRNA (anticodon + acide amine)
- Dogme central : ADN → ARN → Proteine
- Definition d'un gene
- Table du code genetique

**Concepts cles** :
- Proteines = polymeres d'acides amines
- Codon = triplet de bases ARN
- AUG = start (Met), UAA/UAG/UGA = stop
- tRNA : adaptateur entre codon et acide amine
- Ribosome : usine de traduction
- Code quasi-universel
- Polypeptide vs proteine

**Pour qui** :
- Comprendre expression genique complete (ADN → Proteine)
- Base pour annotation de genomes
- Essentiel pour proteomique
- Traduction in silico
- Probleme Rosalind : PROT, ORF, SPLC

---

### Fiche 08 : Theoreme de Bayes (NOUVELLE !)
**Fichier** : `fiche_08_theoreme_bayes.md`

**Contenu** :
- Probabilites conditionnelles P(A|B)
- Formulation du theoreme de Bayes
- Prior, vraisemblance, posterior, evidence
- Exemple detaille : test genetique
- Calculs pratiques et tableaux de contingence
- Applications en bio-informatique
- Reseaux bayesiens
- Statistiques bayesiennes vs frequentistes

**Concepts cles** :
- P(A|B) = P(B|A) × P(A) / P(B)
- Retourner les probabilites conditionnelles
- Importance de la prevalence (prior)
- Mise a jour de croyances avec nouvelles donnees
- MCMC pour inference complexe

**Pour qui** :
- Comprendre inference probabiliste
- Base pour phylogenie bayesienne (BEAST, MrBayes)
- Annotation de genomes et variant calling
- Tests diagnostiques et leur interpretation
- Machine learning bayesien
- Essentiel pour bio-informatique moderne

**Applications** :
- Inference phylogenetique (BEAST, MrBayes, PhyloBayes)
- Annotation de genes (GeneMark, Glimmer)
- Variant calling (GATK, FreeBayes)
- Classificateurs bayesiens naifs
- Reseaux bayesiens pour genetique
- Tests de paternite

---

## Progression d'apprentissage recommandee

### Ordre logique
1. **Fiche 01** - Comprendre ou se trouve l'ADN dans la cellule
2. **Fiche 02** - Comprendre la structure de l'ADN
3. **Fiche 03** - Comprendre comment l'ADN change (mutations)
4. **Fiche 04** - Comprendre comment l'ADN est lu (transcription)
5. **Fiche 05** - Comprendre comment l'ADN se transmet (heredite)
6. **Fiche 06** - Applications mathematiques de la genetique (probabilites)
7. **Fiche 07** - Comprendre comment l'information devient proteine (traduction)
8. **Fiche 08** - Inference probabiliste et applications (theoreme de Bayes)

### Liens entre les fiches
```
Fiche 01 (Cellule) → ou se trouve l'ADN ?
         ↓
Fiche 02 (ADN) → quelle est sa structure ?
         ↓
Fiche 03 (Mutations) → comment change-t-il ?
         ↓
Fiche 04 (ARN) → comment est-il copie en ARN ?
         ↓
Fiche 07 (Traduction) → comment l'ARN devient proteine ?
         ↓
Fiche 05 (Mendel) → comment tout cela se transmet ?
         ↓
Fiche 06 (Probabilites) → calculs mathematiques de transmission
         ↓
Fiche 08 (Bayes) → inference et mise a jour de connaissances
```

**Note** : La Fiche 05 (Mendel) peut etre etudiee a tout moment apres la Fiche 02, car elle est plus independante du flux central (ADN → ARN → Proteine). Les fiches 06 et 08 ajoutent les outils mathematiques pour la modelisation.

---

## Correspondance avec Rosalind.info

### Problemes directement lies

**Fiche 02 (ADN)** :
- DNA : Counting DNA Nucleotides
- REVC : Complementing a Strand of DNA

**Fiche 03 (Mutations)** :
- HAMM : Counting Point Mutations
- (Phylogenie plus tard)

**Fiche 04 (ARN)** :
- RNA : Transcribing DNA into RNA
- SPLC : RNA Splicing (plus avance)

**Fiche 05 (Mendel)** :
- IPRB : Mendel's First Law (probabilites genetiques)
- LIA : Independent Alleles (2e loi de Mendel)
- (Genetique des populations plus tard)

**Fiche 06 (Probabilites)** :
- IPRB : Mendel's First Law (resolution complete)
- IEV : Calculating Expected Offspring
- LIA : Independent Alleles

**Fiche 07 (Traduction)** :
- PROT : Translating RNA into Protein
- ORF : Open Reading Frames
- MPRT : Finding a Protein Motif
- MRNA : Inferring mRNA from Protein
- SPLC : RNA Splicing (combine avec Fiche 04)

**Fiche 08 (Bayes)** :
- PROB : Introduction to Random Strings
- Pas de probleme explicitement bayesien, mais utile pour :
  - Comprendre modeles probabilistes
  - Approche phylogenie bayesienne
  - Interpretation de scores de confiance

### Ordre suggere des problemes Rosalind
1. DNA - Compter les nucleotides
2. RNA - Transcription
3. REVC - Complement reverse
4. HAMM - Distance de Hamming
5. FIB - Fibonacci (deja fait)
6. GC - Contenu GC
7. PROT - Traduction ARN → Proteine
8. IPRB - Loi de Mendel (avec Fiche 06 pour calculs)
9. ORF - Cadres de lecture
10. SPLC - Epissage + Traduction
11. PROB - Probabilites de sequences

---

## Points communs entre toutes les fiches

### Structure de chaque fiche
- Definitions claires
- Exemples visuels
- Points cles a retenir
- Auto-evaluation avec reponses
- Mnemoniques
- Lien avec la bio-informatique
- Exercices pratiques
- **Section "Pour aller plus loin"** (lectures, ressources, exercices)

### Format unifie
- Pas de caracteres speciaux problematiques
- Encodage ASCII pur
- Tableaux pour comparaisons
- Exemples de code/sequences
- Progression logique

---

## Utilisation des fiches

### Pour l'apprentissage initial
1. Lire la fiche dans l'ordre
2. Faire les exercices mentalement
3. Verifier les reponses
4. Utiliser les mnemoniques
5. Passer a la fiche suivante

### Pour la revision
1. Lire les "Points cles a retenir"
2. Faire l'auto-evaluation
3. Revenir aux sections problematiques
4. Refaire les exercices

### Pour la pratique
1. Aller directement aux exercices
2. Implementer les algorithmes
3. Resoudre les problemes Rosalind
4. Revenir aux concepts si besoin

### Pour approfondir
1. Consulter "Pour aller plus loin"
2. Lire les ressources recommandees
3. Faire les exercices avances
4. Explorer les concepts connexes

---

## Prochaines fiches a creer

### Priorite 1 (bases essentielles)
- **Fiche 09** : Structure des proteines (secondaire, tertiaire, quaternaire)
- **Fiche 10** : Replication de l'ADN

### Priorite 2 (algorithmique)
- **Fiche 11** : Alignement de sequences (Needleman-Wunsch, Smith-Waterman)
- **Fiche 12** : Recherche de motifs
- **Fiche 13** : Assemblage de genomes (graphes de De Bruijn)

### Priorite 3 (methodes avancees)
- **Fiche 14** : Hidden Markov Models (HMM)
- **Fiche 15** : Phylogenie moleculaire
- **Fiche 16** : Sequencage NGS
- **Fiche 17** : Transcriptomique (RNA-seq)
- **Fiche 18** : Genetique des populations (Hardy-Weinberg)

---

## Ressources complementaires

### Pour approfondir la biologie
- Cours Rosalind.info (problemes avec contexte)
- Videos YouTube : MIT OpenCourseWare
- Livre : "Bioinformatics Algorithms" (Compeau & Pevzner)
- Khan Academy : Genetique et heredite

### Pour la pratique algorithmique
- Rosalind.info - Bioinformatics Stronghold
- LeetCode / HackerRank (pour algo general)
- Project Euler (pour maths)

### Pour la bio-informatique appliquee
- BioPython documentation
- Tutoriels NCBI
- Papers de reference (Nature, Bioinformatics)

### Pour les probabilites et statistiques
- "Think Stats" et "Think Bayes" (Allen Downey)
- Khan Academy : Probabilites
- Seeing Theory : visualisations interactives
- StatQuest (YouTube) : explications accessibles

---

## Changelog

### Version 1.3 (16 novembre 2025)
- Ajout de la Fiche 08 : Theoreme de Bayes
- Applications en inference phylogenetique bayesienne
- Reseaux bayesiens et modeles probabilistes
- Comparaison approches bayesienne vs frequentiste
- MCMC et methodes d'inference
- Tests diagnostiques et interpretation
- Mise a jour de la progression d'apprentissage
- Ajout de logiciels bayesiens (BEAST, MrBayes, Stan)

### Version 1.2 (15 novembre 2025)
- Ajout de la Fiche 07 : Code genetique et traduction
- Mise a jour de la progression d'apprentissage
- Ajout de problemes Rosalind correspondants (PROT, ORF, SPLC)
- Mise a jour de l'ordre suggere des problemes
- Ajout mention section "Pour aller plus loin" dans toutes les fiches
- Note : Fiche 06 existe deja dans le projet (probabilites genetiques)

### Version 1.1 (14 novembre 2025)
- Ajout de la Fiche 05 : Genetique mendelienne et heredite
- Ajout de la Fiche 06 : Probabilites en genetique (calculs avances)
- Mise a jour de la progression d'apprentissage
- Ajout de problemes Rosalind correspondants (IPRB, LIA, IEV)
- Mise a jour des prochaines fiches a creer

### Version 1.0 (14 novembre 2025)
- Creation de 4 fiches thematiques
- Separation des sujets pour clarte
- Correction problemes d'encodage
- Ajout d'exercices pratiques
- Liens avec Rosalind.info

---

## Notes d'utilisation

### Format des fichiers
- Markdown standard
- Pas de caracteres speciaux UTF-8 problematiques
- Compatible avec tous les editeurs
- Facile a convertir (PDF, HTML, etc.)

### Organisation
- Chaque fiche est independante
- Mais progression logique recommandee
- References croisees entre fiches
- Index pour navigation

### Mise a jour
- Ajouter nouvelles fiches au fur et a mesure
- Mettre a jour cet index
- Incrementer numero de version
- Noter changements dans changelog

---

## Themes couverts par les 8 fiches

### Biologie cellulaire et moleculaire
- ✓ Structure cellulaire (Fiche 01)
- ✓ Structure de l'ADN (Fiche 02)
- ✓ Structure de l'ARN (Fiche 04)
- ✓ Code genetique et traduction (Fiche 07)

### Genetique et evolution
- ✓ Mutations (Fiche 03)
- ✓ Heredite mendelienne (Fiche 05)

### Mathematiques et probabilites
- ✓ Probabilites genetiques (Fiche 06)
- ✓ Theoreme de Bayes et inference (Fiche 08)

### Dogme central
- ✓ ADN → ARN (Transcription, Fiche 04)
- ✓ ARN → Proteine (Traduction, Fiche 07)

### Encore a couvrir
- ☐ Structure des proteines (Fiche 09)
- ☐ Replication de l'ADN (Fiche 10)
- ☐ Alignement de sequences (Fiche 11)
- ☐ HMM et modeles probabilistes (Fiche 14)

---

## Vue d'ensemble du flux d'information

```
        ADN (Fiche 02)
         |
         | Replication (Fiche 10 - a venir)
         |
         v
        ADN
         |
         | Transcription (Fiche 04)
         |
         v
        ARN
         |
         | Traduction (Fiche 07)
         |
         v
      Proteine (Fiche 09 - a venir)
         |
         | Fonction cellulaire
         |
         v
    Phenotype (Fiche 05)
         |
         | Heredite
         |
         v
    Transmission (Fiche 05, 06)
         |
         | Inference
         |
         v
    Modelisation (Fiche 08)
```

---

## Parcours d'apprentissage par objectif

### Objectif : Resoudre problemes Rosalind basiques
**Fiches essentielles** : 1, 2, 3, 4, 7
**Temps estime** : 2-3 semaines
**Problemes cibles** : DNA, RNA, REVC, HAMM, GC, PROT

### Objectif : Comprendre genetique et heredite
**Fiches essentielles** : 1, 2, 5, 6
**Temps estime** : 2-3 semaines
**Problemes cibles** : IPRB, LIA, IEV

### Objectif : Bases pour phylogenie bayesienne
**Fiches essentielles** : 2, 3, 8
**Temps estime** : 3-4 semaines
**Logiciels cibles** : BEAST, MrBayes

### Objectif : Annotation de genomes
**Fiches essentielles** : 2, 4, 7, 8
**Temps estime** : 3-4 semaines
**Logiciels cibles** : GeneMark, Glimmer, Prodigal

### Objectif : Variant calling
**Fiches essentielles** : 2, 3, 8
**Temps estime** : 3-4 semaines
**Logiciels cibles** : GATK, FreeBayes

### Objectif : Base complete bio-informatique
**Toutes les fiches** : 1-8
**Temps estime** : 2-3 mois
**Resultat** : Solide comprehension des fondamentaux

---

**Bon courage pour ta reconversion en bio-informatique !**

Tu as maintenant une base solide pour :
- Comprendre le flux complet de l'information genetique
- Lire et comprendre des sequences biologiques
- Resoudre les problemes Rosalind de base
- Lire des papers scientifiques
- Apprehender les algorithmes de bio-informatique
- Contribuer a des projets open source
- Comprendre la genetique et l'heredite
- Maitriser les bases de l'inference probabiliste
- Utiliser des methodes bayesiennes modernes

**Next steps** :
1. Reviser ces 8 fiches regulierement
2. Resoudre les problemes Rosalind correspondants
3. Implementer les algorithmes en Python
4. Explorer les logiciels bayesiens (BEAST, MrBayes)
5. Contribuer a des projets comme rust-bio

**Rappel important** : Pas de pression, pas de deadline. C'est un marathon, pas un sprint. Prends le temps de bien comprendre chaque concept avant de passer au suivant. La Fiche 08 complete maintenant tes outils mathematiques pour aborder la bio-informatique moderne avec les methodes d'inference bayesienne !
