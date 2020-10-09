# Covid 19 Alert levels in France
* _**Mobile users**: view in landscape mode._
* _**To view indicator values**: touch/hover over département._

You can find data caveats and alert descriptions below the maps.
{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts.html" height="600" width="100%"></iframe>
{% endraw %}

## Alerts in Ile de France
{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts_idf.html" height="500" width="100%"></iframe>
{% endraw %}

# Why did I make this?

I wanted to be able to see all indicator numbers for different areas of France in one interactive map, and suspect I'm not alone. The official maps from the French governenment are either static images, or are interactive but do not show the indicators that determine alert levels & restrictions.

# Data caveats - please read!

These maps display Covid-19 indicator values. **The values are merely an approximation of the official government figures** used to determine if a threshold has been reached.

I cannot replicate government figures completely due to the following:

* a 3-day lag in testing numbers. Since incidence rates are based on testing data, the 'latest' `incid_tous` & `incid_70+` values here will always from at least 3 days earlier.


* _Personnes agées_ for the French government means people 65 or older. However, the publicly-available testing data only breaks down age in 10-year increments. As a result the maps here show incidence rates for people 70 or older( `incid_70+`). In other words, they are understated compared to official government figures.


* The government examines overall incidence rates for the major metropolitan in France when classifiying a département. These are Paris, Rennes, Bordeaux, Toulouse, Montpellier, Marseilles, Lyon, Grenoble and Lille. However publicly-available testing data is by département, not commune. Paris is the only city with its own département. This likely means the overall incidence rate in these maps (`incid_tous`) is also understated.

Read on for a description of alert levels (for now, still _en français_, translation coming soon) as well as data sources & processing. 

# Les seuils d'alerte (VF)

Les seuils d'alerte sont determinés par les indicateurs suivants : 

* le taux d'incidence, c'est à dire **le nombre de cas pour 100 000 habitants** (on map: `incid_tous`)
* le taux d'incidence chez les personnes agées, c'est à dire les plus de 65 ans (on map: `incid_70+` - see 'Data caveats' on why 70 instead of 65)
* Le pourcentage des lits en réanimation occupés par des patients Covid-19 (on map: `rea%`)

## Alerte

Le premier niveau, les zone en “alerte”, correspond à ce qu’on appelait jusqu’ici la zone rouge, ces lieux où le virus circule activement.

* le taux d’incidence de plus de 50

La circulation du virus reste néanmoins “peu intense” chez les plus de 65 ans et le Covid a un “faible impact sur les réanimations”.

**Mésures déclenchées**

Pour ces départements, peu de mesures supplémentaires sont ajoutées, si ce n’est que les rassemblements devront être limités à 30 personnes. 

Toutefois, les préfets sont autorisés à prendre des mesures complémentaires si nécéssaire.

## Alerte renforcée

Le seuil d’“alerte renforcée”, également appelé “super-rouge”, correspond à :

* un taux d’incidence de plus de 150
* un taux d’incidence de plus de 50 chez les personnes âgées*

**Mésures déclenchées**

* la jauge des rassemblements est baissée de 5 000 à 1 000 personnes 
* les rassemblements de plus de 10 personnes dans l’espace public sont interdits 
* les fêtes locales et étudiantes sont interdites
* les gymnases, salles des fêtes et salles de sport sont fermés
* les bars et restaurant doivent fermer à partir de 22 heures. 

De plus, le ministre de la Santé a rappelé que “le télétravail doit être favorisé autant que possible, surtout sur les publics vulnérables”.

## Alerte maximale

Le seuil d’“alerte maximale”, appelé rouge écarlate,  représente :

* un taux d’incidence de plus de 250
* un taux d’incidence de plus de 100 chez les personnes âgées. 
* les services de réanimation comptent au moins 30% de patients malades du Covid

**Mésures déclenchées**

* la fermeture totale des bars et des restaurants, ainsi que les établissements recevant du public, sauf s’il existe un protocole sanitaire strict. 

NB: Les théâtres, les cinémas et les musées peuvent donc rester ouverts. 

“Ces dispositions sont temporaires, l’objectif est qu’elles ne durent pas plus de deux semaines”, a déclaré Olivier Véran.

## État d’urgence sanitaire

L’état d’urgence sanitaire est le seuil d’alerte le plus élevé, correspondant à la couleur noire :

* un taux d’incidence de plus de 250
* un taux d’incidence de plus de 100 chez les personnes âgées. 
* les services de réanimation comptent au moins 60% de patients malades du Covid.

**Mésures déclenchées**

Le ministre des Solidarités et de la Santé n’a pour l’heure pas détaillé les mesures qui seraient décidées avec ce seuil d’alerte.

# Data sources

The source data comes from Santé Publique France:

* [Source data for incidence rates](https://www.data.gouv.fr/fr/datasets/donnees-relatives-aux-resultats-des-tests-virologiques-covid-19/)
* [Source data for ICU saturation](https://www.data.gouv.fr/en/datasets/donnees-hospitalieres-relatives-a-lepidemie-de-covid-19/)

I then did additional data processing to:

* create rolling 7-day sums for positive tests and total number of tests 

* calculate incidence rates for entire population as well as incidence rates for the 70+ age group

* calculate percentage of ICU beds occupied by Covid patients

* classify each département according to the alert thresholds described above...to the best of my ability with publicly-available data. See 'Data Caveats' below.

You can find the data processing scripts [here](https://github.com/limegimlet/covid19/tree/master).
