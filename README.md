# Résolution du Problème du Sac à Dos (Knapsack Problem)

## Description du Projet
Ce projet porte sur la résolution et l'implémentation algorithmique du **Bounded Knapsack Problem** (Problème du sac à dos borné). L'objectif est de maximiser la valeur totale d'une sélection d'objets sans dépasser la capacité maximale de poids du sac, tout en respectant les limites de quantité pour chaque type d'objet.

**Membres du groupe :**
* **Magomed Tsitsiev** (33%)
* **Nouannapha Phichith** (33%)
* **Noé Arokeum** (33%)

## Algorithmes Implémentés
Le projet explore trois approches principales pour résoudre ce problème d'optimisation :

### 1. Sac à dos fractionnaire (Fractional Knapsack)
* **Approche :** Version où il est permis de diviser les objets. L'algorithme suit une stratégie gloutonne en triant les objets par ratio valeur/poids décroissant.
* **Complexité :** $O(n \log n)$.

### 2. Programmation Dynamique (Dynamic Programming)
* **Version Itérative :** Utilisation d'un tableau $(n+1) \times (W+1)$ pour stocker les résultats intermédiaires.
* **Version Mémoïsée (`knapdynMem`) :** Utilisation de la récursivité couplée à un dictionnaire de mémoïsation pour éviter les calculs redondants.
* **Complexité :** $O(n \times W \times B)$, où $W$ est la capacité et $B$ la borne de quantité maximale.

### 3. Branch and Bound (Séparation et Évaluation)
* **Principe :** Exploration d'un arbre de recherche décisionnel avec élagage (pruning) des branches non prometteuses.
* **Optimisation :** La borne supérieure (Upper Bound) est calculée à chaque nœud à l'aide de l'algorithme fractionnaire. Le tri des objets par ratio permet de trouver de bonnes solutions plus tôt et d'optimiser considérablement l'élagage.

## Analyse des Performances et Complexité
Des tests de performance comparatifs ont été réalisés avec le module `timeit` :
* **Algorithme le plus rapide :** `knapfrac` (glouton).
* **Stabilité :** La programmation dynamique avec mémoïsation (`knapdynMem`) s'avère plus stable et souvent plus rapide que la version itérative pure.
* **Efficacité :** Le Branch and Bound est performant grâce à un élagage efficace, bien que sa complexité théorique reste exponentielle dans le pire des cas.

## Utilisation
Le projet est implémenté sous forme de Jupyter Notebook (`knapsack_algorithms_comparison.ipynb`).

Pour exécuter le projet :
1. Installer Python et les bibliothèques standards nécessaires.
2. Lancer le notebook avec Jupyter (`jupyter notebook knapsack_algorithms_comparison.ipynb`).
3. Exécuter les cellules pour voir les différentes implémentations et les résultats des benchmarks comparatifs.
