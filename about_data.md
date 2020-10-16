# About the data

The data here is meant to help you understand how Covid-19 is evolving in different areas of France. The goal is to give you more context beyond a increasingly-alarming case numbers announced for a certain date.

Right now you can interact with these plots to zoom in on a timeframe, an indicator, or a deparment - whatever interests you. Hover over a point to see the underlying values.

**Coming soon**

* **tracking the curfew areas** - where Covid is the most active - to see how if/when/how fast the case counts & ICU occupancy goes down. Curfew starts on Sat October 17 at 21h00. Progress will be slow: it will take two weeks minimum according to exports to expect any changes, but being able to visualize progress is always motivating.

* **adding alert thresholds** to the indicator plots, which helps put the Covid curves in perspective.

## Data caveats - please read!

These maps display Covid-19 indicator values. **The values are merely an approximation of the official government figures** used to determine if a threshold has been reached.

I cannot replicate government figures completely due to the following:

* a 3-day lag in testing numbers. Since incidence rates are based on testing data, the 'latest' `incid_tous` & `incid_70+` values here will always from at least 3 days earlier.


* _Personnes agées_ for the French government means people 65 or older. However, the publicly-available, daily testing data only breaks down age in 10-year increments. As a result the maps here show incidence rates for people 70 or older( `incid_70+`). In other words, they are understated compared to official government figures.


* The government examines overall incidence rates for the major metropolitan in France when classifiying a département. These are Paris, Rennes, Bordeaux, Toulouse, Montpellier, Marseilles, Lyon, Grenoble and Lille. However publicly-available testing data is by département, not commune. Paris is the only city with its own département. This likely means the overall incidence rate in these maps (`incid_tous`) is also understated.

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
