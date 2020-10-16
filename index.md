**Confused about alerts and restrictions in France?** Hover over this map to better understand the latest alert levels<sup>*</sup>. 

_**Mobile users**: view in landscape._

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts.html" height="600" width="100%"></iframe>
{% endraw %}

**<sup>*</sup>** _<sub>based on latest publicly-available indicator values. See **Data caveats** for more info.</sub>_

# How are the alert indicators evolving?
{:.no_toc}

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_fr_trends.html" height="500" width="100%"></iframe>
{% endraw %}

**These national numbers hide regional variations. You can compare regions and departments [on this page](region_kpi.html)**.

# Learn more
{:.no_toc}

* TOC
{:toc}

## Alert FAQs

### What does the info in the map hover boxes mean?

These are the indicators that determine overall alert level for a département or group of départements. 

**This label**: | **represents**: | **which means:**
`niveau_global`| Alert level |_How actively the Covid-19 is spreading in an area. Reaching a new alert level "unlocks" possible new restrictions. Or eases them, if indicators go down._
`incid_tous` | Incidence rate |_The number of positive tests per 100k population. Officially, this is measured for major metropolitan areas. In these maps, it's measured at the department level. See **Data caveats** for details._
`incid_70+`| Incidence rate among the elderly |_Offically, this is the incidence rate for those over 65. In these maps, it's over 70. See **Data caveats** for details. Measured at department level._
`rea%` | Percent of ICU beds occupied by Covid patients | _The most worrisome indicator. It normally starts creeping up once the incidence rates are already high. Unlike incidence rates, it's measured at the regional level._

### How are alert levels triggered?

These are the levels defined by the government

**Alert level** | **Incidence rate** | **Elderly incidence rate** | **ICU % saturation**
**Alerte** | > 50 | - |-
**Alerte renforcée** | > 150 | > 50 | -
**Alerte maximale** | > 250 | > 100 | > 30
**Etat d'urgence sanitaire** | > 250 | > 100 | > 60

Since there are scenarios where a department has passed a threshold for some, but not all indicators to move up an alert level. For these scenarios I've added the **Vigilence** level.


The typical example is a département with `incid_70+` well above 50, but a low `incid_tous`. This could be a result of testing bias: a cluster in an EHPAD leads to a disproportionate amount of testing of the older population compared to the general population. 

### What are the restrictions?

The possible restrictions are determined by the alert level in your area:

(In French: to be translated shortly.)

#### Alerte

Pour ces départements, peu de mesures supplémentaires sont ajoutées, si ce n’est que les rassemblements devront être limités à 30 personnes. 

Toutefois, les préfets sont autorisés à prendre des mesures complémentaires si nécéssaire.

#### Alerte renforcée

* la jauge des rassemblements est baissée de 5 000 à 1 000 personnes 
* les rassemblements de plus de 10 personnes dans l’espace public sont interdits 
* les fêtes locales et étudiantes sont interdites
* les gymnases, salles des fêtes et salles de sport sont fermés
* les bars et restaurant doivent fermer à partir de 22 heures. 

De plus, le ministre de la Santé a rappelé que “le télétravail doit être favorisé autant que possible, surtout sur les publics vulnérables”.

#### Alerte maximale

* la fermeture totale des bars et des restaurants, ainsi que les établissements recevant du public, sauf s’il existe un protocole sanitaire strict. 

NB: Les théâtres, les cinémas et les musées peuvent donc rester ouverts. 

“Ces dispositions sont temporaires, l’objectif est qu’elles ne durent pas plus de deux semaines”, a déclaré Olivier Véran.

#### État d’urgence sanitaire

Le ministre des Solidarités et de la Santé n’a pour l’heure pas détaillé les mesures qui seraient décidées avec ce seuil d’alerte.

### How can I see regional breakdowns for the indicators?

Go [here](region_kpi.html).

### Why create yet more Covid infographics?

The official government sites are not informative enough. They show either static images, or are interactive but do not show the indicators that determine alert levels & possible restrictions. They are also hard to find.

### Where can I see the official government stats on Covid-19

The ones that I've been referring to:

* Ministère des Solidarités et Santé: [Indicateurs de l’activité épidémique](https://solidarites-sante.gouv.fr/soins-et-maladies/maladies/maladies-infectieuses/coronavirus/etat-des-lieux-et-actualites/article/indicateurs-de-l-activite-epidemique)

_The official & most current alert map (albeit a static one) that is being emulated here (but please read **Data Caveats** section below). 

* Santé Publique France: [COVID-19 : tableau de bord de l’épidémie en chiffres](https://www.santepubliquefrance.fr/dossiers/coronavirus-covid-19/coronavirus-chiffres-cles-et-evolution-de-la-covid-19-en-france-et-dans-le-monde#block-266151)

_Shows most recent case, hospitalization and death counts for France overall._

* gouvernement.fr : [Info coronavirus](https://www.gouvernement.fr/info-coronavirus/carte-et-donnees)

_Interactive map of the hospitalization numbers from Santé Publique France._
