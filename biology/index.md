# Index des fiches de revision - Biologie moleculaire

**Date de creation** : 14 novembre 2025  
**Derniere mise a jour** : 15 novembre 2025

---

## Vue d'ensemble

Ce dossier contient 6 fiches de revision thematiques couvrant les bases de la biologie moleculaire necessaires pour la bio-informatique. Les fiches sont organisees de maniere progressive et peuvent etre etudiees dans l'ordre.

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
- Probleme Rosalind : IPRB, LIA (voir Fiche 06 pour les maths)

---

### Fiche 06 : Probabilites en genetique
**Fichier** : `fiche_06_probabilites_genetiques.md`

**Contenu** :
- Probabilites de croisement (carre de Punnett revisite)
- Tirage sans remise dans une population
- Calcul de P(tirer un couple)
- Formules pour couples identiques vs differents
- Resolution complete de problemes type IPRB
- Pieges courants et verification
- Algorithme de resolution

**Concepts cles** :
- P(dominant) = Σ [P(tirer couple) × P(dominant|couple)]
- Meme genotype : (nb_G/N) × ((nb_G-1)/(N-1))
- Genotypes differents : 2 × (nb_G1×nb_G2) / (N×(N-1))
- Facteur ×2 pour l'ordre de tirage
- Verification : Σ P(tirage) = 1.0

**Pour qui** :
- Resoudre les problemes mathematiques de genetique
- Comprendre les probabilites avancees
- Modeliser les croisements
- Probleme Rosalind : IPRB, IEV, LIA

---

## Progression d'apprentissage recommandee

### Ordre logique
1. **Fiche 01** - Comprendre ou se trouve l'ADN dans la cellule
2. **Fiche 02** - Comprendre la structure de l'ADN
3. **Fiche 03** - Comprendre comment l'ADN change (mutations)
4. **Fiche 04** - Comprendre comment l'ADN est lu (transcription)
5. **Fiche 05** - Comprendre comment l'ADN se transmet (heredite)
6. **Fiche 06** - Calculer les probabilites de transmission

### Liens entre les fiches
```
Fiche 01 (Cellule) → ou se trouve l'ADN ?
         ↓
Fiche 02 (ADN) → quelle est sa structure ?
         ↓
Fiche 03 (Mutations) → comment change-t-il ?
         ↓
Fiche 04 (ARN) → comment est-il utilise ?
         ↓
Fiche 05 (Mendel) → comment se transmet-il ?
         ↓
Fiche 06 (Probas) → comment calculer les transmissions ?
```

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
- Introduction aux concepts (alleles, genotypes)
- Carre de Punnett de base

**Fiche 06 (Probabilites)** :
- IPRB : Mendel's First Law (probabilites genetiques)
- IEV : Calculating Expected Offspring
- LIA : Independent Alleles (2e loi de Mendel)

### Ordre suggere des problemes Rosalind
1. DNA - Compter les nucleotides
2. RNA - Transcription
3. REVC - Complement reverse
4. HAMM - Distance de Hamming
5. FIB - Fibonacci (deja fait)
6. GC - Contenu GC
7. **IPRB** - Loi de Mendel (avec Fiche 06 !)
8. PROT - Traduction (necessite fiche suivante sur code genetique)

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
- Section "Pour aller plus loin"

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

---

## Prochaines fiches a creer

### Priorite 1 (bases essentielles)
- **Fiche 07** : Code genetique et traduction
- **Fiche 08** : Replication de l'ADN
- **Fiche 09** : Structure des proteines

### Priorite 2 (algorithmique)
- **Fiche 10** : Alignement de sequences (Needleman-Wunsch)
- **Fiche 11** : Recherche de motifs
- **Fiche 12** : Assemblage de genomes (graphes de De Bruijn)

### Priorite 3 (specialisations)
- **Fiche 13** : Phylogenie moleculaire
- **Fiche 14** : Sequencage NGS
- **Fiche 15** : Transcriptomique (RNA-seq)
- **Fiche 16** : Genetique des populations (Hardy-Weinberg)

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

---

## Changelog

### 15 novembre 2025
- Ajout de la Fiche 06 : Probabilites en genetique
- Approfondissement mathematique pour IPRB
- Formules de tirage sans remise
- Algorithme de resolution complet
- Cas de tests et verification

### 14 novembre 2025
- Ajout de la Fiche 05 : Genetique mendelienne et heredite
- Mise a jour de la progression d'apprentissage
- Ajout de problemes Rosalind correspondants (IPRB, LIA)
- Mise a jour des prochaines fiches a creer
- Creation de 4 fiches thematiques initiales
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
- Noter changements dans changelog

---

## Themes couverts par les 6 fiches

### Biologie cellulaire et moleculaire
- ✓ Structure cellulaire (Fiche 01)
- ✓ Structure de l'ADN (Fiche 02)
- ✓ Structure de l'ARN (Fiche 04)

### Genetique et evolution
- ✓ Mutations (Fiche 03)
- ✓ Heredite mendelienne (Fiche 05)
- ✓ Probabilites genetiques (Fiche 06)

### Biologie moleculaire
- ✓ Transcription ADN → ARN (Fiche 04)

### Encore a couvrir
- ☐ Traduction ARN → Proteine (Fiche 07)
- ☐ Replication de l'ADN (Fiche 08)
- ☐ Structure des proteines (Fiche 09)

---

**Bon courage pour ta reconversion en bio-informatique !**

Tu as maintenant une base solide pour :
- Comprendre les problemes Rosalind
- Lire des papers scientifiques
- Apprehender les algorithmes de bio-informatique
- Contribuer a des projets open source
- Comprendre la genetique des populations
- Resoudre des problemes mathematiques de genetique

**Next steps** :
1. Reviser ces 6 fiches regulierement
2. Resoudre les problemes Rosalind correspondants
3. Implementer les algorithmes en Python
4. Contribuer a des projets comme rust-bio

**Rappel important** : Pas de pression, pas de deadline. C'est un marathon, pas un sprint. Prends le temps de bien comprendre chaque concept avant de passer au suivant.
