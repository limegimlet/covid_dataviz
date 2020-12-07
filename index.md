_**Mobile users**: view in landscape._

_All plot data on this site is updated nightly._

# Confinement # 2: Where France is now
{:.no_toc}

<blockquote><b>NEW</b>: While the data on this site is updated nightly, the text is not! <b>For the latest summaries check the <a href="https://limegimlet.github.io/learning/" target="_blank">blog</a></b>.</blockquote>

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

## Number of departments where incidence rates are decreasing

<blockquote><b>Data notes</b>: to make sure these decreases aren't simply due to less testing, these <b>counts are based on the NET incidence rate change</b>: % change of `incid_tous` minus  % change of `tx_depistage`.</blockquote>

{% raw %}<iframe width="100%" height="500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/285.embed?showlink=false"></iframe>
{% endraw %}


For a daily breakdown by department, [check out these heatmaps](confined.md#incidence-rate--decreases){:target="_blank"}.

## Elderly incidence rate decreasing in more departments

<blockquote><b>Data notes</b>: to make sure these decreases aren't simply due to less testing, these <b>counts are based on the NET incidence rate change</b>: % change of `incid_tous` minus  % change of `tx_depistage`.</blockquote>

{% raw %}<iframe width="100%" height="500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/315.embed?showlink=false"></iframe>
{% endraw %}

For a daily breakdown by department, [check out these heatmaps](confined.md#elderly-incidence-rate--decreases){:target="_blank"}.

## ICU saturation increasing in nearly all departments

{% raw %}<iframe width="100%" height="500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/283.embed?showlink=false"></iframe>
{% endraw %}

For a daily breakdown by department, [check out these heatmaps](confined.md#icu-saturation--decreases){:target="_blank"}.


## ICU saturation: slowly going down
{:.no_toc}

### At the regional level

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/rea_pct_region.html" height="600" width="100%"></iframe>
{% endraw %}

<blockquote><b>Data notes</b>:<br>
* Hospital data for that day available after 14h, but there's a 3-day lag with testing data, which is why the ICU maps are more recent than the alert map.
<br>
<br>
* To show Covid's full impact on ICU saturation, `rea%` & `rea%_dep` are based on the number of permanent ICU beds. Although hospitals have found some additional ICU capacity for the 2nd wave, this comes at the expense of other hospital care.
</blockquote>

### At the departmental level

The map below shows how much `rea%` varies by department, even within the same region.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/rea_pct_dept.html" height="600" width="100%"></iframe>
{% endraw %}

### What does ICU saturation mean, in reality?

Le Parisien has been profiling what's going on in the hospitals around France during the second wave. Unfortunately, most are behind a paywall.

One example (that's also open) is the city of Orléans in the Loiret, part of the Centre-Val-de-Loire region. As of Nov 14, Loiret's `rea%_dep` was at 153%, while region `rea%` was 90%.

In the article from Nov 13th, they described having added 30 additional ICU beds and needing to postpone 35-40% of surgeries.

What it means is if you need a tumor removed, your surgery will still go ahead. On the other hand, surgeries for non life-threatening issues such as prostate surgery, breast reconstruction after a masectomy, or IVF procedures will be postponed.

Nonetheless, these delays can still cause pyschological harm and impact quality of life; for IVF they also impact outcome: time counts when it comes to fertility.

Full article (FR) [here](https://www.leparisien.fr/societe/sante/covid-19-le-centre-hospitalier-d-orleans-contraint-de-transferer-des-patients-vers-tours-et-blois-13-11-2020-8408156.php){:target="_blank"}.

## Where's the alert map?

Nov 14: The alert map has been moved off this page for the time being. The alert triggers no longer make sense now that incidence rates have begun falling, since they drop so much quicker than ICU saturation.

For example, we now have departments back down to the `alerte` level because `incid_tous` has gone below 150 cases for 100k population, but `rea%` is still above 60%. In some departments, regional ICU saturation is at 97% but incidence rates are now relatively low.

How do you classify these? Even the government now has abandoned their official alert map (see the section on official numbers under Alert FAQs, further below).

Nevertheless, for the sake of consistency & transparency, you can still view my map [here](alerts.html).

# Where France is going
{:.no_toc}

The curves show that the incidence rate for the elderly is growing faster than the overall incidence rate.

* Dec 7: both `incid_tous` & `incid_70+` have flattened, but `incid_70+` is "stuck" at a much higher level than `incid_tous`. Is this testing biais due to clusters in EHPADs, or is it indeed representative?
* Nov 15: since confinement, incidence rates are falling overall, but `incid_70+` is falling much slower than for `incid_tous`.
* Oct 28: the lag was less than 2 days.
* Oct 23: the lag was only 3 days.
* Oct 23: the lag was only 3 days.

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_fr_trends.html" height="500" width="100%"></iframe>
{% endraw %}

# How these trends play out in hospitals
{:.no_toc}

{% raw %}<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://limegimlet.github.io/covid_dataviz/kpi_rea_dc_trends.html" height="500" width="100%"></iframe>
{% endraw %}

**These national trends hide regional variations. Compare regions and departments [on this page](region_kpi.html)**.

# How is France doing compared to our neighbours?
{:.no_toc}

Dec 7: Many countries are experiencing the same pattern of sharp decline after 2nd wave restrictions, only to see a flattening as the holidays approach. Exceptions are Italy and Germany.

{% raw %}<iframe src="https://ourworldindata.org/coronavirus-data-explorer?zoomToSelection=true&minPopulationFilter=1000000&country=FRA~BEL~DEU~ITA~ESP~IRL~GBR~CHE~LUX&region=Europe&casesMetric=true&interval=smoothed&hideControls=true&perCapita=true&smoothing=7&pickerMetric=location&pickerSort=asc" loading="lazy" style="width: 100%; height: 600px; border: 0px none;"></iframe>
{% endraw %}

Again, keep in mind testing bias: the more tests per capita, the higher the incidence rates.

For example, [Luxembourg had sky-high testing rates during the summer](https://www.theguardian.com/world/2020/aug/18/luxembourg-covid-infection-rate-masks-mass-testing-regime-eu-travel-blacklist){:target="_blank"}, which was scaled back in the fall.

It's likely that Luxembourg's recent spike in incidence rate is partially due to testing being scaled back up, which is also more feasible in a country that is as tiny as it is wealthy.

# Learn more
{:.no_toc}

* TOC
{:toc}

## FAQs

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
