# Projet de datavisualisation : Population couverte par une aide personnelle au logement en décembre par EPCI
![carte-de-france-des-departements-et-regions-800](https://user-images.githubusercontent.com/121296617/213013289-f8196b68-da5a-442f-b4a8-1fe01af00c12.jpg)


## Table des matires
### I. Origine du jeu de données, contrôle et amlioration de la qualité des données
### 1. Origine du jeu de données
### 2. Contrôle et amlioration de la qualité des données







#
 
## I. Origine des jeux de données, contrôle et amlioration de la qualité des données


### 1. Origine du jeu de données

    Notre jeu de données principal a pour titre "Population couverte par une aide personnelle au logement en décembre par EPCI". Couvrant la période de 2016 à 2020, il est fourni sous licence ouverte sur le site open data (CAFDATA) de la Caisse des Allocations Familiales (CAF). En effet, la CAF est un organisme de droit privé 1, 2 à compétence départementale 3 chargée de verser aux particuliers des prestations financières à caractère familial ou social (prestations légales), dans des conditions déterminées par la loi 4. 
    En vue de croiser ce jeu de données à un autre pour ressortir plus amples interprétations, nous avons choisi un jeu de données relatif aux taux de chômage localisés aux 3ᵉ trimestre (2016-2020) par départements, disponible sur le site de l'Institut National de la Statistique et des Etudes Economiques en abrégé INSEE.
    
### 2. Contrôle et amlioration de la qualité des données

    Le présent jeu de données est relativement complet. En effet, nous avons un fichier contenant 6286 lignes quasiment remplies. Cependant, le sprint qualité nous a permis de constater que dans certains départements quelques cellules sont incomplètes. Il s’agit principalement des EPCI des départements ayant les codes suivants : 971, 972, 973, 974, 976.
Ainsi, nous avons choisi de supprimer ces 23 Etablissements Publics de Coopration Intercommunale (EPCI) présents sur la capture d'écran ci-après :

![image](https://user-images.githubusercontent.com/121296617/212471136-f34dd37f-4d17-45a0-b012-2d02607d0925.png)

Nous avons également inséré dans notre jeu de données une colonne intitulée " LIBELLE_DEP " afin d'associer à chaque numéro de département, son nom.

## II. Visualisation des données

### 1. Première visualisation : Foyers bénéficiant des différents aides par département et par EPCI





### 2. Deuxième visualisation : Evolution des différentes aides octroyées


### 3. Troisième visualisation : Rapport entre les aides aux logement et le taux de chômage par département

Cette visualisation a pour but de vérifier s'il existe une relation entre le taux de chômage et le nombre d'aides allouées aux populations en fonction des départements. Pour cela, nous avons limiter notre étude à 2016 et 2020 qui réprésentent les dates extrêmes de notre période d'étude.

<iframe title="[ Taux de chômage par département, 2016 ]" aria-label="Map" id="datawrapper-chart-QxJRs" src="https://datawrapper.dwcdn.net/QxJRs/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="644" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
 Cette carte projette le taux de chômage dans les départements français en 2016. Nous pouvons constater un taux compris entre 9,2% et 10,9% (avec une tendance élevée au nord et au sud). Dans les départements situés à l'Est et à Ouest (avec une nimorité au Centre), la tendance est plutôt comprise entre 6% et 9,2%.
 
 <iframe title="[ Taux de chômage par département, 2020 ]" aria-label="Map" id="datawrapper-chart-QxJRs" src="https://datawrapper.dwcdn.net/QxJRs/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="655" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
En 2020, on note tout d'abord la baisse du taux de chômage. Ce dernier est compris entre 6,6% et 8,8%. Toutes les taux élévés restent visbiles dans les départements du Nord et du Sud. 
