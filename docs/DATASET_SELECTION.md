# Dataset Selection

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Version :** 1.0
>
> **Statut :** Validé

---

# 1. Objectif de ce document

Ce document décrit le processus ayant conduit au choix du dataset utilisé dans le projet **FarmerLedger Digitizer**.

Il présente :

- les besoins en données du projet ;
- les critères de sélection ;
- les datasets étudiés ;
- leur comparaison ;
- la justification du choix final.

L'objectif est de garantir un choix de dataset cohérent, reproductible et justifiable d'un point de vue technique comme pédagogique.

---

# 2. Contexte

Le cahier des charges décrit la numérisation d'un registre manuscrit utilisé par une coopérative de producteurs de café.

Cependant, aucun jeu de données n'est fourni.

Le projet nécessite donc la sélection d'un dataset public permettant de développer les compétences visées tout en respectant le niveau de difficulté annoncé.

---

# 3. Besoin en données

Le projet nécessite un dataset répondant aux caractéristiques suivantes.

## Nature des données

- Images
- Écriture manuscrite
- Caractères annotés

---

## Type de problème Machine Learning

Classification supervisée.

Entrée :

- image d'un caractère manuscrit.

Sortie :

- caractère correspondant.

---

## Caractéristiques attendues

Le dataset doit :

- contenir des caractères manuscrits ;
- être correctement annoté ;
- être suffisamment volumineux pour entraîner un CNN ;
- être librement accessible ;
- être compatible avec TensorFlow/Keras ;
- être facilement exploitable avec OpenCV.

---

# 4. Critères de sélection

Les datasets étudiés sont évalués selon les critères suivants.

| Critère | Importance |
|----------|-----------:|
| Correspondance avec le cahier des charges | ⭐⭐⭐⭐⭐ |
| Valeur pédagogique | ⭐⭐⭐⭐⭐ |
| Compatibilité avec un premier projet CNN | ⭐⭐⭐⭐⭐ |
| Qualité des annotations | ⭐⭐⭐⭐☆ |
| Documentation disponible | ⭐⭐⭐⭐☆ |
| Facilité d'utilisation | ⭐⭐⭐⭐☆ |
| Réutilisation dans les projets futurs | ⭐⭐⭐⭐⭐ |
| Licence ouverte | ⭐⭐⭐⭐⭐ |

---

# 5. Datasets étudiés

## 5.1 EMNIST

### Description

EMNIST (Extended Modified National Institute of Standards and Technology) est une extension du célèbre dataset MNIST.

Il contient des caractères manuscrits comprenant des chiffres ainsi que plusieurs jeux de lettres.

Plusieurs variantes sont disponibles :

- ByClass
- ByMerge
- Balanced
- Letters
- Digits
- MNIST

---

### Avantages

- référence mondiale pour la reconnaissance de caractères manuscrits ;
- parfaitement adapté aux CNN ;
- excellente documentation ;
- largement utilisé dans l'enseignement et la recherche ;
- directement exploitable avec TensorFlow.

### Inconvénients

- caractères isolés ;
- ne représente pas directement des pages complètes de registre.

---

## 5.2 IAM Handwriting Database

### Description

Base de données constituée de véritables textes manuscrits.

Elle est principalement utilisée pour les systèmes OCR avancés.

### Avantages

- très proche du problème réel ;
- lignes et mots manuscrits ;
- excellente qualité scientifique.

### Inconvénients

- beaucoup plus complexe ;
- nécessite des traitements supplémentaires (segmentation, extraction de lignes, etc.) ;
- peu adaptée à un premier projet.

---

## 5.3 MNIST

### Description

Dataset historique de reconnaissance de chiffres manuscrits.

### Avantages

- extrêmement simple ;
- très bien documenté ;
- idéal pour découvrir les CNN.

### Inconvénients

- uniquement des chiffres ;
- insuffisant pour représenter le contexte du projet.

---

## 5.4 CVL Handwriting Database

### Description

Dataset académique contenant des textes manuscrits réels.

### Avantages

- très réaliste ;
- adapté à l'OCR.

### Inconvénients

- plus complexe ;
- demande davantage de prétraitement.

---

# 6. Comparaison

| Critère | EMNIST | IAM | MNIST | CVL |
|----------|:------:|:---:|:------:|:---:|
| Proximité métier | ⭐⭐⭐⭐☆ | ⭐⭐⭐⭐⭐ | ⭐⭐☆☆☆ | ⭐⭐⭐⭐⭐ |
| Simplicité pédagogique | ⭐⭐⭐⭐⭐ | ⭐⭐☆☆☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐☆☆ |
| Compatible premier CNN | ⭐⭐⭐⭐⭐ | ⭐⭐⭐☆☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐☆☆ |
| Documentation | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐☆ |
| Réutilisation future | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐☆ | ⭐⭐⭐☆☆ | ⭐⭐⭐⭐☆ |

---

# 7. Dataset retenu

Le dataset retenu pour ce projet est :

# **EMNIST Balanced**

---

# 8. Justification du choix

EMNIST Balanced représente le meilleur compromis entre :

- simplicité ;
- qualité ;
- volume ;
- intérêt pédagogique ;
- proximité avec le cahier des charges.

Il permet d'apprendre les concepts fondamentaux de la reconnaissance de caractères manuscrits sans introduire prématurément la complexité d'un système OCR complet.

Ce choix respecte également le niveau de difficulté "Facile" annoncé pour cette première mission.

---

# 9. Pourquoi la variante "Balanced" ?

Parmi les différentes variantes d'EMNIST, **Balanced** a été retenue pour plusieurs raisons.

Elle offre :

- un équilibre entre les différentes classes ;
- la présence de chiffres et de lettres ;
- une taille adaptée à un premier projet ;
- une meilleure représentativité qu'un dataset limité uniquement aux chiffres.

Cette variante prépare également les projets futurs portant sur des documents plus complexes.

---

# 10. Limites du dataset retenu

Le dataset présente néanmoins plusieurs limites.

Il ne contient pas :

- de pages complètes ;
- de tableaux manuscrits ;
- de registres comptables ;
- de segmentation documentaire.

Le modèle développé dans ce projet ne constituera donc pas un OCR complet.

Il représentera uniquement le moteur de reconnaissance de caractères.

---

# 11. Perspectives

Les projets futurs pourront utiliser des datasets plus proches des situations réelles.

Par exemple :

- IAM Handwriting Database ;
- CVL Handwriting Database ;
- formulaires administratifs numérisés ;
- registres historiques ;
- documents OCR complexes.

Le modèle développé dans ce projet constituera une première brique réutilisable dans ces systèmes.

---

# 12. Décision finale

Après analyse des différentes alternatives, **EMNIST Balanced** est retenu comme dataset officiel du projet **FarmerLedger Digitizer**.

Ce choix garantit :

- une progression pédagogique cohérente ;
- une implémentation compatible avec TensorFlow/Keras ;
- une excellente documentation ;
- une forte réutilisabilité dans les projets suivants ;
- un équilibre optimal entre simplicité et réalisme.

---

# 13. Références

## Dataset officiel

- EMNIST (NIST Special Database 19)

## Documentation

- Documentation officielle EMNIST
- TensorFlow Datasets
- Hugging Face Datasets

---

# 14. Historique des décisions

| Version | Date | Auteur | Modification |
|----------|------|---------|--------------|
| 1.0 | Initialisation | Machine Learning Builder Track | Sélection du dataset EMNIST Balanced |