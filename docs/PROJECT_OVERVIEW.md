# Project Overview

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Difficulté :** Facile
>
> **Domaine :** Computer Vision • Machine Learning • OCR • Digitalisation documentaire
>
> **Statut :** Phase de conception

---

# 1. Présentation du projet

FarmerLedger Digitizer est une application de reconnaissance de caractères manuscrits (Handwritten Character Recognition - HCR) dont l'objectif est de participer à la numérisation des registres comptables d'une coopérative agricole.

Le projet s'inscrit dans une démarche de transformation numérique visant à préserver un patrimoine documentaire critique, réduire les risques liés à la perte d'informations et faciliter l'accès à l'historique des opérations de la coopérative.

Bien que le contexte soit celui d'une coopérative de producteurs de café au Burundi, les concepts développés sont applicables à de nombreux domaines nécessitant la numérisation de documents manuscrits.

---

# 2. Contexte métier

Depuis plusieurs années, une coopérative de producteurs de café conserve l'ensemble de ses livraisons et paiements dans un registre manuscrit unique.

Ce registre représente une source d'information essentielle :

- historique des livraisons ;
- historique des paiements ;
- suivi des producteurs ;
- mémoire financière de la coopérative.

Cependant, plusieurs risques existent :

- perte du registre ;
- détérioration physique ;
- difficulté de consultation ;
- dépendance au trésorier historique capable d'interpréter certaines écritures anciennes.

La coopérative souhaite donc amorcer une transition vers une gestion numérique de ses données.

---

# 3. Problématique

Comment convertir automatiquement des caractères manuscrits présents dans un registre papier en données numériques exploitables avec un niveau de précision suffisant pour faciliter la numérisation des archives de la coopérative ?

---

# 4. Objectifs du projet

Le projet poursuit plusieurs objectifs complémentaires.

## Objectif métier

Contribuer à la numérisation d'un registre manuscrit afin de sécuriser les informations historiques de la coopérative.

## Objectif technique

Développer un premier modèle de reconnaissance de caractères manuscrits basé sur un réseau de neurones convolutif (CNN).

## Objectif pédagogique

Comprendre l'ensemble d'un pipeline Machine Learning appliqué à un problème réel de Computer Vision.

---

# 5. Périmètre du projet

Le projet couvre :

- le chargement d'un dataset de caractères manuscrits ;
- le prétraitement des images ;
- la construction d'un modèle CNN ;
- l'entraînement du modèle ;
- l'évaluation des performances ;
- la génération de prédictions ;
- la structuration des résultats.

Le projet ne couvre pas :

- l'OCR complet d'une page ;
- la segmentation automatique des lignes ;
- la segmentation automatique des caractères ;
- le déploiement du modèle en production ;
- l'interface utilisateur.

Ces aspects seront abordés dans des projets plus avancés du parcours.

---

# 6. Cas d'utilisation

Le système devra être capable de :

- reconnaître un caractère manuscrit ;
- prédire sa classe ;
- restituer cette prédiction sous une forme exploitable ;
- servir de première brique d'un futur système complet de numérisation documentaire.

---

# 7. Compétences développées

## Machine Learning

- Construction d'un pipeline ML
- Entraînement supervisé
- Classification d'images
- Validation de modèle
- Évaluation des performances

## Computer Vision

- Lecture d'images
- Prétraitement
- Binarisation
- Normalisation
- Manipulation d'images

## Deep Learning

- Réseaux de neurones convolutifs (CNN)
- Convolutions
- Pooling
- Fonctions d'activation
- Softmax

## Data Engineering

- Organisation des données
- Prétraitement
- Structuration des sorties
- Export des résultats

## Software Engineering

- Architecture de projet
- Modularisation
- Configuration
- Documentation
- Tests

---

# 8. Technologies utilisées

| Domaine | Technologie |
|----------|-------------|
| Langage | Python |
| Deep Learning | TensorFlow / Keras |
| Vision | OpenCV |
| Manipulation des données | pandas |
| Calcul scientifique | NumPy |
| Visualisation | Matplotlib |
| Évaluation | scikit-learn |

---

# 9. Livrables attendus

À la fin du projet, le dépôt devra contenir :

- une architecture de projet professionnelle ;
- un pipeline complet d'entraînement ;
- un modèle CNN entraîné ;
- les métriques d'évaluation ;
- les scripts de prédiction ;
- la documentation standard du projet.

---

# 10. Critères de réussite

Le projet sera considéré comme réussi lorsque :

- le dataset sera correctement intégré ;
- le pipeline d'entraînement sera fonctionnel ;
- le modèle produira des prédictions cohérentes ;
- les performances seront correctement évaluées ;
- le code sera documenté ;
- la structure du dépôt respectera le standard défini pour le parcours.

---

# 11. Limites du projet

Ce projet constitue une première étape.

Il ne vise pas à résoudre le problème complet de la lecture automatique d'un registre manuscrit.

Il se concentre volontairement sur une tâche fondamentale :

> la reconnaissance de caractères manuscrits.

Cette approche permet de construire des bases solides avant d'aborder des systèmes OCR plus complexes.

---

# 12. Positionnement dans le parcours

FarmerLedger Digitizer constitue la première mission du Machine Learning Builder Track.

Il introduit les concepts fondamentaux qui seront réutilisés dans la majorité des projets suivants :

- pipeline Machine Learning ;
- traitement d'images ;
- apprentissage supervisé ;
- réseaux de neurones convolutifs ;
- évaluation de modèles.

Les compétences acquises serviront notamment de fondation pour les futurs projets portant sur :

- OCR avancé ;
- analyse documentaire ;
- Vision Transformers ;
- Intelligence Documentaire ;
- systèmes RAG multimodaux.

---

# 13. Vision long terme

Le projet est conçu comme la première brique d'un futur système complet de numérisation documentaire.

À terme, cette brique pourra être intégrée dans une architecture plus large comprenant :

- détection automatique des documents ;
- segmentation des lignes ;
- segmentation des caractères ;
- reconnaissance des champs ;
- validation humaine ;
- stockage structuré ;
- recherche documentaire intelligente.

---

# 14. Références

Cette documentation est complétée par :

- DATASET_SELECTION.md
- DATASET.md
- ARCHITECTURE.md
- MODEL.md
- TRAINING.md
- EVALUATION.md
- RESULTS.md
- LESSONS_LEARNED.md
- CHANGELOG.md
- CONTRIBUTING.md