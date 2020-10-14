# Objectif
Ce repository présente un exemple d'utilisation d'une carte géographique avec Tableau Desktop (Tableau Software).

Le cas d'usage est le suivant : localisation d'arbres fruitiers (pommmier, poirier, figuier, châtaignier) à cueillette automnale à Paris.

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

## Chargement des données dans Tableau Desktop
A l'ouverture de Tableau Desktop, ouvrir une Connexion par 'Dans un fichier >  Fichier texte'

![open_file](/screenshots/01_open_file.PNG)

et sélectionner le fichier  **les-arbres.csv**

## Création des données géographiques
Après avoir chargé les données, on va créer les coordonnées géographiques.

Faire un clic droit sur 'Geo Point 2D' puis 'Transformer > Scinder' pour récupérer la latitude et la longitude dans 2 champs distincts.

![conversion_lat_lon](/screenshots/screenshot_tableau_map%20(1).png)

Le résultat donne :
![conversion_scinder](/screenshots/screenshot_tableau_map%20(2).png)

Faire un clic droit sur 'Geo Point 2D - Scinder 1' puis 'Renommer' pour le renommer par 'latitude'.

Faire ensuite clic droit sur 'latitude' pour le convertir en latitude géographique pour Tableau par 'Rôle géographique' > 'Latitude'.

![conversion_lat](/screenshots/screenshot_tableau_map%20(3).png)

Renommer également le champ 'Geo Point 2D - Scinder 2' en 'longitude' et le convertir en longitude géographique par clic droit, 'Rôle géographique' > 'Longitude'.

## Mise en place des filtres
On va mettre en place 2 filtres : un sur les arbres voulus, un sur une hauteur minimale d'arbre pour une récolte, disons 2m.

Sélectionner le champ 'Libelle Francais' et glisser le dans 'Filtres'

![filtre_libelle](/screenshots/screenshot_tableau_map%20(4).png)

puis sélectionner les arbres suivants : 'Châtaignier', 'Figuier', 'Poirier à fruits', 'Pommier à fruits'

![filtre_libelle_detail](/screenshots/screenshot_tableau_map%20(5).png)

Sélectionner ensuite 'Hauteur(m)' et glisser le dans 'Filtres'

![filtre_hauteur](/screenshots/screenshot_tableau_map%20(6).png)

Sélectionner 'Attribut' 

![filtre_hauteur_att](/screenshots/screenshot_tableau_map%20(7).png)

puis sur l'écran suivant 'Minimum' et mettre 2 et OK

![filtre_hauteur_val](/screenshots/screenshot_tableau_map%20(8).png)

## Création de la map
On va créer la carte de représentation des données.

Sélectionner les champs 'latitude' et 'longitude'

![lat_lon](/screenshots/screenshot_tableau_map%20(9).png)

puis glisse les dans Lignes par exemple

![lat_lon_positionne](/screenshots/screenshot_tableau_map%20(11).png)

Cliquer ensuite sur 'Montre-moi' et sur la carte 

![lat_lon_map](/screenshots/screenshot_tableau_map%20(12).png)

Le résultat produit donne la carte ci-dessous :

![lat_lon_map_point](/screenshots/screenshot_tableau_map%20(13).png)

Pour naviguer sur la carte, cliquer sur la carte sur la flèche et sélectionner la fonction dite 'Panoramique' (double-flèche croisée)

![lat_lon_map_view](/screenshots/screenshot_tableau_map%20(14).png)

Cliquer ensuite sur 'Carte' > 'Cartes d'arrière-plan' > 'Rues' pour une meilleure vision des lieux sur la carte 

![lat_lon_map_rue](/screenshots/screenshot_tableau_map%20(15).png)

## Mise en forme minimale
On va améliorer la mise en forme de la carte.

Rajouter le nom de l'arbre sur les points de la carte en sélectionnant 'Libelle Francais' et en le glissant sur 'Etiquettes'.

![lat_lon_map_libelle](/screenshots/screenshot_tableau_map%20(16).png)

Le résultat est le suivant :

![lat_lon_map_libelle_view](/screenshots/screenshot_tableau_map%20(17).png)

Afin d'avoir des couleurs différentes par arbre, sélectionner 'Libelle Francais' et le glisser sur 'Couleur'.

![lat_lon_map_color](/screenshots/screenshot_tableau_map%20(18).png)

Le résultat est le suivant :

![lat_lon_map_color_view](/screenshots/screenshot_tableau_map%20(19).png)

On personalise les couleurs en cliqaunt sur 'Couleur' > 'Modifier les couleurs'

![lat_lon_map_color_modify_1](/screenshots/screenshot_tableau_map%20(20).png)

puis on sélectionner chaque libellé d'arbre et on clique sur la couleur voulue :

![lat_lon_map_color_modify_2](/screenshots/screenshot_tableau_map%20(21).png)

![lat_lon_map_color_modify_3](/screenshots/screenshot_tableau_map%20(22).png)

On change le libellé de 'Libelle Francais' en 'Fruit' pour le résultat suivant :

![board_title](/screenshots/screenshot_tableau_map%20(25).png)

On finalise en créant le tableau de bord :

![libelle_name](/screenshots/screenshot_tableau_map%20(23).png)

Sélectionner la feuille et la glisser dans l'espace central

![libelle_name_view](/screenshots/screenshot_tableau_map%20(24).png)

On propose de masquer le titre par un clic-droit sur la zone du titre puis 'Masquer le titre'

![board_new](/screenshots/screenshot_tableau_map%20(25).png)

Ce qui donne le résultat final :

![Rendu final](/screenshots/Tableau%20Desktop%20-%20map%20-%20cueillette%20automnale%20de%20fruits%20paris%20v2.PNG)

# Extrapolation
Pour étendre ce cas d'usage, une carte (Web) plus étendue sur la base de données publiques et contributives est disponible à cette adresse [http://fallingfruit.org/?c=forager%2Cfreegan&locale=fr](http://fallingfruit.org/?c=forager%2Cfreegan&locale=fr)

Bonne cueillette !
