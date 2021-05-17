# Application 

## Description

Dans cet exercice, il faut modéliser avec un diagramme
de classe l'application suivante.

Il n'est pas nécessaire de compléter entièrement les informations pour modéliser les classes. 

### Mesures

L'application permet de faire des mesures.

- Une mesure contient
  - Un numéro en entier
  - Une valeur en double 
- Les mesures sont sauvées en format xml. Ce qui veut dire qu'il y aura une méthode qui permet de récupérer les paramètres
de la mesure en format `XML`

### Configuration
Il y a deux configurations pour cette application. Une qui
permet de sauver les paramètres pour l'application et une 
pour les informations du hardware.

Ces configurations pourront être sauvées en format `XML`.

- Configuration pour l'application
  - nom : `string`
  - id : `int`
  - theme : `int`
  - user_id : `int`

- Configuration pour le hardware
  - nom : `string`
  - id : `int`
  - type : `int`
  - adresse : `int`

### Sauvegarde
Pour sauvegarder les données, il est possible d'écrire soit
dans une carte `SD` soit dans une mémoire `USB`
