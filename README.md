# Exemple de Map avec Tableau Desktop
Exemple d'utilisation de map avec Tableau Desktop (Tableau Software) : cueillette d'automne de fruits à Paris

# Objectif
Ce repository présente un exemple d'utilisation d'une carte dans Tableau Desktop.

Le cas d'usage est le suivant : localisation d'arbres fruitiers (pommmier, poirier, figuier, châtaignier) à cueillette automnale.

Les données utilisées sont accessibles en Open Data au lien qui suit : [open-data-paris-arbres](https://opendata.paris.fr/explore/dataset/les-arbres/export/?disjunctive.typeemplacement&disjunctive.arrondissement&disjunctive.libellefrancais&disjunctive.genre&disjunctive.espece&disjunctive.varieteoucultivar&disjunctive.stadedeveloppement&disjunctive.remarquable
).

# Résultat
Le tableau de bord donne le rendu suivant, extrait : ![Rendu final](/screenshots/Tableau%20Desktop%20-%20map%20-%20cueillette%20automnale%20de%20fruits%20paris%20v2.PNG)

Il est possible de filtrer par fruit en cliquant tout simplement sur le libellé du fruit en haut à droite, exemple :
![Rendu final filtre](/screenshots/Tableau%20Desktop%20-%20map%20-%20filtre%20pommier%20paris.PNG)

# Livrables 
 - les données, un fichier csv les-arbres.csv (~31Mo) compressé en zip dans le repo : **[les-arbres.zip](les-arbres.zip)**
 - le classeur Tableau Desktop : **[Tableau_map_cueillette_automnale_fruits_paris.twb](Tableau_map_cueillette_automnale_fruits_paris.twb)**
Le classeur a été construit avec Tableau Desktop version 2020.3 mais il est compatible avec d'anciennes versions.

Niveau : débutant

# Etapes détaillées de construction
Vous trouverez ci-dessous les étapes détaillées de construction du tableau de bord.

## Récupération des données
On récupère les données par ce lien [open-data-paris-arbres](https://opendata.paris.fr/explore/dataset/les-arbres/export/?disjunctive.typeemplacement&disjunctive.arrondissement&disjunctive.libellefrancais&disjunctive.genre&disjunctive.espece&disjunctive.varieteoucultivar&disjunctive.stadedeveloppement&disjunctive.remarquable).

Il est proposé de récupérer les données au format csv (~31Mo) :

![get_data](/screenshots/get_data.png)

## Chargement dans Tableau Desktop
A l'ouverture de Tableau Desktop, ouvrir une Connexion par 'Dans un fichier >  Fichier texte'

![open_file](/screenshots/01_open_file.PNG)

et sélectionner les-arbres.csv

## Création des données géographiques
![conversion_lat_lon](/screenshots/screenshot_tableau_map%20(1).png)
![conversion_scinder](/screenshots/screenshot_tableau_map%20(2).png)
![conversion_lat](/screenshots/screenshot_tableau_map%20(3).png)

## Mise en place des filtres
![filtre_libelle](/screenshots/screenshot_tableau_map%20(4).png)
![filtre_libelle_detail](/screenshots/screenshot_tableau_map%20(5).png)
![filtre_hauteur](/screenshots/screenshot_tableau_map%20(6).png)
![filtre_hauteur_att](/screenshots/screenshot_tableau_map%20(7).png)
![filtre_hauteur_val](/screenshots/screenshot_tableau_map%20(8).png)
## Création de la map
![lat_lon](/screenshots/screenshot_tableau_map%20(9).png)
![lat_lon_positionne](/screenshots/screenshot_tableau_map%20(11).png)
![lat_lon_map](/screenshots/screenshot_tableau_map%20(12).png)
![lat_lon_map_point](/screenshots/screenshot_tableau_map%20(13).png)
![lat_lon_map_view](/screenshots/screenshot_tableau_map%20(14).png)
![lat_lon_map_rue](/screenshots/screenshot_tableau_map%20(15).png)
## Mise en forme minimale
![lat_lon_map_libelle](/screenshots/screenshot_tableau_map%20(16).png)
![lat_lon_map_libelle_view](/screenshots/screenshot_tableau_map%20(17).png)
![lat_lon_map_color](/screenshots/screenshot_tableau_map%20(18).png)
![lat_lon_map_color_view](/screenshots/screenshot_tableau_map%20(19).png)
![lat_lon_map_color_modify_1](/screenshots/screenshot_tableau_map%20(20).png)
![lat_lon_map_color_modify_2](/screenshots/screenshot_tableau_map%20(21).png)
![lat_lon_map_color_modify_3](/screenshots/screenshot_tableau_map%20(22).png)
![libelle_name](/screenshots/screenshot_tableau_map%20(26).png)
![libelle_name_view](/screenshots/screenshot_tableau_map%20(27).png)
![board_new](/screenshots/screenshot_tableau_map%20(23).png)
![board_map](/screenshots/screenshot_tableau_map%20(24).png)
![board_title](/screenshots/screenshot_tableau_map%20(25).png)
# Extrapolation
Pour étendre ce cas d'usage, une carte (Web) plus étendue sur la base de données publiques et contributives est disponible à cette adresse [http://fallingfruit.org/?c=forager%2Cfreegan&locale=fr](http://fallingfruit.org/?c=forager%2Cfreegan&locale=fr)

Bonne cueillette !
