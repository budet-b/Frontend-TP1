# Frontend TP 1 - To do list advanced

Ce TP va vous faire réviser les bases déjà vu précédemment ainsi que des nouvelles notions.

Nous allons aborder dans ce TP:
- `useState`
- `useContext`
- `useReducer`
- `useRef`
- `useEffect`

Un ToDo est défini par 
```ts
export type ToDo = {
  description: string;
  id: string;
};
```

Antd est installé de base dans les packages, vous êtes libre de l'utiliser. Plus d'informations sur https://ant.design/components/overview/

## NewToDo
Dans `src/components/NewToDo/index.tsx` créer un input en utilisant `useState`. Créer un bouton qui nous servira d'ajout pour plus tard.

## ToDo Reducer
Dans `src/Reducer/ToDoReducer.ts` remplir le reducer avec les actions de type ADD, RESET, POP, DELETE.
L'action POP fera supprimer le dernier ToDo enregistré.
L'action DELETE devra supprimer le ToDo de l'index passé.

## ToDo item
Dans `src/components/ToDo/index.tsx` créer le composant qui prendra un ToDo en paramètre et qui affichera sa description.
Ajouter un bouton pour le supprimer au hover.

## Add ToDo
Dans `src/components/NewToDo/index.tsx` brancher le bouton pour ajouter un ToDo à notre Reducer.
Vous aurez besoin d'un UUID:

```
import { v4 as uuidv4 } from 'uuid';

{
  id: uuidv4() 
}
```

## Remove ToDo
Dans `src/components/ToDo/index.tsx` brancher le reducer et la suppression du ToDo selectionné.

## ToDo List
Dans `src/components/ToDoList/index.tsx` créer un composant qui récupère les ToDo de notre Reducer et affiche les ToDo items;

## Remove All Todo
Dans le fichier qui vous semble le plus cohérent, rajouter un bouton `Reset` qui va appeler notre Reducer et l'action `RESET`.

## ToDo to the top
Avec une Ref faire en sorte qu'à chaque nouveau ToDo ou suppression d'un ToDo un scrollTop soit effectué.

## ToDo Dark
En remplissant le context `src/contexts/ThemeContext.tsx` gérer un Dark Theme qui devra changer le background de votre site ainsi que les ToDo.

## ToDo confetti
En utilisant Lottie, afficher une animation (dans `src/assets/confetti.json`) lors de l'ajout d'un nouveau ToDo.
```ts
import Lottie from 'lottie-react';
```

## Bonus #1 Render les ToDo persistant
Comment faire en sorte que lors d'un refresh je garde mes ToDo ?

## Bonus #2 Implémenter une Recherche
Ajouter un Input qui nous permet de trier les ToDo avec ma recherche