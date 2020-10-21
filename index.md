_**Mobile users**: view in landscape._

# Covid-19: Where France is now<sup>*</sup>
{:.no_toc}

<blockquote><b>UPDATE</b>: Since midnight Oct 17 2020, 9 métropoles (shown on map) are under curfew from 21h to 06h for a minimum of 4 weeks. </blockquote> 

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts.html" height="600" width="100%"></iframe>
{% endraw %}

**<sup>*</sup>** _<sub>based on latest publicly-available indicator values. See <a href="about_data.html">About the data</a> for more info.</sub>_

# Where France is going
{:.no_toc}

French incidence rates are currently one of the highest in Europe and still rising quickly. Yet to spare the economy, we're still applying the brakes gently. 

As when driving a car, we can't expect to see an immediate slowdown: it will take longer to see flattening, but hopefully one that's sustainable.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_fr_trends.html" height="500" width="100%"></iframe>
{% endraw %}

A common argument that restrictions are exagerated and uncessesary is that hospitals numbers and deaths are relatively low despite high case numbers. That was true during the summer when it was overwhelmingly young people testing positive on the beach & mountains. 

But since _la rentrée_ that's no longer the case as the generations mingled once back home. 

Now older people are increasingly testing positve. In the plot above you can see `incid_70+` speed up around Sept 1. (Double-click on legend to show only that indicator, and this uptick will be more obvious.)

## The takeaway: Covid-19 is slow-acting
{:.no_toc}

An important takeaway here is with Covid-19: it normally takes a while before you feel it. This applies both to individuals infected _and_ symptomatic, and to society at large.

When people dismiss a rise in incidence rates by pointing to empty hospitals, keep this in mind: <blockquote>With widespread testing–as there was in France since mid-July–there will be a step-wise delay between the rises in overall incidence rate (`incid_tous`), elderly incidence rate (`incid_70+`), and ICU occupancy (`rea%`)</blockquote>. 

And, unfortunately, deaths.

Speaking of which...

# How these trends play out in hospitals
{:.no_toc}

Below you can see a corresponding rise in ICU arrivals around Sept 1. At this point, deaths (`dc`) had already started a slow rise that is now looking increasingly exponential. 

(The big bump from Sept 18 to 25 was not from new deaths, but the result of catching up on a [data-entry backlog](https://www.bfmtv.com/sante/coronavirus-un-rattrapage-de-donnees-provoque-une-forte-hausse-du-nombre-de-deces-dans-les-hopitaux_AN-202009180358.html)

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_rea_dc_trends.html" height="500" width="100%"></iframe>
{% endraw %}

**These national trends hide regional variations. Compare regions and departments [on this page](region_kpi.html)**.

# How is France doing compared to our neighbours?

Oct 19: We're up there, but several countries are catching up quickly.

{% raw %}<iframe src="https://ourworldindata.org/coronavirus-data-explorer?zoomToSelection=true&minPopulationFilter=1000000&country=FRA~BEL~DEU~ITA~ESP~IRL~GBR~CHE~LUX&region=Europe&casesMetric=true&interval=smoothed&hideControls=true&perCapita=true&smoothing=7&pickerMetric=location&pickerSort=asc" loading="lazy" style="width: 100%; height: 600px; border: 0px none;"></iframe>
{% endraw %}

# Learn more
{:.no_toc}

* TOC
{:toc}

## Alert FAQ

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

On October 14 2020 Emmanuel Macron announced a national health emergency due to pressure on ICUs in urban areas. As a result, <b>since midnight Oct 17 2020, 9 métropoles (shown on map) are under curfew from 21h to 06h for a minimum of 4 weeks</b>, possibly extending to 6.

In addition to the curfew, to slow the spread the following measures apply to the entire country:

* No gatherings of more than 6 people in public.

* Work from home at least 50 %.

* Festive events in village halls or community centers are forbidden.

* In enclosed spaces hosting seated spectators, a limit of 5 000 people, with a vacant seat between them. For other public-facing establishments where people are seated, the limit is 6 people.

* Sports training facilities: openings allowed depending on the specific alert status of the département.

### How can I see regional breakdowns for the indicators?

Go [here](region_kpi.html).

## Why create yet more Covid infographics?

The goal here is to see the alert statuses, possible restrictions, and the numbers that determine these alerts in one place. The official government sites are scattered, and either static images with a lot of dense text, or are interactive but do not show the indicators that determine alert levels. They are also hard to find.

Other sites I've visited are overwhelming. This site is my attempt at finding a middle ground. <a href="mailto:sehosking@gmail.com?subject=Feedback for covid_dataviz">Your feedback is welcomed</a>. 

## Where can I see the official government stats on Covid-19?

**The official alert map** with the most up-to-date numbers: 

* [Ministère des Solidarités et Santé : Indicateurs de l’activité épidémique](https://solidarites-sante.gouv.fr/soins-et-maladies/maladies/maladies-infectieuses/coronavirus/etat-des-lieux-et-actualites/article/indicateurs-de-l-activite-epidemique)

The map is a static image followed by a long list of départements, which is what prompted me to create the interactive map here.

NB: Due to data availability, there will be some differences between the two. Please read [About the data](about_data.html) 

**For the most recent case, hospitalization and death counts for France overall:**

* [Santé Publique France: COVID-19 : tableau de bord de l’épidémie en chiffres](https://www.santepubliquefrance.fr/dossiers/coronavirus-covid-19/coronavirus-chiffres-cles-et-evolution-de-la-covid-19-en-france-et-dans-le-monde#block-266151)

**For an iteractive map of the hospitalization and death counts from Santé Publique France:**

* [gouvernement.fr : Info coronavirus](https://www.gouvernement.fr/info-coronavirus/carte-et-donnees)

