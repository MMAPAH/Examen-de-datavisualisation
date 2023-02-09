<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0APREFIX%20bd%3A%20%3Chttp%3A%2F%2Fwww.bigdata.com%2Frdf%23%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0APREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0ASELECT%20DISTINCT%20%3Fr%C3%A9gionsLabel%20%3Fgeoloc%20%0AWHERE%20%7B%0A%0A%3Fr%C3%A9gions%20wdt%3AP31%20wd%3AQ36784.%20%0A%3Fr%C3%A9gions%20wdt%3AP625%20%3Fgeoloc%20.%0A%0A%0ASERVICE%20wikibase%3Alabel%7B%20%0Abd%3AserviceParam%20wikibase%3Alanguage%20%22fr%2Cen%22%7D%0A%7D%0A%0A%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups"></iframe>
# Carte des différentes régions de France

## Table des matires
### I. Origine du jeu de données, contrôle et amélioration de la qualité des données
### 1. Origine du jeu de données 
### 2. Contrôle et amlioration de la qualité des données







 
## I. Origine des jeux de données, contrôle et amélioration de la qualité des données 

    Pour mieux comprendre notre jeu de données, il est nécessaire de présenter ses origines ainsi que toutes les manipulations qui y ont été faites afin d'améliorer sa qualité. 

### 1. Origine du jeu de données

    Notre jeu de données principal a pour titre "Population couverte par une aide personnelle au logement en décembre par EPCI". Couvrant la période de 2016 à 2020, il est fourni sous licence ouverte sur le site open data (CAFDATA) de la Caisse des Allocations Familiales (CAF). En effet, la CAF est un organisme de droit privé 1, 2 à compétence départementale 3 chargée de verser aux particuliers des prestations financières à caractère familial ou social (prestations légales), dans des conditions déterminées par la loi 4. Elle a de ce fait une compétence territoriale et une mission de service public qui consiste à reverser des aides financières soit pour des raisons familiales, soit pour des raisons sociales.
    En vue de croiser ce jeu de données à un autre pour ressortir plus amples interprétations, nous avons choisi trois (03) jeux de données à savoir :
  - le taux de chômage localisé aux 3ᵉ trimestre (2016-2020) par départements, disponible sur le site de l'Institut National de la Statistique et des Etudes Economiques en abrégé INSEE ;
  - la population par région, téléchargeable sur le site de l'Institut Nationel d'Etudes Démographique (INED) ;
  - et le nombre de ménages par régions disponible sur le même site que le précédent.
    
### 2. Contrôle et amlioration de la qualité des données

    Le jeu de données provenant de la CAF est relativement complet. En effet, nous avons un fichier contenant 6286 lignes quasiment remplies. Cependant, le sprint qualité nous a permis de constater que dans certains départements quelques cellules sont incomplètes. Il s’agit principalement des  Etablissements Publics de Coopration Intercommunale (EPCI) des départements ayant les codes suivants : 971, 972, 973, 974, 976.  
Ainsi, nous avons choisi de supprimer ces 23 (EPCI) présents sur la capture d'écran ci-après :

![image](https://user-images.githubusercontent.com/121296617/212471136-f34dd37f-4d17-45a0-b012-2d02607d0925.png)

Nous avons également inséré dans notre jeu de données une colonne intitulée " LIBELLE_DEP " afin d'associer à chaque numéro de département, son nom.
Notre jeu de données se présente ainsi de la manière suivante :

<iframe title="Population couverte par une aide personnelle au logement en décembre (2016-2020)" aria-label="Table" id="datawrapper-chart-n1Azn" src="https://datawrapper.dwcdn.net/n1Azn/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="1273" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>

## II. Visualisation des données

### 1. Première visualisation : Nombre de foyers couverts par une aide au logement par département

EXPLIQUER ICI LES DIFFERENTES AIDES PROJETEES : BRANCHE FAMILLE? APL, ALS, ALF 
 
<div class="flourish-embed flourish-chart" data-src="visualisation/12677752"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
 
 ### 2. Deuxième visualisation : Pourcentage d'allocataires de la branche famille par ordre croissant des régions

<iframe title="[ Pourcentage d'allocataires de la branche famille par ordre croissant des régions]" aria-label="Multiple Donuts" id="datawrapper-chart-aCbwt" src="https://datawrapper.dwcdn.net/aCbwt/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="686" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>



### 2. Troisième visualisation : Croisement des données
 
 Le but de cette visualisation est de faire le rapport entre le nombre total d'allocataires de la branche famille sous l'angle des régions, le nombre de ménages et l'estimation de la population. Ces données complémentaires ont été prises sur le site de l'Institut National d'Etudes Démographiques (INED). La période considérée est de 2016 à 2018. Toutefois, en ce qui concerne le nombre de ménages, nous n'avons uniquement trouvé les données sur l'année 2018.

<div class="flourish-embed flourish-chart" data-src="visualisation/12677782"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

### 3. Quatrième visualisation : Rapport entre les aides aux logement et le taux de chômage par département

Cette visualisation a pour but de vérifier s'il existe une relation entre le taux de chômage et le nombre d'aides allouées aux populations en fonction des départements. Pour cela, nous avons limité notre étude à 2016 et 2020 qui réprésentent les dates extrêmes de notre période d'étude. L'outil utilisé est datawrapper. 
 
<iframe title="[ Taux de chômage, 2016]" aria-label="Map" id="datawrapper-chart-apMad" src="https://datawrapper.dwcdn.net/apMad/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="624" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
2016 : taux de chômage entre 6,2% et 15,4%.
 Cette carte projette le taux de chômage dans les départements français en 2016. Nous pouvons constater un taux compris entre 9,2% et 10,9% (avec une tendance élevée au nord et au sud). Dans les départements situés à l'Est et à Ouest (avec une nimorité au Centre), la tendance est plutôt comprise entre 6% et 9,2%.
 
<iframe title="[ Taux de chômage, 2020]" aria-label="Map" id="datawrapper-chart-wyOta" src="https://datawrapper.dwcdn.net/wyOta/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="663" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
 2020 : taux de chômage entre 4,6% et 12,5%
 En 2020, on note tout d'abord la baisse du taux de chômage. Ce dernier est compris entre 4,6% et 12,5%. Toutes les taux élévés restent visbiles dans les départements du Nord et du Sud. 
 
Nous avons choisi de visualiser les données relatives aut total des allocataires de la branche famille. En effet, la branche Famille gère deux minima sociaux et un complément de revenus à savoir :
- l'allocation aux adultes handicapés (Aah), versée à plus d'un million de personnes de plus de 20 ans dont le taux d'invalidité est au moins de 50% et qui ont de faibles ressources financières ; 
- et le revenu de solidarité active (Rsa), prestation qui garantit un montant minimal de ressources aux personnes sans activité. Il assure également un complément de revenu aux personnes qui ont de faibles revenus d'activité. Ce qui permet de faire le lien avec la visualisation du taux de chômage.
 
Notons que la notion d'allocataire est une notion de foyer (à rapprocher par exemple des ménages au sens Insee) et non d'individu. Ainsi, compter des allocataires signifie compter des foyers constitués de personnes seules ou de plusieurs personnes (familles).
 
<iframe title="[ Total allocataires de la branche famille, 2016]" aria-label="Map" id="datawrapper-chart-QxJRs" src="https://datawrapper.dwcdn.net/QxJRs/5/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="651" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>
 
On constate ici que le nombre de foyers bénéficiant d'une aide de la branche famille est élevé de façon particulière dans les départements de l'Ouest, ainsi que dans une partie des départements situés au Nord et au Sud. 
 
 
<iframe title="[ Total allocataires de la branche famille, 2020 ]" aria-label="Map" id="datawrapper-chart-PEtBw" src="https://datawrapper.dwcdn.net/PEtBw/2/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="687" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();</script>

Conclusion partielle 
 
En 2020, le nombre d'allocatires à considérablement augmenté dans toutes les régions. L'on aurait logiquement pensé que plus le taux de chômage diminuait, plus le nombre de foyers bénéficiares d'aides de la branche famille diminuerait également. Ce qui n'est pourtant pas le cas. En effet, entre 2016 et 2020, le taux de chômage est passé de l'intervalle 6,2%-15,4% à l'intervalle 4,6%-12,5%, Or le nombre d'allocataires est passé de /////////////////////////////////////////////////////////////. Il est important de noter qu'en 2020, en plus des régions partielles du Nord et du Sud ayant des taux élevés de chômage, tous les départements de l'Ouest perçoievnt une aide de la branche famille avec un nombre assez élevé. En tenant compte du fait que cette région avait un faible taux de chômage cette même année, nous pouvons dire qu'elle a soit un nombre élévé d'adultes handicapés, soit un fort taux de personnes à faibles revenus d'activité.
 
 


