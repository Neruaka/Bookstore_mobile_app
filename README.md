# BookStore

## Thème de l'application

Application de gestion de bibliothèque personnelle. On peut ajouter des livres, les mettre en favoris, les supprimer et rechercher dans notre collection.

## Présentation globale

BookStore c'est une app pour gérer sa collection de livres perso. L'idée c'est d'avoir un endroit où on peut voir tous nos livres, ajouter ceux qu'on a lu ou qu'on veut lire, et marquer nos préférés en favoris.

L'app a un thème sombre qui est plus agréable pour les yeux avec une barre de recherche pour retrouver rapidement un livre par son titre, son auteur ou son genre. On peut aussi filtrer pour voir uniquement nos favoris.

Quand on clique sur un livre on voit tous les détails : la couverture, l'auteur, l'année de sortie, le genre, la note et une description. Depuis cet écran on peut supprimer le livre ou le mettre en favori.

## Fonctionnalités implémentées

- Affichage de la liste des livres avec FlatList
- Recherche par titre, auteur ou genre
- Filtre pour afficher tous les livres ou seulement les favoris
- Ajout d'un nouveau livre via un formulaire
- Affichage des détails d'un livre
- Suppression d'un livre avec confirmation
- Système de favoris (ajouter/retirer)
- Persistance des données (livres et favoris sauvegardés sur le téléphone)
- Validation du formulaire avec messages d'erreur
- Écran de chargement pendant le chargement des données

## Choix techniques

**FlatList plutôt que .map()** : Utilisation de FlatList pour la liste des livres parce que c'est optimisé pour les longues listes. Contrairement à .map() qui rend tous les éléments d'un coup, FlatList rend seulement ce qui est visible à l'écran.

**Hook personnalisé useAsyncStorageState** : Pour pas répéter le code de AsyncStorage.getItem/setItem partout, j'ai créé un hook qui synchronise automatiquement un state avec le stockage local. Ca permet de sauvegarder les livres et les favoris facilement.

**Passage de fonctions via route.params** : Pour que l'écran de détail puisse supprimer un livre ou changer les favoris, je passe les fonctions en paramètres de navigation.

**StyleSheet pour les styles** : Tous les styles sont dans StyleSheet.create() en bas de chaque fichier. C'est plus propre que de mettre du style inline partout et c'est optimisé par React Native.

## Guide pour lancer le projet

### Prérequis

- Node.js
- npm
- Expo Go sur téléphone / Android Studio 

### Installation
```bash
# Cloner le projet puis aller dans le dossier
cd BookStore

# Installer les dépendances
npm install

# Lancer le projet
npx expo start
```

### Lancer sur téléphone

1. Lance `npx expo start` dans le terminal
2. Scanne le QR code avec l'app Expo Go (Android) ou l'appareil photo (iOS)
3. L'app se lance sur ton téléphone

Si ça marche pas (problème de réseau), essayer avec le tunnel :
```bash
npx expo start --tunnel
```
