# Plan d'accès interactif

## Objectif

Un plan facile à réutilliser pour valoriser les accès à un lieu ou à un événement.

## Structuration 

Une page html dans la racine du dossier. 
Un fichier géogrphique géojson. 

Certains types de tags sont interprétés dans le geojson : 
- Pour les lignes 
	- ref : nom court affiché sur la ligne.
	- stroke : couleur
	- dash : 'true' si il faut faire des pointillés
	- stroke-width : taille du trait à définir de 1 à 10 : tram = 6
	- opacity : peu défini
	- *marker-symbol* (non utilisé pour le moment mais pourrait complétér la ref)
	
Cette couche n'est pas cliquable hormis sur les affichages présentés dans ref. 

- Pour les symboles ou les textes
	- "marker-symbol": 'bus' ferry' 'bicycle'  'bicloo'  'car'  'rail-light'  'logo_event_small.png'  'logo_event'  'logo_large'  'logo_long'  'parking'  'walk' 
	- 
	- NON UTILISE 
		 - "marker-size": "medium",
		 - "marker-color": "#3dd6f5",
 
"amenity": "parking",
"name": "<strong>Zone de stationnement automobile toléré</strong>",
"marker-symbol": "car",
"zoom": "large", // non utilisé pour le moment
"fill": "BLUE",
"fill-opacity": 0.5
	

L'ordre d'affichage qu sein d'une couche est basé sur l'ordre du fichier géojson.

Contenu de popup : 
<br><a target=_blank href=\"https://destineo.fr/fr/horaires/TAN/Bus/ligne/30/direction/OUTWARD/88\">Horraires prochains passages</a>


## Mode développement 

### Lancement de chromium avec possibilité de CROS 

Pour pouvoir faire des tests de fonctionnalité il est nécessaire d'ouvrir la page web en utilisant les scripts mapbox sur les fichiers stocké en local. Par défaut cela n'est pas autorisé par le navigateur. 

1. Installer chromium.

2. Lancer chromimum avec la sécurité désactivée.
C:\Users\Utilisateur\AppData\Local\Chromium\Application\chrome.exe --disable-web-security --user-data-dir="2021 Lieux culturel"