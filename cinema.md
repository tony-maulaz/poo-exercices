# Cinéma

## But

Le but de cet exercice est de modéliser une situation réelle à l'aide d'un diagramme de cas d'utilisation `use case`.

Il est important de modéliser uniquement les parties importantes. Il se peut qu'il y ait des informations qui ne méritent pas d'apparaître sur le diagramme.

## Description

Vous êtes mandaté par une entreprise pour modéliser le fonctionnement d'une salle de cinéma. Il faut donc représenté de manière graphique les différentes actions à réaliser et qui peut les effectuer.

Tout les employés du cinéma peuvent contrôler les billets à l'entrée de la salle. Si le film a une limite d'age, l'employé chargé du contrôle va aussi s'assurer que le détenteur du billet a l'age adéquat pour visionner le film.

Un employé formé pourra démarrer la projection du film. Pour se faire il devra commencer par `initialiser` le projecteur. Pour projeter un film, l'employé va charger une bobine de film, contrôler le réglage du projecteur et démarrer la séance.

N'importe quel client peut acheter un billet. Il est possible d'acheter un billet par internet, ou alors en cash directement à la caisse du cinéma.

Si le film possède une limite d'age, le client devra en être informé lors de l'achat du billet.

Un technicien peut passer pour faire un service sur le projecteur. Lors du service il faudra `initialiser` le projecteur.

## Réalisation

Réaliser un diagramme de cas d'utilisation en utilisant le logiciel ou l'application 
- `draw.io`