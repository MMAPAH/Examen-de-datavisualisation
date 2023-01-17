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
