_**Mobile users**: view in landscape._

_All data on this site is updated nightly._

# Covid-19, confined # 2: Where France is now<sup>*</sup>
{:.no_toc}

<!--
(_Please wait a few seconds while the maps loads..._)

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/alerts.html" height="600" width="100%"></iframe>
{% endraw %}

**<sup>*</sup>** _<sub>based on 7-day rolling averages and the latest publicly-available indicator values. See <a href="about_data.html">About the data</a> for more info.</sub>_

### What does the info in the hover boxes mean?
{:.no_toc}

These are the indicators that determine overall alert level for a département or group of départements.

**This label**: | **represents**: | **which means:**
`niveau`| Alert level |_How actively the Covid-19 is spreading in an area. Reaching a new alert level "unlocks" possible new restrictions. Or eases them, if indicators go down._
`incid_tous` | Incidence rate |_The number of positive tests per 100k population. Officially, this is measured for major metropolitan areas. In these maps, it's measured at the department level. See [About](about_data.md#About this data (data caveats)) for details._
`incid_70+`| Incidence rate among the elderly |_Offically, this is the incidence rate for those over 65. In these maps, it's over 70. See **Data caveats** for details. Measured at department level._
`rea%` | Percent of ICU beds occupied by Covid patients | _The most worrisome indicator. It normally starts creeping up once the incidence rates are already high. Unlike incidence rates, it's measured at the regional level._

### How are alert levels triggered?
{:.no_toc}

These are the levels defined by the government

**Alert level** | **Incidence rate**<br>`incid_tous` | **Elderly incidence rate**<br>`incid_70+` | **ICU % saturation**<br>`rea%`
**OK** | <= 50 | <= 50 | <= 30%
**Alerte** | > 50 | - |-
**Alerte renforcée** | > 150 | > 50 | -
**Alerte maximale** | > 250 | > 100 | > 30%
**Etat d'urgence sanitaire** | > 250 | > 100 | > 60%

Since there are scenarios where a department has passed one threshold, but not the other(s) needed to move up an alert level. For these scenarios I've added the **Vigilence** level.

The typical example is a département with `incid_70+` well above 50, but a low `incid_tous`. This could be a result of testing bias: a cluster in an EHPAD leads to a disproportionate amount of testing of the older population compared to the general population.
-->

## Overall incidence rate down in most departments

Nov 14: the majority of mainland France departments have seen their `incid_tous` rates decrease since the confinement began.

Also, to make sure the decreases aren't just due to less testing, these counts are based on % change of `incid_tous` less the % change  the `tx_depistage`.

{% raw %}<iframe width="100%" height="500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/285.embed?showlink=false"></iframe>
{% endraw %}

For a daily breakdown by department, [check out these heatmaps](confined.md){:target="_blank"}.

### Where's the alert map?

Nov 14: The alert map has been moved off this page for the time being. The alert triggers no longer make sense now that incidence rates have begun falling, since they drop so much quicker than ICU saturation rates.

For example, we now have departments back down to the `alerte` level because `incid_tous` has gone below 150 cases for 100k population, but `rea%` is still above 60%. In some departments, regional ICU saturation is at 97% but incidence rates are now relatively low.

How do you classify these? Even the government now has abandoned their official alert map.

Nevertheless, for the sake of consistency & transparency, you can still view my map [here](alerts.html).

## ICU saturation is still growing in nearly all departments

Unfortunately, it looks like confinement has had zero effect so far for ICU occupancy by Covid patients.

{% raw %}<iframe width="100%" height="500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/283.embed?showlink=false"></iframe>
{% endraw %}

For a daily breakdown by department, [check out these heatmaps](confined.md){:target="_blank"}.

## And so ICUs maps keep getting redder
{:.no_toc}

ICU saturation is normally measured by region since hospitals are managed at the regional level, allowing for inter-region transfers of patients.

The hope for the 2nd wave was to keep hospitals open for non-Covid patients, which  is why the threshold for Etat d'urgence sanitaire is "only" at 60%.

Nov 4: To make the regional ICU map more informative with so many regions over 60% saturation, the maximum value for the colorscale has been increased from 60 to 100.

<blockquote><b>Data notes</b>:<br>
* Hospital data for that day available after 14h, but there's a 3-day lag with testing data, which is why the ICU maps are more recent than the alert map.
<br>
<br>
* To show Covid's full impact on ICU saturation, `rea%` & `rea%_dep` are based on the number of permanent ICU beds. Although hospitals have found some additional ICU capacity for the 2nd wave, this comes at the expense of other hospital care.
</blockquote>

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/rea_pct_region.html" height="600" width="100%"></iframe>
{% endraw %}

The map below shows how much `rea%` varies by department.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/rea_pct_dept.html" height="600" width="100%"></iframe>
{% endraw %}

# Where France is going
{:.no_toc}

The curves show that the incidence rate for the elderly is growing faster than the overall incidence rate.
* Sept 1: `incid_70+` was lagging `incid_tous` by about 2.5 weeks.
* Oct 23: the lag was only 3 days.
* Oct 28: the lag was less than 2 days.
* Nov 15: since confinement, incidence rates are falling overall, but `incid_70+` is falling much slower than for `incid_tous`.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_fr_trends.html" height="500" width="100%"></iframe>
{% endraw %}

Granted, incidence rates are heavily subject to testing bias. For example, since mid-September there's been a change in testing strategy to reduce bottlenecks, by  prioritizing those who are symptomatic, and who are also more likely to be older.

Regardless of incidence rates, though, the plot above shows that ICU saturation is already above 30% nationally.

Moreover, if you isolate `rea%` (click the legend) and zoom in from Sept 1, you can  see how the increase in ICU occupancy has accelerated after Oct 15.

# How these trends play out in hospitals
{:.no_toc}

Below you can see a rise in ICU arrivals around September 1st (zoom in). Deaths (`dc`) had already started a slow rise that by late October is looking speeding up.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_rea_dc_trends.html" height="500" width="100%"></iframe>
{% endraw %}

(The big bump from Sept 18 to 25 was not from new deaths those days, but the result of catching up on a [data-entry backlog](https://www.bfmtv.com/sante/coronavirus-un-rattrapage-de-donnees-provoque-une-forte-hausse-du-nombre-de-deces-dans-les-hopitaux_AN-202009180358.html){:target="_blank"}.)

**These national trends hide regional variations. Compare regions and departments [on this page](region_kpi.html)**.

# How is France doing compared to our neighbours?
{:.no_toc}

Oct 23: In an odd coincidence, the countries where French is spoken are all at the top.

A more general observation: Spain & Belgium were, per capita, the worst-hit countries of Europe's first wave, only to became the heralds of the second wave. A symptom of the political bickering within their regions?

{% raw %}<iframe src="https://ourworldindata.org/coronavirus-data-explorer?zoomToSelection=true&minPopulationFilter=1000000&country=FRA~BEL~DEU~ITA~ESP~IRL~GBR~CHE~LUX&region=Europe&casesMetric=true&interval=smoothed&hideControls=true&perCapita=true&smoothing=7&pickerMetric=location&pickerSort=asc" loading="lazy" style="width: 100%; height: 600px; border: 0px none;"></iframe>
{% endraw %}

Again, keep in mind testing bias: the more tests per capita, the higher the incidence rates.

For example, [Luxembourg had sky-high testing rates during the summer](https://www.theguardian.com/world/2020/aug/18/luxembourg-covid-infection-rate-masks-mass-testing-regime-eu-travel-blacklist){:target="_blank"}, which was scaled back in the fall.

It's likely that Luxembourg's recent spike in incidence rate is partially due to testing being scaled back up, which is also more feasible in a country that is as tiny as it is wealthy.

# Learn more
{:.no_toc}

* TOC
{:toc}

## Alert FAQ

### What are the restrictions?

The possible restrictions are determined by the alert level in your area. (Descriptions in French)

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

Nov 3: this link returns a `404: file not found` error, without a redirect. The ministry's home page no longer refers to it, either, and instead points you to the SPF dashboard (link further down).

I have asked why via [twitter](https://twitter.com/sehosking/status/1323982747866681344?s=20){:target="_blank"}.

~~* [Ministère des Solidarités et Santé : Indicateurs de l’activité épidémique](https://solidarites-sante.gouv.fr/soins-et-maladies/maladies/maladies-infectieuses/coronavirus/etat-des-lieux-et-actualites/article/indicateurs-de-l-activite-epidemique)~~

~~The map is a static image followed by a long list of départements, which is what prompted me to create the interactive map here.~~

~~NB: Due to data availability, there will be some differences between the two. Please read [About the data](about_data.html)~~

**For the most recent case, hospitalization and death counts for France overall:**

* [Santé Publique France: COVID-19 : tableau de bord de l’épidémie en chiffres](https://www.santepubliquefrance.fr/dossiers/coronavirus-covid-19/coronavirus-chiffres-cles-et-evolution-de-la-covid-19-en-france-et-dans-le-monde#block-266151)

**For an iteractive map of the hospitalization and death counts from Santé Publique France:**

* [gouvernement.fr : Info coronavirus](https://www.gouvernement.fr/info-coronavirus/carte-et-donnees)
