# Confinement: where is it having the greatest impact?

* The heatmaps below show **daily _percentage_ change since Oct 28 2020** for `incid_tous`, `incid_70+`, and `rea%_dep` in the 96 mainland France departments.

* **Departments appear in descending order**: the department with the greatest decrease or increase since confinement began is the first listed.

* To make sure changes in incidence rate aren't simply due to changes in testing volume, the % change in incidence rate shown here is the **net change**,  after subtracting % change in testing rate.  

* Note the color scale to the right of each heatmap: it varies for each.

* Also, note that the scale for decreases is far more modest for `rea%` than for increases. **In other words, we've still got a ways to go**.

## Incidence rate % decreases

A growing number of departments show decreasing `incid_tous` rates.

However, even if it's decreasing, in absolute numbers it's still high: there's still a very high number of new infections out there.

Since inevitably a certain proportion of those infected now will end up in ICU ~7 days from now, it still means stress for hospitals for the foreseeable future.

{% raw %}<iframe width="100%" height="1900" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/203.embed?showlink=false"></iframe>{% endraw %}

## Incidence rate % increases

You definitely get a sense that increases are really levelling off: the biggest post-confinement increase on Nov 15 was 12%.

{% raw %}<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/205.embed?showlink=false"></iframe>{% endraw %}

## Elderly incidence rate % decreases

Compared to the overall incidence rate, there are fewer departments with decreases in `incid_70+`. However, the size of the decreases, at least for the top few departments, is somewhat larger.

I suspect this is because many elderly Covid cases are from EHPAD (old age home) clusters. As with any type of cluster, it prompts intensive testing - and from the hover info you can see that the test rate had indeed increased for the first 7 departments on Nov 15.  

Intenstive testing quickly uncovers more cases, hence rapid spikes in `incid_70+` on the way up, and steeper plunges once the cluster shrinks. All this translates into bigger % changes.

{% raw %}<iframe width="100%" height="1500" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/207.embed?showlink=false"></iframe>{% endraw %}

## Elderly incidence rate % increases

The cluster effect that I described in the decreases section seems even more pertinent here.

In the past 2.5 weeks you can see from the color changes along the rows that there have been rapid changes in both directions. In some cases a department goes from pale blue to deep red over a few days.

Compared to increases in `incid_tous`, there are not just more departments with `incid_70+` that is still increasing more than 2 weeks into confinement, the increase rate is bigger - see the range of the scale at right.

{% raw %}<iframe width="100%" height="800" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/209.embed?showlink=false"></iframe>{% endraw %}


## ICU saturation % decreases

These are modest, and seem to be all rural. It's likely they have few ICU beds so the arrival or departure of one or two patients can have a big % impact.

{% raw %}<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/211.embed?showlink=false"></iframe>{% endraw %}

## ICU saturation % increases

The first row is something of an outlier, with such a giant increase that the still-large increases elsewhere literally pale in comparison.

Also, Deux-Sèvres is the department with the 2nd-lowest number of ICU beds per 100k population: 2.08. For comparison, the highest numbers (in Territoire du Belfort & Paris) are above 17 beds per 100k population.

{% raw %}<iframe width="100%" height="2000" frameborder="0" scrolling="no" src="//plotly.com/~limegimlet/213.embed?showlink=false"></iframe>{% endraw %}
