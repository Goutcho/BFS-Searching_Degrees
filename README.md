# Projet "Degrees"

## Vue d'ensemble

Le projet Degrees explore les techniques d'intelligence artificielle dans l'analyse des réseaux sociaux, visant spécifiquement à trouver le degré de séparation entre deux individus dans un réseau de base de données de films. Il démontre l'utilisation d'un algorithme de recherche en largeur pour traverser et analyser les données du réseau.

## Structure

Le projet comprend deux composants principaux :

### util.py

#### Classe `Node`

Représente un nœud dans la structure de données avec des attributs :
- `state` : L'état ou la valeur du nœud.
- `parent` : Le nœud parent de ce nœud, utile pour retracer le chemin.
- `action` : L'action prise pour arriver à ce nœud depuis le parent.

#### Classe `StackFrontier`

Implémente une structure de données de pile (LIFO) pour gérer les nœuds, avec des méthodes :
- `add` : Ajoute un nouveau nœud à la frontière.
- `contains_state` : Vérifie si un état est dans la frontière pour éviter les révisites.
- `empty` : Vérifie si la frontière est vide, indiquant l'achèvement de la recherche.
- `remove` : Supprime et renvoie le dernier nœud ajouté.

#### Classe `QueueFrontier` (étend `StackFrontier`)

Implémente une file d'attente (FIFO) en modifiant la méthode `remove` pour renvoyer le premier nœud ajouté.

### degrees.py

Implémente la fonctionnalité principale avec :
- `load_data(directory)`: Charge les données des acteurs, films et rôles à partir de fichiers CSV.
- `main()`: Le point d'entrée. Charge les données, demande les noms et trouve le chemin le plus court avec `shortest_path`.
- `shortest_path(source_id, target_id)`: Utilise la recherche en largeur pour trouver le degré de séparation le plus court.
- `person_id_for_name(name)`: Renvoie l'ID pour un nom, en gérant les homonymes.
- `neighbors_for_person(person_id)`: Renvoie les paires (movie_id, person_id) pour les rôles partagés dans des films.

## Pour commencer

Pour exécuter le projet, assurez-vous que Python et les fichiers CSV nécessaires sont prêts. Exécutez :

```bash
python degrees.py

Entrez vos noms d'acteurs' tiré du CSV

Voyez !