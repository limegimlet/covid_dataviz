**Confused about alerts and restrictions in France?** Hover over this map to better understand the latest alert levels<sup>*</sup>. 

_**Mobile users**: view in landscape._

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts.html" height="600" width="100%"></iframe>
{% endraw %}

**<sup>*</sup>** _<sub>based on latest publicly-available indicator values. See **Data caveats** for more info.</sub>_

## What do these alert levels mean?
{:.no_toc}

These alerts are meant to convey how actively Covid-19 is spreading. Reaching a new alert level "unlocks" possible new restrictions. Or eases them, if indicators go down. 

## What does the info in the hover boxes mean?
{:.no_toc}

These are the indicators that determine overall alert level (`niveau_global`) for a département or group of départements. 

1. **Incidence rate** (`incid_tous`): the number of positive tests per 100k population.

2. **Incidence rate among the elderly** (`incid_70+`): offically, this is the incidence rate for those over 65; for these maps, it's over 70. To learn why, see **Data caveats**.

3. **Percent of ICU beds occupied by Covid patients** (`rea%`)

## How are alert levels triggered?
{:.no_toc}

**Alert level** | **Incidence rate** | **Elderly incidence rate** | **ICU % saturation**
Alerte | > 50 | - |-
Alerte renforcée | > 150 | > 50 | -
Alerte maximale | > 250 | > 100 | > 30
Etat d'urgence sanitaire | > 250 | > 100 | > 60

Their associated restrictions are described in **What are the restrictions?** further down.

# How are the indicators evolving?
{:.no_toc}

Here is a national overview:

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_fr_trends.html" height="600" width="100%"></iframe>
{% endraw %}

Keep in mind, there's a lot of regional variation:

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_rea%_by_reg.html" height="600" width="100%"></iframe>
{% endraw %}

# Find out more:
{:.no_toc}

* TOC
{:toc}

## What are the restrictions?

The possible restrictions are determined by the alert level in your area:

(In French: to be translated shortly.)

### Alerte

**Mésures déclenchées**

Pour ces départements, peu de mesures supplémentaires sont ajoutées, si ce n’est que les rassemblements devront être limités à 30 personnes. 

Toutefois, les préfets sont autorisés à prendre des mesures complémentaires si nécéssaire.

### Alerte renforcée

**Mésures déclenchées**

* la jauge des rassemblements est baissée de 5 000 à 1 000 personnes 
* les rassemblements de plus de 10 personnes dans l’espace public sont interdits 
* les fêtes locales et étudiantes sont interdites
* les gymnases, salles des fêtes et salles de sport sont fermés
* les bars et restaurant doivent fermer à partir de 22 heures. 

De plus, le ministre de la Santé a rappelé que “le télétravail doit être favorisé autant que possible, surtout sur les publics vulnérables”.

### Alerte maximale

**Mésures déclenchées**

* la fermeture totale des bars et des restaurants, ainsi que les établissements recevant du public, sauf s’il existe un protocole sanitaire strict. 

NB: Les théâtres, les cinémas et les musées peuvent donc rester ouverts. 

“Ces dispositions sont temporaires, l’objectif est qu’elles ne durent pas plus de deux semaines”, a déclaré Olivier Véran.

### État d’urgence sanitaire

**Mésures déclenchées**

Le ministre des Solidarités et de la Santé n’a pour l’heure pas détaillé les mesures qui seraient décidées avec ce seuil d’alerte.

## How can I see regional breakdowns for the indicators?

Go [here](region_kpi.html).

## Why create yet more Covid infographics?

The official government sites are not informative enough. They show either static images, or are interactive but do not show the indicators that determine alert levels & possible restrictions. They are also hard to find.

Check them out yourself (in French):

* Santé Publique France: [COVID-19 : tableau de bord de l’épidémie en chiffres](https://www.santepubliquefrance.fr/dossiers/coronavirus-covid-19/coronavirus-chiffres-cles-et-evolution-de-la-covid-19-en-france-et-dans-le-monde#block-266151)

_Shows most recent case, hospitalization and death counts for France overall._

* gouvernement.fr : [Info coronavirus](https://www.gouvernement.fr/info-coronavirus/carte-et-donnees)

_Interactive map of numbers from Santé Publique France._

* Ministère des Solidarités et Santé: [Indicateurs de l’activité épidémique](https://solidarites-sante.gouv.fr/soins-et-maladies/maladies/maladies-infectieuses/coronavirus/etat-des-lieux-et-actualites/article/indicateurs-de-l-activite-epidemique)

_The official, albeit static, alert map that I've tried to replicate (but please see section below)._


# Data caveats - please read!

These maps display Covid-19 indicator values. **The values are merely an approximation of the official government figures** used to determine if a threshold has been reached.

I cannot replicate government figures completely due to the following:

* a 3-day lag in testing numbers. Since incidence rates are based on testing data, the 'latest' `incid_tous` & `incid_70+` values here will always from at least 3 days earlier.


* _Personnes agées_ for the French government means people 65 or older. However, the publicly-available testing data only breaks down age in 10-year increments. As a result the maps here show incidence rates for people 70 or older( `incid_70+`). In other words, they are understated compared to official government figures.


* The government examines overall incidence rates for the major metropolitan in France when classifiying a département. These are Paris, Rennes, Bordeaux, Toulouse, Montpellier, Marseilles, Lyon, Grenoble and Lille. However publicly-available testing data is by département, not commune. Paris is the only city with its own département. This likely means the overall incidence rate in these maps (`incid_tous`) is also understated.

# Data sources

The source data comes from Santé Publique France:

* [Source data for incidence rates](https://www.data.gouv.fr/fr/datasets/donnees-relatives-aux-resultats-des-tests-virologiques-covid-19/)
* [Source data for ICU saturation](https://www.data.gouv.fr/en/datasets/donnees-hospitalieres-relatives-a-lepidemie-de-covid-19/)

I then did additional data processing to:

* create rolling 7-day sums for positive tests and total number of tests 

* calculate incidence rates for entire population as well as incidence rates for the 70+ age group

* calculate percentage of ICU beds occupied by Covid patients

* classify each département according to the alert thresholds described above...to the best of my ability with publicly-available data. See 'Data Caveats' above.

You can find the data processing scripts [here](https://github.com/limegimlet/covid19/tree/master).
