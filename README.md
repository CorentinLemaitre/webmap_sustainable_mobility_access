# Plan d'accès interactif

## Objectif

Un plan facile à réutiliser pour valoriser les accès à un lieu ou à un événement.

## Structuration 

Une page html dans la racine du dossier => `index.html` 

Un fichier géographique géojson => `map_data.geojson`

Les données stocké dans le géojson servent à la création de la carte stylisé.

L'ordre d'affichage qu sein d'une couche est basé sur l'ordre du fichier géojson.



## Règles de style 

Tags interprétés dans le geojson : 

### Les symboles

Ces règles s'appliquent également à tout ce qui est texte et symbole sur une ligne ou une surface. 

Cette couche est cliquable avec des popup actif de base.

- ``marker-symbol``  au choix parmi 'bus' 'ferry' 'bicycle'  'bicloo'  'car'  'rail-light'  'logo_event_small.png'  'logo_event'  'logo_large'  'logo_long'  'parking'  'walk' 
- ``name`` : contient le contenu présenté par le popup. Zone de stationnement automobile toléré</strong>",

### Les lignes 

Cette couche n'est pas cliquable hormis sur les affichages présentés dans ref. 

- ``ref`` : nom court affiché sur la ligne dans pointeur
- `stroke` : couleur en code HTML
- ``dash`` : 'true' si il faut faire des pointillés. Sinon non spécifié.
- ``stroke-width`` : taille du trait à définir de 1 à 10 : tram = 6
- ``opacity`` : peu défini

Tags non utilisés

- *``marker-symbol``* (non utilisé pour le moment mais pourrait compléter la ref)





 - `ref` 

Tags NON UTILISE 
- "marker-size": "medium",
 - "marker-color": "#3dd6f5",
 - "zoom": "large", // non utilisé pour le moment
 - "fill": "BLUE",
 - "fill-opacity": 0.5

Contenu de popup : 
<br><a target=_blank href=\"https://destineo.fr/fr/horaires/TAN/Bus/ligne/30/direction/OUTWARD/88\">Horraires prochains passages</a>


# Développement 

## Lancement de chromium avec possibilité de CROS 

Pour pouvoir faire des tests de fonctionnalité il est nécessaire d'ouvrir la page web en utilisant les scripts mapbox sur les fichiers stocké en local. Par défaut cela n'est pas autorisé par le navigateur. 

1. Installer chromium.

2. Ouvrer un exploreur de fichier dans votre dossier de travail ou est situé le html et les fichier sources.

3. Lancer une invite de commande (<kbd>Ctrl</kbd> + <kbd>L</kbd> puis  `cmd`  et <kbd>Entrée</kbd> ) 

4. Dans l'invite de commande lancer chromimum avec la sécurité désactivée.

  ```bash
  
  D:\Cloud\OneDrive\Bureau\chrome-win\chrome.exe --disable-web-security --user-data-dir=./
  ```

5. indiquer l'adresse dans le pc ou est situé la page web via un clic glissé.



## Task-list des améliorations

- Lorsque l'on clique sur la couche il y a 
- Lorsque l'on clique sur un bouton ca affiche les labels de la couche liée. 
- Séparer le token du code. 
- Lorsque l'on clique sur un élément "REF" il y a un highlight de la ligne concerné.
- Dans la couche géojson ajouter thème setup ou initial
- Avoir une seule couche javascript qui affiche à la fois le point et le ref de ligne pour simplifier popup etc.
- Séparer code javascript et page HTML 