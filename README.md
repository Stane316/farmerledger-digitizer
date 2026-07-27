# FarmerLedger Digitizer

> **Machine Learning Builder Track — Projet 01 / 25**
>
> Numérisation intelligente de registres manuscrits à l'aide d'un réseau de neurones convolutif (CNN).

---

## À propos du projet

**FarmerLedger Digitizer** est le premier projet du **Machine Learning Builder Track**, un parcours composé de **25 missions professionnelles indépendantes** destinées à construire une expertise complète en :

- Machine Learning
- Data Science
- Computer Vision
- Deep Learning
- AI Engineering
- MLOps
- Architecture IA

Chaque projet est inspiré d'un problème réel rencontré par une organisation africaine.

Cette première mission porte sur la **numérisation d'un registre manuscrit** appartenant à une coopérative agricole.

---

# Contexte

Une coopérative de producteurs de café située dans les hauts plateaux du Burundi conserve depuis plusieurs décennies un registre manuscrit contenant :

- les livraisons de café ;
- les paiements effectués ;
- les informations historiques des producteurs.

Ce registre constitue la mémoire comptable de la coopérative.

Cependant :

- aucune copie numérique n'existe ;
- certaines écritures ne sont comprises que par le trésorier actuel ;
- le registre risque d'être perdu ou détérioré.

L'objectif est de développer un système capable de reconnaître automatiquement les caractères manuscrits afin de préparer la numérisation complète de ces archives.

---

# Objectifs

Le projet vise à construire un pipeline complet de Machine Learning permettant de :

- charger un dataset de caractères manuscrits ;
- prétraiter les images ;
- entraîner un réseau de neurones convolutif (CNN) ;
- évaluer les performances du modèle ;
- produire un modèle réutilisable.

Ce projet constitue une introduction aux techniques de **Computer Vision** appliquées à la reconnaissance de caractères manuscrits.

---

# Objectifs pédagogiques

À l'issue de ce projet, les compétences suivantes auront été abordées :

## Machine Learning

- apprentissage supervisé ;
- classification multi-classes ;
- préparation des données ;
- évaluation de modèles.

## Deep Learning

- CNN ;
- convolutions ;
- pooling ;
- couches denses ;
- fonctions d'activation.

## Computer Vision

- images numériques ;
- prétraitement ;
- normalisation ;
- pipeline de vision.

## Ingénierie logicielle

- architecture modulaire ;
- documentation professionnelle ;
- reproductibilité ;
- gestion des expérimentations.

---

# Stack technique

| Domaine | Technologie |
|----------|-------------|
| Langage | Python |
| Framework Deep Learning | TensorFlow / Keras |
| Vision par ordinateur | OpenCV |
| Manipulation des données | pandas |
| Calcul scientifique | NumPy |
| Visualisation | Matplotlib |
| Évaluation | scikit-learn |
| Dataset | EMNIST Balanced |

---

# Structure du projet

```text
FarmerLedgerDigitizer/

├── configs/
├── data/
├── docs/
├── experiments/
├── models/
├── notebooks/
├── outputs/
├── scripts/
├── src/
├── tests/
├── README.md
└── requirements.txt
```

---

# Documentation

Toute la documentation du projet est disponible dans le dossier **docs/**.

| Document | Description |
|----------|-------------|
| PROJECT_OVERVIEW.md | Présentation générale du projet |
| DATASET_SELECTION.md | Analyse et justification du choix du dataset |
| DATASET.md | Guide d'acquisition et d'utilisation du dataset |
| ARCHITECTURE.md | Architecture technique complète |
| MODEL.md | Architecture du modèle CNN |
| TRAINING.md | Stratégie d'entraînement |
| EVALUATION.md | Méthodologie d'évaluation |
| RESULTS.md | Structure des résultats attendus |
| LESSONS_LEARNED.md | Retour d'expérience |
| CHANGELOG.md | Historique des évolutions |

---

# Pipeline Machine Learning

```text
Acquisition des données

        ↓

Prétraitement

        ↓

Construction du Dataset

        ↓

Création du CNN

        ↓

Entraînement

        ↓

Validation

        ↓

Évaluation

        ↓

Sauvegarde du modèle

        ↓

Prédiction
```

---

# Dataset

Le projet utilise le dataset :

**EMNIST Balanced**

Pourquoi ce choix ?

- largement reconnu dans la communauté scientifique ;
- adapté à l'apprentissage des CNN ;
- bonne diversité d'écritures manuscrites ;
- compatible avec les objectifs pédagogiques du projet.

Toutes les informations relatives au téléchargement et à la préparation du dataset sont disponibles dans :

```text
docs/DATASET.md
```

---

# Architecture du modèle

Le modèle est un **Convolutional Neural Network (CNN)** composé de :

- deux couches de convolution ;
- deux couches de MaxPooling ;
- une couche Flatten ;
- une couche Dense ;
- une couche Dropout ;
- une couche Softmax.

Les détails sont documentés dans :

```text
docs/MODEL.md
```

---

# Résultats attendus

À l'issue du projet, les livrables suivants seront disponibles :

- modèle entraîné ;
- courbes Accuracy et Loss ;
- matrice de confusion ;
- rapport de classification ;
- prédictions ;
- métriques ;
- documentation complète.

---

# Organisation des expérimentations

Chaque expérimentation est conservée dans :

```text
experiments/
```

Chaque expérience documente :

- les hyperparamètres ;
- les performances ;
- les observations ;
- les conclusions.

Cette approche garantit la reproductibilité des résultats.

---

# Feuille de route

## Phase 1

- [x] Analyse du projet
- [x] Choix du dataset
- [x] Documentation complète

## Phase 2

- [ ] Développement du pipeline de données

## Phase 3

- [ ] Implémentation du modèle CNN

## Phase 4

- [ ] Entraînement

## Phase 5

- [ ] Évaluation

## Phase 6

- [ ] Optimisation

## Phase 7

- [ ] Publication GitHub

---

# Progression dans le Machine Learning Builder Track

| Projet | Statut |
|---------|--------|
| Projet 01 — FarmerLedger Digitizer | 🚧 En développement |
| Projet 02 | ⏳ À venir |
| Projet 03 | ⏳ À venir |
| ... | ... |
| Projet 25 | ⏳ À venir |

---

# Licence

Ce projet est réalisé dans un objectif pédagogique dans le cadre du **Machine Learning Builder Track**.

Les licences des bibliothèques et du dataset utilisé doivent être respectées.

---

# Auteur

**Stane Aniambossou**

Étudiant en Génie Logiciel — AI Engineering • Machine Learning • Data Science • LLM Engineering • AI Agents

---

# Remerciements

Merci à la communauté open source ainsi qu'aux auteurs du dataset **EMNIST Balanced** pour la mise à disposition de ressources permettant l'apprentissage du Machine Learning.

---

# Conclusion

**FarmerLedger Digitizer** est bien plus qu'un premier exercice de Deep Learning.

Il constitue la première brique d'un parcours de 25 projets destiné à construire une expertise professionnelle en Machine Learning, AI Engineering et conception de produits d'intelligence artificielle.

Chaque projet du parcours réutilisera les fondations méthodologiques, architecturales et documentaires mises en place ici afin de construire progressivement un portfolio GitHub cohérent, professionnel et orienté vers la résolution de problèmes réels.