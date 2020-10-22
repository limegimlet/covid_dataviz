# About this site (under construction)

The data here is meant to help you understand how Covid-19 is evolving in different areas of France. My goal right now is to give you more context beyond increasingly-alarming case numbers announced for a certain date. Is that good or bad? Are we heading up or down?

To that end, in case you haven't already noticed, the plots here all interactive: you can zoom in on a area of a plot to get more detail, or isolate only a few lines on a plot by clicking the legend. 

Oh and mobile users: turn your phone **sideways**.

**Coming soon**

* **tracking the curfew areas** - where Covid is the most active - to see how if/when/how fast the case counts & ICU occupancy goes down. Curfew starts on Sat October 17 at 21h00. Progress will be slow—experts say it will take two weeks minimum according to exports to expect any changes—but being able to visualize progress is always motivating.

* **adding alert thresholds** to the indicator plots, which helps put the Covid curves in perspective.

* **creating a map of the metropoles under curfew**

## About Covid-19 data

To borrow a phrase from economists, there's no such thing as a perfect dataset. Covid-19 data is the embodiment of this. It's extremely hard to establish any certainties with a novel virus that spreads so easily, manifests with such varied symptoms and outcomes, and wreaks literal havoc across so much of the world.

In such a fast-evolving environment, data collection is not going to be exhaustive, nor ideal. The New York Times, Le Monde, The Guardian and the Canadian Broadcasting Company, just to name my go-to information sources as a layperson, have all reported stories of delayed results, not enough testing of asymptomatics, technical snafus, among other problems. 

This applies to all Covid-19 data, not just what is visualized here. 

Nonetheless, even if this data is not 100% accurate, it still provides decent benchmarks of where we are, and rough signposts of where we might be heading in near future. 

## Data caveats for the data here

These maps display Covid-19 indicator values. **The values are merely an approximation of the official government figures** used to determine if a threshold has been reached.

I cannot replicate government figures completely due to the following:

* a 3-day lag in testing numbers. Since incidence rates are based on testing data, the 'latest' `incid_tous` & `incid_70+` values here will always from at least 3 days earlier.


* _Personnes agées_ for the French government means people 65 or older. However, the publicly-available, daily testing data only breaks down age in 10-year increments. As a result the maps here show incidence rates for people 70 or older( `incid_70+`). In other words, they are understated compared to official government figures.


* The government examines overall incidence rates for the major metropolitan in France when classifiying its surrounding département. Until Oct 15 2020 there wasn't any data on these metropoles, so I've applied those thresholds to departments instead. This likely means the overall incidence rate in these maps (`incid_tous`) is also understated compared to official figures.

## Data sources

The Covid-19 data comes from Santé Publique France:

* [Daily counts of positive tests & total tests](https://www.data.gouv.fr/fr/datasets/donnees-relatives-aux-resultats-des-tests-virologiques-covid-19/)
* [Daily totals Covid-19 hospitalizations & ICU occupancy](https://www.data.gouv.fr/en/datasets/donnees-hospitalieres-relatives-a-lepidemie-de-covid-19/)

I then did additional data processing to:

* create rolling 7-day sums for positive tests and total number of tests

* calculate incidence rates for entire population as well as incidence rates for the 70+ age group

* calculate percentage of ICU beds occupied by Covid patients

* classify each département according to the alert thresholds described above...to the best of my ability with publicly-available data. See 'Data Caveats' above.

You can find these data processing scripts [here](https://github.com/limegimlet/covid19/tree/master).
