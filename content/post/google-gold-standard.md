---
date: "2021-08-10"
tags: ["recommendations"]
title: "Recommendation Gold Standard - Google Infoboxes"
---

## Introdution

In this blog post, we want to present a gold standard for evaluating top-N ranked recommendation lists for Pokémons. This gold standard was extracted from infoboxes shown by the Google search engine for each particular Pokémon. As of now, infoboxes weren't shown for most Pokémons of the newer generations of VII and VIII.

## Methodology

The Google search engine (available at [google.com](https://google.com)) was used to search for the English label of each Pokémon (e.g. `"Pikachu"`). This can lead to the following four outcomes:

1) An infobox is shown for the Pokémon displaying some basic information, and at the bottom a number of other entities including other Pokémon are recommended. Optionally, it is possible to click on the `"View x more"` to see more recommendations.

2) An infobox is shown for the Pokémon displaying some basic information, but no recommendations at the bottom.

3) The label of the Pokémon is ambigiuos to Google, i.e. it is referring to multiple entities for which the search engine would be able to show an infobox. In this case, a selection field is presented to the user in which they can select their preference.
    * a) the Pokémon is not among those detected entities.
    * b) the Pokémon is among those detected entities. Selecting this option, can lead to outcome (1) or (2).

4) No infobox is available for the search term.

![Google Search Outcomes](https://pokemonkg.org/images/post/pokemon-gold-standard-google-infoboxes-outcomes.png)

We try to exract recommended Pokémon from infoboxes, and in case of (2), (3a), and (4) we fail. If we fail after searching for the label, the same procedure is repeated by searching for the English label of the Pokémon plus the word `"pokemon"` (e.g. `"Pikachu pokemon"`). Should this attempt fail as well, then we try to find the Pokémon in the recommendation list of another Pokémon. If all those attempts fail, then we have found no recommendations for this particular Pokémon.

Should we have been successful for a Pokémon, then a closer look is taken at the recommended enities in the infobox. Those entities must not necessarily be other Pokémon, while it is rare to find one thats not. The label of the entities is strictly matched to a set of labels of all known Pokémon, which works surprisingly well. Hence, we easily get a list of recommended Pokémon simply skipping all non-Pokémon entities.

Finally, the browsing experience was setup such that (A) fresh browser instance is used for each search, (B) all cookies were disabled, and (C) a VPN into the United Kingdom was used.


The source code of the Python application can be found [here]().

## Result


### Generation I



### Generation I-II

### Generation I-VI