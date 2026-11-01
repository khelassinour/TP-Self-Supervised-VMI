# TP-Self-Supervised-VMI

**Auteur :** Nour El Imene KHELASSI  
**Formation :** Master 2 VMI — Université Paris Cité  

Ce dépôt contient le notebook du TP portant sur l'apprentissage de représentations visuelles sans supervision humaine à l'aide de tâches prétextes.

## Contenu du projet

* `selfsupervised_demos.ipynb` : Notebook complet exécuté sous Google Colab avec GPU T4, comprenant :
  1. L'étude et l'évaluation linéaire des approches prétextes existantes (**Context Encoder**, **Rotation Prediction**, **SimCLR**).
  2. L'évaluation comparative des représentations sur **CIFAR-10** et sur un second jeu de données (**Fashion-MNIST**).
  3. L'implémentation de la tâche prétexte de prédiction de position relative de patchs (*Doersch et al., 2015*), incluant :
     - La classe `RelativePatchDataset` pour l'extraction de patchs central et voisins (8 classes).
     - Le réseau siamois `RelativePositionNet` avec encodeur convolutionnel partagé.
  4. L'évaluation linéaire de l'encodeur de position relative sur les deux jeux de données et la génération des graphiques comparatifs.

## Résultats obtenus (Linear Probing — Test Accuracy)

| Méthode / Tâche Prétexte | CIFAR-10 Acc (%) | Fashion-MNIST Acc (%) |
| :--- | :---: | :---: |
| Context Encoder (Inpainting) | 45.77% | 85.52% |
| Rotation Prediction | 79.91% | 92.22% |
| SimCLR (Contrastive) | 92.84% | 84.90% |
| Relative Patch Position | 38.36% | 63.12% |

## Utilisation

Pour réexécuter le notebook :
1. Ouvrir le fichier `selfsupervised_demos.ipynb` dans Google Colab.
2. Activer un accélérateur matériel GPU (*Exécution > Modifier le type d'exécution > GPU T4*).
3. Exécuter les cellules de configuration au début du notebook pour cloner les dépendances et télécharger les checkpoints.
