# CHANGELOG.md

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Version actuelle :** 1.0.0
>
> **Format :** Keep a Changelog
>
> **Versioning :** Semantic Versioning (SemVer)

---

# À propos de ce document

Ce document constitue l'historique officiel du projet.

Il permet de suivre l'ensemble des évolutions réalisées tout au long du cycle de vie du projet :

- nouvelles fonctionnalités ;
- corrections de bugs ;
- améliorations techniques ;
- changements d'architecture ;
- évolution de la documentation ;
- évolution du modèle de Machine Learning.

L'objectif est d'assurer une traçabilité complète des décisions et des modifications apportées au projet.

---

# Convention de versionnement

Le projet utilise le **Semantic Versioning (SemVer)**.

Format :

```text
MAJOR.MINOR.PATCH
```

Exemple :

```text
1.2.3
```

où :

- **MAJOR** : changement incompatible ou refonte importante.
- **MINOR** : ajout de fonctionnalités compatibles.
- **PATCH** : corrections de bugs ou petites améliorations.

---

# Types de changements

Les modifications seront classées dans les catégories suivantes.

## Added

Nouvelles fonctionnalités.

---

## Changed

Modifications importantes.

---

## Improved

Améliorations de performances ou de qualité.

---

## Fixed

Corrections de bugs.

---

## Removed

Éléments supprimés.

---

## Deprecated

Fonctionnalités devenant obsolètes.

---

## Security

Correctifs liés à la sécurité.

---

# Historique des versions

---

# [1.0.0] - Initialisation du projet

## Added

### Initialisation

- Création du dépôt Git.
- Mise en place de l'architecture standard du projet.
- Création de l'environnement Python.
- Définition de l'organisation des dossiers.
- Adoption du standard documentaire du Machine Learning Builder Track.

### Documentation

Création des documents de référence :

- README.md
- PROJECT_OVERVIEW.md
- DATASET_SELECTION.md
- DATASET.md
- ARCHITECTURE.md
- MODEL.md
- TRAINING.md
- EVALUATION.md
- RESULTS.md
- LESSONS_LEARNED.md
- CHANGELOG.md

### Dataset

- Analyse des besoins en données.
- Étude comparative de plusieurs datasets.
- Sélection du dataset **EMNIST Balanced**.
- Documentation complète du processus d'acquisition.

### Architecture

- Définition de l'architecture logicielle.
- Définition du pipeline Machine Learning.
- Définition de l'organisation des modules.
- Définition des flux de données.
- Définition des décisions d'architecture (ADR).

### Modèle

- Sélection d'un CNN comme architecture de référence.
- Définition des couches du réseau.
- Définition des hyperparamètres initiaux.
- Choix de l'optimiseur Adam.
- Choix de la fonction de perte Sparse Categorical Crossentropy.

### Entraînement

- Définition de la stratégie d'entraînement.
- Définition des callbacks.
- Définition de la sauvegarde des modèles.
- Définition de la gestion des expérimentations.

### Évaluation

- Définition des métriques.
- Définition des critères de validation.
- Définition des analyses qualitatives.
- Définition des protocoles d'évaluation.

### Résultats

- Définition du format de restitution.
- Définition des graphiques.
- Définition des tableaux de résultats.
- Définition des rapports générés.

### Capitalisation

- Mise en place du document LESSONS_LEARNED.
- Définition de la stratégie de capitalisation des connaissances.

---

## Changed

Aucun.

---

## Improved

Aucun.

---

## Fixed

Aucun.

---

## Removed

Aucun.

---

## Deprecated

Aucun.

---

## Security

Aucun.

---

# Versions futures

Les versions suivantes seront ajoutées au fur et à mesure de l'évolution du projet.

---

# [1.1.0] - Développement du pipeline de données

**Prévu**

## Added

- Chargement du dataset.
- Vérification automatique.
- Prétraitement.
- Normalisation.
- Pipeline TensorFlow.

---

# [1.2.0] - Première version du modèle CNN

**Prévu**

## Added

- Implémentation du modèle.
- Compilation.
- Sauvegarde.
- Chargement.

---

# [1.3.0] - Première phase d'entraînement

**Prévu**

## Added

- Entraînement complet.
- Checkpoints.
- Callbacks.
- Historique d'entraînement.

---

# [1.4.0] - Évaluation complète

**Prévu**

## Added

- Accuracy.
- Loss.
- Matrice de confusion.
- Rapport de classification.
- Visualisations.

---

# [1.5.0] - Première version stable

**Prévu**

## Added

- Documentation finale.
- Validation du projet.
- Publication GitHub.

---

# Journal des ADR

Les changements d'architecture devront toujours être synchronisés avec les documents ADR présents dans la documentation.

Chaque modification importante devra préciser :

- l'ADR concernée ;
- la justification ;
- les impacts ;
- la date de validation.

---

# Politique de mise à jour

Le fichier CHANGELOG.md doit être mis à jour :

- avant chaque nouvelle version ;
- après chaque fonctionnalité importante ;
- après chaque correction de bug significative ;
- après toute modification d'architecture ;
- après toute évolution du modèle ;
- après toute évolution de la documentation.

Les mises à jour doivent être réalisées dans l'ordre chronologique inverse (la version la plus récente en premier).

---

# Bonnes pratiques

Pour garantir la qualité du suivi du projet :

- chaque entrée doit être datée ;
- les descriptions doivent être courtes et précises ;
- les changements doivent être classés dans la bonne catégorie ;
- les numéros de version doivent respecter Semantic Versioning ;
- aucune modification importante ne doit être réalisée sans être documentée dans ce fichier.

---

# Conclusion

Le fichier **CHANGELOG.md** constitue la mémoire technique de l'évolution du projet.

Associé aux autres documents de la documentation standard, il garantit :

- une traçabilité complète des évolutions ;
- une meilleure collaboration ;
- une maintenance facilitée ;
- une compréhension rapide de l'historique du projet ;
- une gestion professionnelle des versions.

Il sera enrichi tout au long du développement de **FarmerLedger Digitizer** et servira de référence pour les futurs projets du **Machine Learning Builder Track**.