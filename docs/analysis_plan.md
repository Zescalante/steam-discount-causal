
# Motivation and Analysis Outline

The motivation behind this analysis is a first foray into causal inference to familiarize myself with the concepts/tools in an applied capacity. Here, I'll describe the dataset used, and broadly describe the plan for analysis before having reduced any data. 

## The Data

Source of data: https://data.mendeley.com/datasets/ycy3sy3vj2/1

We have a time-series dataset of the player counts, pricing history, and other metadata of 2000 apps (mostly games) from Steam. The 2000 apps were chosen from those with highest player count within last 24 hours of 2017-12-11. Player count history is available for each app from (2017-12-14, 2020-08-12). Full attribute/metadata info available at the [source](https://data.mendeley.com/datasets/ycy3sy3vj2/1).


## Estimand, Treatment, Control Units

Question to answer: Do discounts raise engagement lastingly, or only transient (briefly)? I'll define lasting engagement as an increase in mean weekly(?) concurrent players after one month. 

What method will I use? A DiD analysis? Need to research how this is carried out in my context.

Estimand (metric that I'll use to make judgments): The average effect of a discount on treated games, by days (no need to be as granular as minutes or hours) since the discount began.

Unit: Game i on day t. 
Outcome (Y): Log concurrent players (peak? or mean?)

For the treatment (D), I'll choose any discount depth (>0%) as a minimum treatment, a no-discount window beforehand of a month(?). Whether I'll study first discounts only, or repeated ones (undecided?). 

What about the control group? Not-yet-treated (not yet discounted) games, never-treated (never discounted) games, or matched games? 

## Factors to Consider

Since seasonal (steam) sales affect many games, I'll focus on off-sale discounts. 

Since anticipation of broad sales may factor, I'll need to be aware of this for pre-trends (how will I do this?)

This dataset is likely affected by the COVID surge. How to handle this? 

Spillover interference likely: one game being discounted likely affects outcome of another game. Violates no-interference assumption.

Similarly, competing releases: games release on the same day could impact player numbers. Need to check if newly released games are included in the data, and how to handle.

Possible heterogeneous effects: outcomes might differ by genre, discount depth, game age, etc.

Selection bias: We consider only the top-played games. 

Should I completely exclude free to play games? Or can I utilize these in the analysis? Some kind of untreated proxy control?
