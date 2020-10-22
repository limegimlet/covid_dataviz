# About this site

The data here is meant to help you understand how Covid-19 is evolving in different areas of France. 

The goal is to give you more context beyond increasingly-alarming case numbers: Is that good or bad? Are we heading up or down?

To that end (in case you haven't already noticed) these plots are all interactive: zoom in on a area to get more detail, or select just a few lines by clicking the legend. 

Oh, and mobile users: _please turn your phone **sideways**._

### Coming soon

* **tracking the curfew areas** - where Covid is the most active - to see how if/when/how fast the case counts & ICU occupancy goes down. Curfew started on Sat October 17 at 21h00. Progress will be slow—experts say it will take two weeks minimum according to exports to expect any changes—but being able to visualize progress is always motivating.

* **adding alert thresholds** to the indicator plots, which helps put the Covid curves in perspective.

* **creating a map of the metropoles under curfew**

* **discussing how testing influences incidence rates** 

## About Covid-19 data

To borrow a phrase from economists, there's no such thing as a perfect dataset. Covid-19 data is the embodiment of this. It's extremely hard to establish any certainties with a novel virus that spreads so easily, manifests with such varied symptoms and outcomes, and wreaks literal havoc across so much of the world.

In such a fast-evolving environment, data collection is not going to be exhaustive, nor ideal. The New York Times, Le Monde, The Guardian and the Canadian Broadcasting Company, just to name my go-to information sources as a layperson, have all reported stories of delayed results, not enough testing of asymptomatics, technical snafus, among other problems. 

This applies to all Covid-19 data, not just what is visualized here. 

Nonetheless, even if Covid data is not 100% accurate, it still provides decent benchmarks of where we are, and rough signposts of where we might be heading in near future. 

## About this data (data caveats)

These maps display Covid-19 indicator values. **The values are merely an approximation of the official government figures** used to determine if a threshold has been reached.

I cannot replicate government figures completely due to the following:

* a 3-day lag in testing numbers. Since incidence rates are based on testing data, the 'latest' `incid_tous` & `incid_70+` values here will always from at least 3 days earlier.


* _Personnes agées_ for the French government means people 65 or older. However, the publicly-available, daily testing data only breaks down age in 10-year increments. As a result the maps here show incidence rates for people 70 or older( `incid_70+`). In other words, they are understated compared to official government figures.


* The government examines overall incidence rates for the major metropolitan in France when classifiying its surrounding département. Until Oct 15 2020 there wasn't any data on these metropoles, so I've applied those thresholds to departments instead. This likely means the overall incidence rate in these maps (`incid_tous`) is also understated compared to official figures.

## About me

Most of my professional life has been spent as a technical communicator, or herding others, at enterprise software firms in the search/analytics/business intelligence space. 

Upshot: I've spent a lot of time learning new, often pretty complex, tools quickly, just to explain to techie types the ABCs of searching/accessing/analyzing/distributing data with them. Rinse and repeat.

After years of this I became more interested in learning how to access & analyze data myself, beyond ABC. At the command line with open-source librairies, rather than in a UI on enterprise platforms.

That's how looking at Covid-19 data and compulsively reading Covid news articles somewhat naturally became my hobby since April 2020. It was a good distraction, oddly enough, while confined to a small Parisian apartment for 2.5 months. 

With the arrival of the second wave and accompanying media blitz of stats, alerts, and heatmaps, I realized it was leaving me overwhelmed. And if someone for whom data visualization is a fun weekend activity (sometimes) is overwhelmed, what about everyone else?

## Data sources

The Covid-19 data comes from Santé Publique France which updates daily at 19h15 Paris time. 

The plots here are updated shortly afterwards, usually by 21h Paris time.

* [Daily counts of positive tests & total tests](https://www.data.gouv.fr/fr/datasets/donnees-relatives-aux-resultats-des-tests-virologiques-covid-19/)
* [Daily totals Covid-19 hospitalizations & ICU occupancy](https://www.data.gouv.fr/en/datasets/donnees-hospitalieres-relatives-a-lepidemie-de-covid-19/)
* [Daily incidence rates for metropoles](https://www.data.gouv.fr/en/datasets/indicateurs-de-lactivite-epidemique-taux-dincidence-de-lepidemie-de-covid-19-par-metropole)

Other data sources:

* [INSEE population by dept](https://www.insee.fr/fr/statistiques/4265439?sommaire=4265511)
* [INSEE population by dept & age group](https://www.insee.fr/fr/statistiques/1893198)
* [ICU beds by department](https://drees.solidarites-sante.gouv.fr/etudes-et-statistiques/publications/article/nombre-de-lits-de-reanimation-de-soins-intensifs-et-de-soins-continus-en-france)
* [French departments geojson](https://static.data.gouv.fr/resources/carte-des-departements-2-1/20191202-212236/contour-des-departements.geojson)
* [lat & long coordinates for curfew metropoles](https://public.opendatasoft.com/explore/dataset/geoflar-communes-2013/download/?format=geojson&timezone=Europe/Berlin&lang=en) 
  * NB: This data now directly available on gouv.donnees.fr, will switch to this shortly.


When I started in April 2020, there wasn't as much data available—or at least findable—so I've done additional data processing to:

* create rolling 7-day sums for positive tests and total number of tests

* calculate incidence rates for entire population as well as incidence rates for the 70+ age group

* calculate percentage of ICU beds occupied by Covid patients

* classify each département according to the alert thresholds described above...to the best of my ability with publicly-available data. See 'Data Caveats' above.

Even though rolling 7-day averages and taux d'incidence are now available pre-calculated on data.gouv.fr, I prefer to keep working with daily "raw" numbers, especially as it allows me to see testing numbers (which I hope to share more here soon). 

* The exception is metropole incidence rate data, which for now are only available pre-calculated.

You can find my data processing scripts [here](https://github.com/limegimlet/covid19/tree/master).
