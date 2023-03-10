## Population couverte par une aide personnelle au logement en décembre par EPCI
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0APREFIX%20bd%3A%20%3Chttp%3A%2F%2Fwww.bigdata.com%2Frdf%23%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0APREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0ASELECT%20DISTINCT%20%3Fr%C3%A9gionsLabel%20%3Fgeoloc%20%0AWHERE%20%7B%0A%0A%3Fr%C3%A9gions%20wdt%3AP31%20wd%3AQ36784.%20%0A%3Fr%C3%A9gions%20wdt%3AP625%20%3Fgeoloc%20.%0A%0A%0ASERVICE%20wikibase%3Alabel%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%7D%0A%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
#### Carte des différentes régions de France

## Table des matières
I. [Origine du jeu de données, contrôle et amélioration de la qualité des données](#Présentation)  
1. [Origine du jeu de données](#Origine-du-jeu-de-données) 
2. [Contrôle et amélioration de la qualité des données](#Contrôle-et-amlioration-de-la-qualité-des-données)

II. [Visualisation des données](#Visualisation-des-données) 
4. [Première visualisation : nombre de foyers couverts par une aide au logement par département](#Première-visualisation-:-nombre-de-foyers-couverts-par-une-aide-au-logement-par-département) 
5. [Deuxième visualisation : pourcentage d'allocataires de la branche famille par ordre croissant des régions](#Deuxième-visualisation-:-pourcentage-d'allocataires-de-la-branche-famille-par-ordre-croissant-des-régions) 
6. [Troisième visualisation : croisement des données](#Troisième visualisation-:-croisement-des-données) 
7. [Quatrième visualisation : rapport entre les aides aux logement et le taux de chômage par département](#Quatrième-visualisation-:-rapport-entre-les-aides-aux-logements-et-le-taux-de-chômage-par-département)

III. [Difficultés rencontrées](#Difficultés-rencontrées) 
9. [Les requêtes wikidata](#Les-requêtes-wikidata) 
10. [La visualisation des données](#La-visualisation-des-données) 

[Conclusion](#Conclusion) 


## I. Origine des jeux de données, contrôle et amélioration de la qualité des données <a id="Présentation"></a>

Pour mieux comprendre notre jeu de données, il est nécessaire de présenter ses origines ainsi que toutes les manipulations qui y ont été faites afin d'améliorer sa qualité. 

### 1. Origine du jeu de données <a id="Origine-du-jeu-de-données"></a>

Notre jeu de données principal a pour titre "Population couverte par une aide personnelle au logement en décembre par EPCI". Couvrant la période de 2016 à 2020, il est fourni sous licence ouverte sur le site open data (CAFDATA) de la Caisse des Allocations Familiales (CAF), téléchargeable [ici](http://data.caf.fr/dataset/population-couverte-par-une-aide-personnelle-au-logement-en-decembre-par-epci/resource/fecaa026-96ca-43a2-acd4-447d56abf2a6). En effet, la CAF est un organisme de droit privé 1, 2 à compétence départementale 3, chargée de verser aux particuliers des prestations financières à caractère familial ou social (prestations légales), dans des conditions déterminées par la loi 4. Elle a de ce fait une compétence territoriale et une mission de service public qui consiste à reverser des aides financières soit pour des raisons familiales, soit pour des raisons sociales.
En vue de croiser ce jeu de données pour ressortir plus amples interprétations, nous avons choisi trois (03) jeux de données à savoir :
* le taux de chômage localisé aux 3ᵉ trimestre (2016-2020) par départements, disponible sur le site de l'Institut National de la Statistique et des Etudes Economiques en abrégé INSEE, accessible [ici](https://www.insee.fr/fr/statistiques/2012804#tableau-TCRD_025_tab1_departements) ;
* l'estimation population par région, téléchargeable [ici](https://www.ined.fr/fr/tout-savoir-population/chiffres/france/structure-population/regions/) sur le site de l'Institut Nationel d'Etudes Démographique (INED) ;
* et le nombre de ménages par régions disponible sur le même site que le précédent.
    
### 2. Contrôle et amélioration de la qualité des données <a id="Contrôle-et-amlioration-de-la-qualité-des-données"></a>

Le jeu de données provenant de la CAF est relativement complet. En effet, nous avons un fichier contenant 6286 lignes quasiment remplies. Cependant, le sprint qualité via [la grille des 120 points](https://github.com/antoinecourtin/DEFI_2019/blob/master/sprint_qualite_grille.csv) ainsi que le sanity check avec le logiciel [Breve](http://hdlab.stanford.edu/breve/) nous ont permis de constater que dans certains départements quelques cellules sont incomplètes. Il s’agit principalement des  Etablissements Publics de Coopration Intercommunale (EPCI) des départements ayant les codes suivants : 971, 972, 973, 974, 976.  
Ainsi, nous avons choisi de supprimer ces 23 (EPCI) présents sur la capture d'écran ci-après :

![image](https://user-images.githubusercontent.com/121296617/212471136-f34dd37f-4d17-45a0-b012-2d02607d0925.png)

De plus, nous avons fait une formule afin de s'assurer que le total des foyers correspondait effectivement aux données indiquées. Ce qui fut le cas (d'où l'insertion de la colonne "Total_aides" dont les données sont similaires à la colonne "Total_allocataires_logement). Nous avons également inséré dans notre jeu de données une colonne intitulée " LIBELLE_DEP " afin d'associer à chaque numéro de département, son nom. Notre jeu de données se présente ainsi de la manière suivante :

<iframe title="Population couverte par une aide personnelle au logement en décembre (2016-2020)" aria-label="Table" id="datawrapper-chart-n1Azn" src="https://datawrapper.dwcdn.net/n1Azn/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="1273" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
## II. Visualisation des données <a id="Visualisation-des-données"></a>

### 1. Première visualisation : nombre de foyers couverts par une aide au logement par département <a id="Première-visualisation-:-Nombre-de-foyers-couverts-par-une-aide-au-logement-par-département"></a>

Aujourd’hui, plusieurs aident financières existent pour le logement. Entre l’Aide Personnalisée au logement (APL), l’Allocation au Logement à caractère Social (ALS) et l’Allocation au Logement à caractère Familial (ALF), la population est souvent dans le flou. En effet :
* l’APL est l’aide au logement la plus récente. Elle s’adresse aux personnes percevant des revenus modestes. Peuvent être éligibles aux APL : les personnes qui habitent dans un foyer d’hébergement conventionné, les locataires, colocataires et sous-locataires (s’ils sont déclarés) ;
* l'allocation de logement familiale (ALF) est une aide financière destinée à réduire le montant de votre loyer. Elle est versée en raison de votre situation familiale (vous touchez des prestations familiales, vous avez des personnes à charge...). Les conditions diffèrent selon que vous relevez du régime général de la caisse d'allocations familiales (Caf) ou du régime agricole de la mutualité sociale agricole (MSA) ;
* créée en 1971 dans l’objectif d’aider les personnes défavorisées, l’ALS est aujourd’hui une allocation versée à tout individu (situation personnelle, professionnelle et âge confondus) qui n’entrent pas dans les critères pour toucher les APL ou ALF. 

La branche famille quant-à elle gère deux minima sociaux et un complément de revenus :
* l’allocation aux adultes handicapés (Aah), versée aux personnes de plus de 20 ans dont le taux d’invalidité est au moins de 50% et qui ont de faibles ressources financières ;
* le revenu de solidarité active (Rsa) : il est accordé aux personnes sans ressources ou avec des ressources très faibles qui ont plus de 25 ans (ou moins de 25 ans si elles attendent un enfant ou ont au moins un enfant à charge) ;
* la Prime d’activité vient compléter les faibles revenus salariaux des personnes de plus de 18 ans, quelle que soit leur situation familiale. 
Notons que la notion d'allocataire est une notion de foyer (à rapprocher par exemple des ménages au sens Insee) et non d'individu. Ainsi, compter des allocataires signifie compter des foyers constitués de personnes seules ou de plusieurs personnes (familles).
 
<div class="flourish-embed flourish-hierarchy" data-src="visualisation/12715038"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
 
Cette visualisation a été faite avec Flourish. Elle représente les différnetes aides octroyées dans les différents départements. Les filtres permettent de choisir l'année et l'aide qu'on souhaite visualiser. On peut ainsi projeter chaque allocation de façon particulière à une date donnée. En parcourant les bulles, les données suivantes sont perçues : le numéro du département, le nom du département et le nombre d'allocataires. On constate ainsi que quelque soient la nature de l'aide et l'année visualisée, Paris regorge le nombre le plus élevé d'allocataires.
 
### 2. Deuxième visualisation : pourcentage d'allocataires de la branche famille par ordre croissant des régions <a id="Deuxième-visualisation-:-Pourcentage-d'allocataires-de-la-branche-famille-par-ordre-croissant-des-régions"></a>

Pour ressortir cette visualisation sous l'angle des régions, nous avons ajouté à nos données une nouvelle colonne dans laquelle nous avons mis pour chaque département, sa region de rattachement. L'outil utilisé ici est Datawrapper.
 
<iframe title="[ Pourcentage d'allocataires de la branche famille par ordre croissant des régions]" aria-label="Multiple Donuts" id="datawrapper-chart-aCbwt" src="https://datawrapper.dwcdn.net/aCbwt/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="686" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>

Nous avons mis en exergue les 5 régions bénéficiant du plus grand nombre d'aides de la branche famille de 2016 à 2020. On constate que chacune de ces régions à gardé son rang au fil des années. Aussi, la région Île-de-France reste en tête avec son pourcentage de 11% qui est le même. Les données sont quasiment les mêmes pour toutes les régions, la petite différence se perçoit au niveau du nombres total d'allocataires qui croit légèrement chaque année. 

### 3. Troisième visualisation : croisement des données <a id="Troisième visualisation-:-Croisement-des-données"></a>
 
Le but de cette visualisation est de ressortir, s'il y'en a, le rapport entre le nombre total d'allocataires de la branche famille sous l'angle des régions, le nombre de ménages et l'estimation de la population. Pour rappel, ces données complémentaires ont été prises sur le site de l'Institut National d'Etudes Démographiques (INED). La période considérée est de 2016 à 2020. Toutefois, en ce qui concerne le nombre de ménages, nous avons uniquement trouvé les données sur l'année 2018.

<div class="flourish-embed flourish-chart" data-src="visualisation/12677782"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
 
Ce graphique nous a permis de réaliser qu'il est difficile d'établir une corrélation entre l'estimation de la population et le nombre d'allocataires. On constate tout de même que le nombre de ménages dans une région est relativement égal à la moitié de la population.

### 4. Quatrième visualisation : rapport entre les aides aux logement et le taux de chômage par département <a id="Quatrième-visualisation-:-Rapport-entre-les-aides-aux-logements-et-le-taux-de-chômage-par-département"></a>

Cette visualisation a pour but de vérifier s'il existe une relation entre le taux de chômage et le nombre d'aides allouées aux populations en fonction des départements. Pour cela, nous avons limité notre étude à 2016 et 2020 qui réprésentent les dates extrêmes de notre période d'étude. Compte tenu de la faible évolution du nombre total d'aides, nous avons électionné uniquement ces deux années afin de ressortir une différence réelle dans les projections. L'outil utilisé est Datawrapper à travers le modèle carte choroplèthe des départements français. 
 
<iframe title="[ Taux de chômage, 2016]" aria-label="Map" id="datawrapper-chart-apMad" src="https://datawrapper.dwcdn.net/apMad/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="624" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
Cette carte choroplèthe projette le taux de chômage dans les départements français en 2016. Nous pouvons constater un taux compris entre 6,2% et 15,4% (avec une tendance élevée au nord et au sud). Dans les départements situés à l'Est et à Ouest (avec une nimorité au Centre), la tendance est plutôt comprise entre 6% et 9,2%.
 
<iframe title="[ Taux de chômage, 2020]" aria-label="Map" id="datawrapper-chart-wyOta" src="https://datawrapper.dwcdn.net/wyOta/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="663" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
En 2020, on note tout d'abord une baisse générale du taux de chômage. Ce dernier est compris entre 4,6% et 12,5%. Toutefois, les taux élévés restent visbiles dans les départements du Nord et du Sud. 
 
Nous avons choisi de visualiser afin de faire une comparaison, les données relatives au nombre total d'allocataires de la branche famille. Comme nous l'avons dit plus haut, la branche Famille gère deux minima sociaux et un complément de revenus. Ce qui permet d'enviager une corrélation avec le taux de chômage.
 
<iframe title="[ Total allocataires de la branche famille, 2016]" aria-label="Map" id="datawrapper-chart-QxJRs" src="https://datawrapper.dwcdn.net/QxJRs/6/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="651" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
On constate ici que le nombre de foyers bénéficiant d'une aide de la branche famille est élevé de façon particulière dans les départements de l'Ouest, ainsi que dans une partie des départements situés au Nord et au Sud. Il en est de même pour l'année 2020 telle que perçu sur la carte choroplèthe ci-après.
 
 
<iframe title="[ Total allocataires de la branche famille, 2020 ]" aria-label="Map" id="datawrapper-chart-PEtBw" src="https://datawrapper.dwcdn.net/PEtBw/3/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="687" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>

Conclusion partielle 
 
En 2020, le nombre d'allocatires à considérablement augmenté dans toutes les régions. L'on aurait logiquement pensé que plus le taux de chômage diminuait, plus le nombre de foyers bénéficiares d'aides de la branche famille diminuerait également. Ce qui n'est pourtant pas le cas. En effet, entre 2016 et 2020, le taux de chômage est passé de l'intervalle 6,2% - 15,4% à l'intervalle 4,6% - 12,5%, or le nombre d'allocataires est passé de l'intervalle 451 - 1,370,820 à l'intervalle 497 - 1,502,347. Il est important de noter qu'en 2020, en plus des régions partielles du Nord et du Sud ayant des taux élevés de chômage, tous les départements de l'Ouest perçoievnt une aide de la branche famille avec un nombre assez élevé. En tenant compte du fait que cette région avait un faible taux de chômage cette même année, nous pouvons dire qu'elle a, soit un nombre élévé d'adultes handicapés, soit un fort taux de personnes à faibles revenus d'activité. 
 
### III. Difficultés rencontrées <a id="Difficultés-rencontrées"></a>
  
#### 1. Les requêtes wikidata <a id="Les-requêtes-wikidata"></a>

Nous avons essayé d'afficher via une requête wikidata, les différente Caisses d'allocations familiales de France, ainsi que leurs adresse et leurs images. Toutefois, nos requêtes n'ont pas affiché le résultat escompté. Nous avons testé plusieurs requêtes parmi lesquelles la suivante :
SELECT ?caf ?cafLabel ?localisation ?latitude ?longitude 
WHERE { 
?caf wdt:P31 wd:Q1395254. 
?caf wdt:P17 wd:Q142. 
?caf wdt:P276 ?localisation. 
?location wdt:P625 ?coordinate. 
?coordinate wdt:P2048 ?latitude. 
?coordinate wdt:P2049 ?longitude. 
SERVICE wikibase:label { 
bd:serviceParam wikibase:language "fr". } 
} LIMIT 100

En outre, nous avons également rencontré des difficultés pour afficher via une requête wikidata, les départements français sur une carte.
  
#### 2. La visualisation des données <a id="La-visualisation-des-données"></a>
 
* Chaque outil ayant sa particularité, la visualisation des données nécessite à chaque fois d'adapter la forme du fichier et même l'orthographe des données qu'il contient (comme ce fut le cas avec Datawrapper, où il a fallut changer les libellés des départements qui étaient écris en majuscules afin de respecter exactement la casse pour que datawrapper puisse valider les données) ;
* Le manque de données sur le nombres de foyers par départements pour les années 2016, 2017, 2019 et 2010 ;
* L'amélioration des données avec Open Office. Ces actions ont été fastidueuses, utiliser Openrefine aurait été plus bénéfique pour nous. Malheureusement, nous avons été formés à l'utilisation de ce logiciel trop tard.

  
# Conclusion <a id="Conclusion"></a>

Lorsque nous avons plusieurs données sous les yeux, il est généralement difficile voire impossible de tirer de bonnes interprétations. Ainsi, pour faciler l'assimilation d'une grande masse de données par notre esprit, des outils de visualisation existent. C'est dans cette optique que nous avons utilisé Flourish et Datawrapper pour visualiser notre jeu de données sur les populations bénéficiant d'une aide au logement de la CAF. Afin d'enrichir notre travail, nous avons croisé notre corpus principal avec les jeux de données sur la population, sur le nombre de foyers par département ainsi que sur le taux de chômage par département. Cela nous a permis de tirer des interprétations parfois contraires à celles qui nous semblaient évidentes. La visualisation des données permet donc, grâce à des paysages qui flattent les yeux et captent les esprits, de donner du sens et de rendre évidentes des interprétations issues des données brutes et en masse. 
La représentation des données sous forme visuelle nous a de ce fait permis d’assimiler un grand nombre d’informations en une fraction de seconde.
Visualiser les données c’est aussi tirer des conclusions à partir des données donc des éléments concrets.
