# RESULTS.md

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Version :** 1.0
>
> **Statut :** Structure des résultats validée

---

# 1. Objectif du document

Ce document définit le format officiel de présentation des résultats du projet **FarmerLedger Digitizer**.

Contrairement au document **EVALUATION.md**, qui décrit **la manière dont le modèle sera évalué**, ce document décrit **la manière dont les résultats seront organisés, présentés, interprétés et archivés**.

Il constitue un modèle de rapport qui sera complété automatiquement une fois les expérimentations terminées.

Son objectif est de garantir une restitution homogène des résultats sur l'ensemble des **25 projets** du Machine Learning Builder Track.

---

# 2. Résumé exécutif

Cette section présente une synthèse rapide des performances obtenues.

Elle doit permettre à un lecteur de comprendre l'état du projet en moins d'une minute.

## Informations générales

| Élément | Valeur |
|----------|---------|
| Projet | FarmerLedger Digitizer |
| Dataset | EMNIST Balanced |
| Modèle | CNN |
| Framework | TensorFlow / Keras |
| Date d'entraînement | À compléter |
| Version du modèle | À compléter |

---

## Résumé des performances

| Indicateur | Valeur |
|------------|---------|
| Accuracy | À compléter |
| Loss | À compléter |
| Precision | À compléter |
| Recall | À compléter |
| F1-Score | À compléter |

---

## Conclusion rapide

> À compléter après les expérimentations.

---

# 3. Résultats de l'entraînement

Cette section présente les résultats directement issus de l'entraînement.

## Configuration utilisée

| Paramètre | Valeur |
|-----------|---------|
| Batch Size | À compléter |
| Epochs | À compléter |
| Learning Rate | À compléter |
| Optimiseur | Adam |
| Fonction de perte | Sparse Categorical Crossentropy |

---

## Temps d'entraînement

| Élément | Valeur |
|----------|---------|
| Temps total | À compléter |
| Temps moyen par époque | À compléter |
| Plateforme utilisée | À compléter |

---

# 4. Performances finales

Les performances finales seront présentées dans un tableau standard.

| Métrique | Valeur |
|-----------|---------|
| Accuracy | À compléter |
| Validation Accuracy | À compléter |
| Test Accuracy | À compléter |
| Training Loss | À compléter |
| Validation Loss | À compléter |
| Test Loss | À compléter |

---

# 5. Courbes d'apprentissage

Les graphiques suivants devront être générés automatiquement.

## Accuracy

```text
outputs/figures/accuracy_curve.png
```

Description :

Évolution de l'Accuracy au fil des époques.

---

## Loss

```text
outputs/figures/loss_curve.png
```

Description :

Évolution de la Loss pendant l'entraînement.

---

# 6. Matrice de confusion

Une matrice de confusion devra être générée.

Emplacement recommandé :

```text
outputs/figures/confusion_matrix.png
```

Objectifs :

- identifier les classes les plus difficiles ;
- visualiser les erreurs ;
- détecter les confusions fréquentes.

---

# 7. Rapport de classification

Le rapport complet devra être exporté.

Exemple de structure :

| Classe | Precision | Recall | F1-Score |
|----------|-----------|--------|----------|
| A | À compléter | À compléter | À compléter |
| B | À compléter | À compléter | À compléter |
| ... | ... | ... | ... |

Ce rapport permettra une analyse détaillée des performances par classe.

---

# 8. Analyse qualitative des prédictions

Cette section présente plusieurs exemples représentatifs.

## Exemples de prédictions correctes

Pour chaque exemple :

- image originale ;
- label réel ;
- prédiction ;
- probabilité.

---

## Exemples d'erreurs

Pour chaque erreur :

- image originale ;
- classe réelle ;
- classe prédite ;
- score de confiance ;
- commentaire.

Cette analyse permettra de mieux comprendre les limites du modèle.

---

# 9. Analyse des erreurs

Les erreurs devront être regroupées selon plusieurs catégories.

## Confusions entre caractères similaires

Exemples :

- O ↔ 0
- I ↔ l
- S ↔ 5

---

## Images difficiles

- faible contraste ;
- bruit ;
- caractère mal centré ;
- écriture atypique.

---

## Limites du modèle

Les erreurs dues à :

- l'architecture ;
- le dataset ;
- les hyperparamètres.

Chaque catégorie devra être documentée.

---

# 10. Comparaison des expérimentations

Toutes les expérimentations devront être comparées.

| Expérience | Accuracy | Loss | Epochs | Observations |
|-------------|----------|------|---------|--------------|
| EXP-001 | À compléter | À compléter | À compléter | À compléter |
| EXP-002 | À compléter | À compléter | À compléter | À compléter |
| EXP-003 | À compléter | À compléter | À compléter | À compléter |

Cette comparaison permettra d'identifier la meilleure configuration.

---

# 11. Modèle retenu

Le meilleur modèle devra être clairement identifié.

Informations à renseigner :

| Élément | Valeur |
|----------|---------|
| Nom du modèle | À compléter |
| Version | À compléter |
| Accuracy | À compléter |
| Date | À compléter |
| Chemin de sauvegarde | models/trained/ |

---

# 12. Résultats exportés

Les principaux fichiers générés devront être archivés.

```text
outputs/

├── figures/
│   ├── accuracy_curve.png
│   ├── loss_curve.png
│   ├── confusion_matrix.png
│
├── reports/
│   ├── classification_report.csv
│   ├── metrics.json
│
├── predictions/
│   ├── predictions.csv
│
└── summary/
    └── experiment_summary.md
```

---

# 13. Interprétation des résultats

Les résultats devront être interprétés selon plusieurs axes.

## Qualité globale

Le modèle répond-il aux objectifs ?

---

## Généralisation

Le modèle conserve-t-il de bonnes performances sur le jeu de test ?

---

## Robustesse

Certaines classes posent-elles problème ?

---

## Limites

Quels sont les principaux points faibles ?

---

## Enseignements

Qu'avons-nous appris au cours de cette expérimentation ?

---

# 14. Recommandations

Cette section doit proposer des pistes d'amélioration.

Par exemple :

- augmenter le nombre d'époques ;
- tester davantage de filtres ;
- modifier le taux de Dropout ;
- introduire de la Data Augmentation ;
- tester Batch Normalization ;
- optimiser le Learning Rate.

Toutes les recommandations devront être justifiées.

---

# 15. Impact métier

Les résultats devront également être analysés sous un angle métier.

Questions à considérer :

- Le modèle est-il suffisamment fiable pour assister un opérateur humain ?
- Peut-il être intégré dans une chaîne de numérisation ?
- Quelles erreurs seraient les plus critiques pour une coopérative agricole ?
- Quelles vérifications humaines resteraient nécessaires ?

Cette analyse rappelle que le projet répond à un besoin concret et non uniquement académique.

---

# 16. Limites du projet

Les performances devront être interprétées en tenant compte des limites suivantes :

- utilisation d'un dataset académique ;
- absence de véritables registres comptables ;
- reconnaissance limitée aux caractères isolés ;
- absence de segmentation automatique ;
- absence de contexte textuel.

Ces limites sont assumées car elles correspondent au niveau pédagogique de cette première mission.

---

# 17. Validation finale

Le projet pourra être considéré comme terminé lorsque :

- toutes les métriques auront été calculées ;
- les graphiques auront été générés ;
- les résultats auront été archivés ;
- le meilleur modèle aura été identifié ;
- les analyses auront été rédigées ;
- les recommandations auront été documentées.

---

# 18. Conclusion

Les résultats constituent la preuve tangible du travail réalisé au cours du projet.

Au-delà des chiffres, ce document doit permettre de raconter l'histoire de l'expérimentation :

- ce qui a été tenté ;
- ce qui a fonctionné ;
- ce qui a échoué ;
- ce qui pourra être amélioré.

Cette approche transforme les résultats en véritable outil d'apprentissage et prépare les projets suivants du **Machine Learning Builder Track**.
