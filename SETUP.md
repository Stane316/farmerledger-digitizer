# SETUP.md

> **Projet :** FarmerLedger Digitizer
>
> **Parcours :** Machine Learning Builder Track
>
> **Mission :** Projet 01 / 25
>
> **Version :** 1.0.0
>
> **Statut :** Guide officiel d'installation et de préparation de l'environnement

---

# Objectif

Ce document explique comment préparer entièrement l'environnement de développement du projet **FarmerLedger Digitizer**.

À la fin de ce guide, vous serez capable de :

- installer les prérequis ;
- créer l'environnement virtuel Python ;
- installer les dépendances ;
- télécharger le dataset officiel ;
- vérifier que tout fonctionne correctement ;
- lancer le premier test du projet.

Ce document est destiné aussi bien aux développeurs qu'aux étudiants découvrant le projet.

---

# Architecture concernée

Le guide suppose que le projet possède la structure suivante.

```text
FarmerLedgerDigitizer/

├── configs/
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
│
├── docs/
├── experiments/
├── models/
│   ├── checkpoints/
│   ├── trained/
│   └── exported/
│
├── notebooks/
├── outputs/
│   ├── figures/
│   ├── predictions/
│   ├── reports/
│   └── summary/
│
├── scripts/
├── src/
├── tests/
│
├── README.md
├── requirements.txt
└── SETUP.md
```

---

# 1. Prérequis

Avant toute installation, vérifier que les outils suivants sont disponibles.

| Logiciel | Version recommandée |
|----------|---------------------|
| Python | 3.12.x |
| Git | dernière version stable |
| VS Code (ou équivalent) | recommandé |
| pip | dernière version |
| Jupyter Notebook | installé via requirements.txt |

---

# 2. Vérifier l'installation de Python

Sous Windows :

```bash
python --version
```

ou

```bash
py --version
```

Résultat attendu :

```text
Python 3.12.x
```

---

Vérifier également pip.

```bash
pip --version
```

---

# 3. Cloner le dépôt

```bash
git clone <URL_DU_DEPOT>

cd FarmerLedgerDigitizer
```

---

# 4. Créer l'environnement virtuel

Depuis la racine du projet :

```bash
python -m venv .venv
```

Une fois créé :

```text
.venv/
```

doit apparaître dans le projet.

---

# 5. Activer l'environnement virtuel

## Windows PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

---

## Windows CMD

```cmd
.venv\Scripts\activate.bat
```

---

## Linux

```bash
source .venv/bin/activate
```

---

## macOS

```bash
source .venv/bin/activate
```

---

Une fois activé, le terminal doit afficher :

```text
(.venv)
```

au début de la ligne.

---

# 6. Mettre pip à jour

```bash
python -m pip install --upgrade pip
```

---

# 7. Installer les dépendances

Installer toutes les bibliothèques du projet.

```bash
pip install -r requirements.txt
```

Selon la connexion Internet, cette étape peut durer plusieurs minutes.

---

# 8. Vérifier les dépendances

Lister les bibliothèques installées.

```bash
pip list
```

Vérifier notamment la présence de :

- TensorFlow
- OpenCV
- NumPy
- pandas
- Matplotlib
- scikit-learn
- TensorFlow Datasets

---

# 9. Vérifier TensorFlow

Lancer Python.

```bash
python
```

Puis :

```python
import tensorflow as tf

print(tf.__version__)
```

Résultat attendu :

```text
2.x.x
```

Quitter Python :

```python
exit()
```

---

# 10. Vérifier OpenCV

```python
import cv2

print(cv2.__version__)
```

---

# 11. Vérifier NumPy

```python
import numpy as np

print(np.__version__)
```

---

# 12. Télécharger le dataset

Le projet utilise :

**EMNIST Balanced**

Le téléchargement est automatique grâce à TensorFlow Datasets.

Exemple :

```python
import tensorflow_datasets as tfds

dataset = tfds.load(
    "emnist/balanced",
    split="train",
    as_supervised=True
)
```

Le téléchargement peut prendre plusieurs minutes lors de la première exécution.

---

# 13. Emplacement du dataset

Le dataset téléchargé est généralement stocké dans le cache TensorFlow.

Pour une organisation conforme au projet, il pourra être copié dans :

```text
data/

└── raw/
```

Les données téléchargées ne doivent jamais être modifiées directement.

---

# 14. Vérifier le dataset

Lancer :

```python
import tensorflow_datasets as tfds

builder = tfds.builder("emnist/balanced")

print(builder.info)
```

Les informations du dataset doivent s'afficher sans erreur.

---

# 15. Vérifier la structure du projet

La structure minimale doit être :

```text
configs/

data/

docs/

experiments/

models/

notebooks/

outputs/

scripts/

src/

tests/
```

Si un dossier manque, le créer avant de commencer le développement.

---

# 16. Premier test

Créer un fichier temporaire.

```python
import tensorflow as tf
import numpy as np

print("TensorFlow :", tf.__version__)
print("NumPy :", np.__version__)

print("Installation réussie.")
```

Exécuter :

```bash
python test_installation.py
```

Résultat attendu :

```text
TensorFlow : ...

NumPy : ...

Installation réussie.
```

---

# 17. Vérifier Jupyter Notebook

Lancer :

```bash
jupyter notebook
```

ou

```bash
jupyter lab
```

Le navigateur doit s'ouvrir automatiquement.

---

# 18. Vérifier les tests

Lorsque le projet contiendra les premiers tests :

```bash
pytest
```

Tous les tests devront passer sans erreur.

---

# 19. Résolution des problèmes fréquents

## Python non reconnu

Vérifier :

```bash
python --version
```

ou

```bash
py --version
```

Réinstaller Python si nécessaire.

---

## pip introuvable

Mettre pip à jour :

```bash
python -m ensurepip --upgrade
```

---

## TensorFlow ne s'installe pas

Vérifier :

- la version de Python ;
- la version de pip ;
- la connexion Internet.

---

## L'environnement virtuel ne s'active pas

Sous PowerShell :

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Puis réactiver :

```powershell
.venv\Scripts\Activate.ps1
```

---

## Erreur de mémoire

Fermer les autres applications.

Réduire la taille du batch pendant l'entraînement.

---

# 20. Vérification finale

Avant de commencer le développement, vérifier les points suivants.

| Vérification | Statut |
|--------------|--------|
| Python installé | ☐ |
| Git installé | ☐ |
| Environnement virtuel créé | ☐ |
| Environnement activé | ☐ |
| Dépendances installées | ☐ |
| TensorFlow fonctionne | ☐ |
| OpenCV fonctionne | ☐ |
| NumPy fonctionne | ☐ |
| Dataset téléchargé | ☐ |
| Structure du projet conforme | ☐ |
| Premier test exécuté | ☐ |

Tous les éléments doivent être validés avant de poursuivre.

---

# 21. Premier lancement du projet

Une fois toutes les vérifications terminées, le projet est prêt à être développé.

Le prochain document de référence est :

```text
MASTER_DEVELOPMENT_PROMPT.md
```

Ce document guidera l'IA de développement pour implémenter le projet de manière progressive, en respectant l'ensemble de l'architecture, de la documentation et des conventions définies.

---

# Conclusion

À ce stade :

- l'environnement de développement est opérationnel ;
- les dépendances sont installées ;
- le dataset est accessible ;
- la structure du projet est conforme ;
- toutes les vérifications techniques ont été réalisées.

Le projet est désormais prêt à entrer dans sa phase de développement, avec une base solide, reproductible et professionnelle, conforme aux standards du **Machine Learning Builder Track**.