# MODEL.md

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Version :** 1.0
>
> **Statut :** Architecture du modèle validée

---

# 1. Objectif du document

Ce document décrit l'architecture du modèle de Deep Learning utilisé dans le projet **FarmerLedger Digitizer**.

Il présente :

- les objectifs du modèle ;
- les choix d'architecture ;
- les couches du réseau ;
- les hyperparamètres retenus ;
- les fonctions d'activation ;
- la fonction de perte ;
- l'optimiseur ;
- les métriques d'évaluation ;
- les stratégies d'entraînement ;
- les limites de cette première architecture ;
- les pistes d'évolution.

Ce document constitue la référence technique pour l'implémentation du modèle.

---

# 2. Objectif du modèle

Le modèle a pour objectif de reconnaître automatiquement un caractère manuscrit à partir d'une image.

Entrée :

> Une image en niveaux de gris de **28 × 28 pixels**.

Sortie :

> La classe correspondant au caractère reconnu.

Le problème est donc un problème de **classification supervisée multi-classes**.

---

# 3. Pourquoi utiliser un CNN ?

Les images possèdent une structure spatiale.

Contrairement à un réseau de neurones entièrement connecté (MLP), un **Convolutional Neural Network (CNN)** est capable de :

- détecter des motifs locaux ;
- apprendre automatiquement les caractéristiques importantes ;
- être robuste aux petites variations d'écriture ;
- réduire le nombre de paramètres ;
- offrir de meilleures performances sur les données visuelles.

Pour un premier projet de Computer Vision, le CNN représente le meilleur compromis entre simplicité et efficacité.

---

# 4. Architecture retenue

Le modèle repose sur une architecture CNN relativement simple, adaptée à un premier projet.

```text
Entrée
(28 × 28 × 1)

↓

Convolution

↓

ReLU

↓

MaxPooling

↓

Convolution

↓

ReLU

↓

MaxPooling

↓

Flatten

↓

Dense

↓

Dropout

↓

Dense (Softmax)

↓

Prédiction
```

Cette architecture est volontairement légère afin de favoriser la compréhension plutôt que la complexité.

---

# 5. Description détaillée des couches

## Couche d'entrée

**Rôle**

Recevoir les images prétraitées.

**Dimensions**

```
28 × 28 × 1
```

---

## Première couche de convolution

Objectif :

extraire les premières caractéristiques.

Exemples :

- bords
- courbes
- traits
- orientations

Paramètres recommandés :

- 32 filtres
- noyau 3 × 3
- padding = same

---

## Fonction d'activation

La fonction **ReLU (Rectified Linear Unit)** est utilisée.

```
f(x) = max(0, x)
```

Pourquoi ?

- apprentissage plus rapide ;
- réduction du problème du gradient qui disparaît ;
- très utilisée en vision par ordinateur.

---

## Première couche de MaxPooling

Objectif :

réduire la dimension des cartes de caractéristiques.

Effets :

- diminution du coût de calcul ;
- meilleure généralisation ;
- réduction du risque de surapprentissage.

Taille recommandée :

```
2 × 2
```

---

## Deuxième couche de convolution

Cette couche apprend des caractéristiques plus complexes.

Par exemple :

- formes
- combinaisons de traits
- structures plus élaborées.

Paramètres recommandés :

- 64 filtres
- noyau 3 × 3

---

## Deuxième MaxPooling

Même objectif que précédemment :

réduction de la dimension.

---

## Flatten

Cette couche transforme les cartes de caractéristiques en un vecteur.

Elle permet la connexion avec les couches entièrement connectées.

---

## Couche Dense

Cette couche combine toutes les caractéristiques extraites.

Paramètres recommandés :

```
128 neurones
```

Activation :

ReLU

---

## Dropout

Le Dropout est ajouté afin de limiter le surapprentissage.

Valeur recommandée :

```
0.5
```

---

## Couche de sortie

Nombre de neurones :

```
47
```

(un neurone par classe EMNIST Balanced)

Fonction d'activation :

Softmax.

Le modèle produit une distribution de probabilités sur l'ensemble des classes.

---

# 6. Architecture complète

```text
Input
28 × 28 × 1

↓

Conv2D
32 filtres

↓

ReLU

↓

MaxPooling

↓

Conv2D
64 filtres

↓

ReLU

↓

MaxPooling

↓

Flatten

↓

Dense
128 neurones

↓

Dropout
0.5

↓

Dense
47 neurones

↓

Softmax
```

---

# 7. Hyperparamètres

Les valeurs suivantes constituent une base de départ.

| Paramètre | Valeur |
|-----------|--------|
| Batch Size | 32 |
| Epochs | 15 à 20 |
| Learning Rate | 0.001 |
| Optimiseur | Adam |
| Fonction de perte | Sparse Categorical Crossentropy |
| Métrique principale | Accuracy |

Ces valeurs pourront être ajustées lors des expérimentations.

---

# 8. Fonction de perte

Le projet utilise :

**Sparse Categorical Crossentropy**

Pourquoi ?

- adaptée aux problèmes de classification multi-classes ;
- compatible avec des labels entiers ;
- directement intégrée dans TensorFlow/Keras.

---

# 9. Optimiseur

Le projet utilise :

**Adam (Adaptive Moment Estimation)**.

Pourquoi ?

- convergence rapide ;
- peu de réglages nécessaires ;
- excellent choix pour un premier projet ;
- largement adopté dans les projets industriels.

---

# 10. Métriques d'évaluation

Les métriques principales seront :

## Accuracy

Mesure la proportion de prédictions correctes.

---

## Loss

Permet de suivre la progression de l'apprentissage.

---

## Matrice de confusion

Permet d'identifier les classes fréquemment confondues.

---

## Rapport de classification

Comprend notamment :

- précision ;
- rappel ;
- F1-score.

Ces métriques offriront une vision plus complète que la seule accuracy.

---

# 11. Stratégie d'entraînement

Le modèle sera entraîné selon les étapes suivantes :

1. Chargement du dataset.
2. Prétraitement.
3. Création des jeux d'entraînement, de validation et de test.
4. Construction du modèle.
5. Compilation.
6. Entraînement.
7. Validation.
8. Sauvegarde du meilleur modèle.
9. Évaluation finale.

---

# 12. Stratégies contre le surapprentissage

Le projet mettra en œuvre plusieurs techniques :

- Dropout ;
- séparation entraînement/validation ;
- suivi de la loss de validation ;
- sauvegarde du meilleur modèle.

Dans les projets futurs, d'autres techniques pourront être introduites :

- Early Stopping ;
- Data Augmentation ;
- Learning Rate Scheduler ;
- Batch Normalization.

---

# 13. Limites de cette architecture

Cette architecture est volontairement simple.

Elle ne permet pas :

- la reconnaissance de lignes de texte ;
- l'analyse de pages complètes ;
- l'OCR documentaire ;
- la lecture de tableaux manuscrits.

Ces fonctionnalités seront développées dans des projets plus avancés.

---

# 14. Perspectives d'évolution

Cette première architecture pourra évoluer progressivement vers des modèles plus performants.

Par exemple :

### Niveau 2

- CNN plus profonds ;
- Batch Normalization ;
- Data Augmentation.

### Niveau 3

- ResNet ;
- EfficientNet ;
- DenseNet.

### Niveau 4

- Vision Transformer (ViT) ;
- CRNN ;
- TrOCR ;
- modèles multimodaux.

L'objectif est de construire progressivement une expertise allant des CNN classiques jusqu'aux architectures modernes de vision par ordinateur.

---

# 15. Décisions d'architecture

## ADR-007

Architecture CNN simple.

**Justification**

Favoriser la compréhension des concepts fondamentaux.

---

## ADR-008

Deux blocs de convolution.

**Justification**

Suffisant pour un premier projet tout en offrant de bonnes performances sur EMNIST.

---

## ADR-009

Optimiseur Adam.

**Justification**

Excellent compromis entre simplicité et efficacité.

---

## ADR-010

Fonction de perte Sparse Categorical Crossentropy.

**Justification**

Compatible avec les labels du dataset.

---

## ADR-011

Utilisation de ReLU.

**Justification**

Standard moderne des réseaux convolutifs.

---

# 16. Résumé

Le modèle retenu constitue une excellente première architecture de Deep Learning.

Il permet :

- d'apprendre le fonctionnement des CNN ;
- de comprendre un pipeline complet de classification d'images ;
- de préparer les projets suivants du parcours.

Cette architecture servira de fondation pour des modèles plus avancés qui seront progressivement introduits tout au long du Machine Learning Builder Track.