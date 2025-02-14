# Reseau-de-communication-IN403
Projet création d'un reseau de communication avec des noeuds dans le cadre de l'UE IN403 à l'UVSQ


# Compte-rendu du projet

## IN403 - Algorithmique de graphes

### Auteurs
Ce projet a été construit par César Charbey, Yohann Front-Reignier et Anissa Kourban.

### Description du projet
Le projet consiste à créer un réseau de communication avec différentes couches de niveaux (backbone, tier2, tier3), et permet à l'utilisateur d'interagir visuellement avec celui-ci.

Il utilise **Tkinter** pour l'interface graphique et des algorithmes classiques comme **l'algorithme de Dijkstra** pour calculer les chemins les plus courts. Les structures de données choisies permettent une représentation efficace du graphe et une interaction conviviale avec l'utilisateur.

### Structure du projet
Nous avons développé **deux classes principales** :
- **Réseau** : gère la structure du réseau et les calculs.
- **NetworkVisualizer** : gère l'affichage graphique avec Tkinter.

#### Classe Réseau
Dans cette classe, nous avons construit le réseau de communication en trois niveaux :
- **Tier 1 (Backbone)** : 10 nœuds interconnectés avec un débit élevé. Chaque lien a **75% de chances d'exister**, avec un poids compris entre **5 et 10**.
- **Tier 2** : 20 nœuds connectés à **au moins 1 ou 2 nœuds de Tier 1** et **2 ou 3 autres nœuds de Tier 2**. Poids des liens : **10 à 20**.
- **Tier 3** : 70 nœuds connectés à **au moins 2 nœuds de Tier 2**. Poids des liens : **20 à 50**.

Chaque nœud est stocké dans un **set** pour éviter les doublons, et les arêtes sont représentées dans un **dictionnaire** associant un nœud à un sous-dictionnaire contenant ses voisins et le poids des connexions.

Les méthodes principales de cette classe incluent :
- **Vérification de la connexité du graphe**.
- **Implémentation de l'algorithme de Dijkstra**.
- **Calcul de la table de routage à partir de Dijkstra**.

#### Classe NetworkVisualizer
L'interface graphique, conçue avec **Tkinter**, permet de :
- Visualiser les **100 nœuds et leurs connexions**.
- **Se déplacer, zoomer et recentrer** l'affichage.
- **Cliquer sur deux nœuds pour afficher le plus court chemin** et son poids total.
- **Choisir un nœud à l'aide d'un panel interactif**.

L'affichage suit une disposition en **spirale inspirée du nombre d'or**, afin de minimiser la superposition des arêtes.

---

### Installation et exécution
#### Prérequis
- Python 3.x
- Tkinter (inclus dans les distributions standard de Python)

#### Exécution
```bash
python main.py
```
