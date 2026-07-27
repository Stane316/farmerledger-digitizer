# DATASET.md

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Dataset officiel :** EMNIST Balanced
>
> **Version :** 1.0
>
> **Statut :** Validé

---

# 1. Présentation

Ce document décrit le dataset officiel utilisé dans le projet **FarmerLedger Digitizer**.

Il constitue la référence technique concernant :

- le téléchargement du dataset ;
- son installation ;
- sa structure ;
- son organisation dans le projet ;
- son utilisation ;
- ses limites ;
- les prétraitements nécessaires avant l'entraînement.

L'objectif est de permettre à n'importe quel développeur de reproduire exactement l'environnement de données utilisé dans ce projet.

---

# 2. Présentation du dataset

Le projet utilise **EMNIST Balanced**, une variante du célèbre dataset **EMNIST (Extended Modified National Institute of Standards and Technology)**.

EMNIST est une extension du dataset MNIST développée afin d'étendre la reconnaissance manuscrite aux lettres et aux chiffres.

Contrairement au dataset MNIST, limité aux chiffres (0 à 9), EMNIST propose plusieurs variantes permettant de reconnaître des caractères alphabétiques et numériques.

Pour ce projet, la variante **Balanced** a été retenue.

---

# 3. Pourquoi ce dataset ?

Le choix d'EMNIST Balanced est motivé par plusieurs raisons.

- parfaitement adapté à un premier projet de Computer Vision ;
- largement utilisé dans l'enseignement et la recherche ;
- excellente qualité des annotations ;
- compatible avec TensorFlow/Keras ;
- compatible avec OpenCV ;
- suffisamment volumineux pour entraîner un CNN ;
- très bien documenté.

Même si le cas métier concerne un registre manuscrit complet, le projet se concentre volontairement sur la reconnaissance de caractères isolés afin de construire des bases solides avant d'aborder des systèmes OCR plus complexes.

---

# 4. Source officielle

Le dataset EMNIST est distribué par le **National Institute of Standards and Technology (NIST)**.

Il est également disponible sur plusieurs plateformes reconnues :

- TensorFlow Datasets
- Hugging Face Datasets
- Kaggle

Dans le cadre de ce projet, la priorité sera donnée à TensorFlow Datasets afin de simplifier l'installation et garantir la reproductibilité.

---

# 5. Licence

Le dataset EMNIST est destiné à un usage académique, pédagogique et de recherche.

Avant toute utilisation dans un contexte commercial, il est recommandé de consulter les conditions de licence de la source officielle utilisée.

---

# 6. Caractéristiques générales

| Caractéristique | Valeur |
|-----------------|--------|
| Type de données | Images |
| Domaine | Reconnaissance de caractères manuscrits |
| Format des images | Niveaux de gris |
| Taille des images | 28 × 28 pixels |
| Nombre de classes | 47 |
| Type d'apprentissage | Classification supervisée |

---

# 7. Structure des données

Chaque observation est composée de deux éléments.

## Entrée

Une image représentant un caractère manuscrit.

Exemple :

```text
Image (28 × 28 pixels)
```

## Sortie

Le label correspondant au caractère représenté.

Exemple :

```text
Classe : A

Classe : 7

Classe : g
```

---

# 8. Organisation dans le projet

Après téléchargement, le dataset devra être organisé selon l'architecture standard du projet.

```text
data/

├── raw/
│   └── emnist/
│
├── interim/
│
├── processed/
│
└── external/
```

### Description

**raw/**

Contient les données téléchargées sans modification.

---

**interim/**

Contient les données après les premiers traitements.

---

**processed/**

Contient les données prêtes pour l'entraînement.

---

**external/**

Contient d'éventuelles données complémentaires.

---

# 9. Méthodes de téléchargement

Plusieurs méthodes sont possibles.

---

## Méthode 1 — TensorFlow Datasets (Recommandée)

Cette méthode est la plus simple et la plus reproductible.

Installation :

```bash
pip install tensorflow tensorflow-datasets
```

Chargement :

```python
import tensorflow_datasets as tfds

dataset = tfds.load(
    "emnist/balanced",
    split="train",
    as_supervised=True
)
```

### Avantages

- téléchargement automatique ;
- version contrôlée ;
- parfaitement intégrée à TensorFlow ;
- aucune manipulation manuelle.

---

## Méthode 2 — Hugging Face Datasets

Installation :

```bash
pip install datasets
```

Chargement :

```python
from datasets import load_dataset

dataset = load_dataset("emnist", "balanced")
```

### Avantages

- intégration avec l'écosystème Hugging Face ;
- très pratique pour les expérimentations.

---

## Méthode 3 — Téléchargement manuel

Le dataset peut également être téléchargé manuellement depuis une source officielle ou un miroir reconnu.

Étapes recommandées :

1. Télécharger les fichiers.
2. Vérifier leur intégrité.
3. Les placer dans :

```text
data/raw/emnist/
```

4. Vérifier que tous les fichiers sont accessibles.

---

# 10. Vérification de l'installation

Après le téléchargement, plusieurs vérifications doivent être réalisées.

## Vérification du chargement

Le dataset doit pouvoir être chargé sans erreur.

---

## Vérification de la taille

Contrôler :

- nombre d'images ;
- nombre de labels ;
- nombre de classes.

---

## Vérification des dimensions

Toutes les images doivent avoir :

```
28 × 28
```

pixels.

---

## Vérification des labels

Chaque image doit posséder un label valide.

---

## Vérification visuelle

Afficher plusieurs images afin de confirmer que les caractères correspondent bien aux labels associés.

---

# 11. Prétraitements nécessaires

Avant l'entraînement, plusieurs opérations devront être réalisées.

## Normalisation

Les valeurs des pixels seront normalisées.

Objectif :

faciliter l'apprentissage du réseau.

---

## Conversion du type

Conversion éventuelle vers un format compatible avec TensorFlow.

---

## Mise en forme

Ajout de la dimension correspondant au canal de couleur.

Exemple :

```
28 × 28

↓

28 × 28 × 1
```

---

## Encodage des labels

Les labels seront convertis dans un format compatible avec la fonction de perte utilisée.

---

## Séparation des données

Création des jeux :

- entraînement ;
- validation ;
- test.

---

# 12. Utilisation dans le projet

Le dataset sera utilisé dans plusieurs étapes.

- exploration des données ;
- visualisation ;
- prétraitement ;
- entraînement du CNN ;
- validation ;
- évaluation ;
- génération des prédictions.

Il constitue la base de l'ensemble du pipeline Machine Learning.

---

# 13. Limites

Le dataset présente plusieurs limites.

Il ne contient pas :

- des registres manuscrits ;
- des tableaux ;
- plusieurs lignes de texte ;
- des colonnes ;
- des signatures ;
- des formulaires.

Il ne permet donc pas de construire directement un système OCR complet.

Cette limitation est volontaire afin de concentrer le projet sur l'apprentissage de la reconnaissance de caractères.

---

# 14. Perspectives d'évolution

Dans les projets suivants, des datasets plus réalistes pourront être utilisés.

Par exemple :

- IAM Handwriting Database ;
- CVL Handwriting Database ;
- formulaires administratifs ;
- registres historiques ;
- documents manuscrits complets.

Le modèle développé ici constituera une première brique réutilisable dans ces systèmes.

---

# 15. Bonnes pratiques

Les données téléchargées ne doivent jamais être modifiées directement.

Toutes les transformations devront être réalisées dans les dossiers :

```text
data/interim/
```

ou

```text
data/processed/
```

afin de conserver une copie intacte des données originales.

---

# 16. Résumé

Le dataset **EMNIST Balanced** constitue un excellent point de départ pour apprendre la reconnaissance de caractères manuscrits.

Il permet de :

- découvrir un pipeline Machine Learning complet ;
- apprendre les bases du Deep Learning appliqué à la vision ;
- développer un premier modèle CNN robuste ;
- préparer les projets plus avancés du parcours.

Ce dataset représente la première pierre d'un futur système complet de numérisation documentaire.

---

# 17. Références

## Dataset

- EMNIST (Extended Modified National Institute of Standards and Technology)

## Plateformes recommandées

- TensorFlow Datasets
- Hugging Face Datasets
- Kaggle

## Bibliothèques utilisées

- TensorFlow
- TensorFlow Datasets
- OpenCV
- NumPy
- pandas