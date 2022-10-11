---
date: "2022-10-01"
tags: ["rdf2vec", "ldsd", "transe", "recommendations"]
title: "KG-based Recommendations"
---
Recommender systems have become particularly popular with the rise of the Web 
and e-commerce. These systems aim to reduce the information overload for users
by filtering out content based on predictions of user preferences. Over the
years, several techniques have evolved for recommender systems. Nonetheless,
collaborative and content-based filtering are the most dominant techniques.

In this blog post, KG-based recommendation approaches are investigated on the
Pokémon KG ([version a](/download/dump/poke-a.nq.gz)).


## Software Setup

|                         Name                           |      Version      |   Model   |
| ------------------------------------------------------ | ----------------- | --------- |
| [kgrec](https://github.com/khaller93/kgrec)            | nightly #da1c26d  | LDSD      |
| [pykeen](https://github.com/pykeen/pykeen)             | 1.9.0             | TransE    |
| [pyRDF2Vec](https://github.com/IBCNServices/pyRDF2Vec) | nightly #266f234  | RDF2Vec   |


## Hyperparameters

Some of the models have hyperparameters that influence their performance and are
required for better reproducibility. 

### Linked Data Semantic Distance (LDSD)

This model has no hyperparameters.

### RDF2Vec

| Depth of Walks | Max Walks per Entity | Reverse Traversal | Skip Type   | Random Seed |
| -------------- | -------------------- | ----------------- | ----------- | ----------- |
| 4              | 200                  | False             | True        | 133         |

### TransE

| Dimensions     | Batch Size | Epoch       | Neg. Samples per Pos. | Random Seed |
| -------------- | ---------- | ----------- | --------------------- | ----------- |
| 208            | 512         | 900        | 12                    | 133         |

| Scoring Function | Loss Margin        | Optimizer LR          |
| ---------------- | ------------------ | --------------------- |
| 1                | 2.770675835864849  | 0.001044990551285324  |

## Evaluation

A brief evaluation of the models were performed for the first generation of 
Pokémons, which were in total 151 monsters. No dataset was available for an
utility/relevance ranking of these Pokémons, which is why we used the scrapped
infobox recommendations from Google instead (see [post](Google)
and [dataset](/recommendation-baseline/google-infobox/2021-08/generation-i.csv)).
However, an expert evaluation of relevance would lead to a more sophisticated
evaluation.

P@N (i.e. precision at N) was computed for all the models.

![P@9 Boxplot](/assets/content/post/kgrec-embeddings-i/p@9-boxplot.png)

## Recommendation - Inspection

In the recommendations, we focused on the 151 Pokémons in the first generation.

**Jigglypuff**

![Jigglypuff](https://img.pokemondb.net/sprites/sun-moon/normal/jigglypuff.png)

| Google (CF)                                                                                       |                               RDF2Vec                                                       | TransE  | LDSD |
|  ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- | ------- | ---- |
| **1.** Wigglytuff ![Wigglytuff](https://img.pokemondb.net/sprites/sun-moon/normal/wigglytuff.png) | **1.** Lickitung ![Lickitung](https://img.pokemondb.net/sprites/x-y/normal/lickitung.png)   | **1.** Wigglytuff ![Wigglytuff](https://img.pokemondb.net/sprites/sun-moon/normal/wigglytuff.png) | |
| **2.** Snorlax ![Snorlax](https://img.pokemondb.net/sprites/sun-moon/normal/snorlax.png)          | **2.** Kadabra ![Kadabra](https://img.pokemondb.net/sprites/sun-moon/normal/kadabra.png)    | **2.** Clefairy ![Clefairy](https://img.pokemondb.net/sprites/sun-moon/normal/clefairy.png)          | |
| **3.** Squirtle ![Squirtle](https://img.pokemondb.net/sprites/x-y/normal/squirtle.png)            | **3.** Lapras ![Lapras](https://img.pokemondb.net/sprites/sun-moon/normal/lapras.png)       | **3.** Clefable ![Clefable](https://img.pokemondb.net/sprites/sun-moon/normal/clefable.png)          | |
| **4.** Pikachu ![Pikachu](https://img.pokemondb.net/sprites/sun-moon/normal/pikachu.png)          | **4.** Rapidash ![Rapidash](https://img.pokemondb.net/sprites/x-y/normal/rapidash.png)      | **4.** Snorlax ![Snorlax](https://img.pokemondb.net/sprites/sun-moon/normal/snorlax.png)    | |
| **5.** Charmander ![Charmander](https://img.pokemondb.net/sprites/x-y/normal/charmander.png)      | **5.** Poliwag ![Jynx](https://img.pokemondb.net/sprites/sun-moon/normal/poliwag.png)       | **5.** Lickitung ![Lickitung](https://img.pokemondb.net/sprites/x-y/normal/lickitung.png)         | |
| **6.** Evee ![Evee](https://img.pokemondb.net/sprites/x-y/normal/eevee.png)                       | **6.** Muk ![Muk](https://img.pokemondb.net/sprites/sun-moon/normal/muk.png)                | **6.** Chansey ![Chansey](https://img.pokemondb.net/sprites/sun-moon/normal/chansey.png)           | |
| **7.** Bulbasaur ![bulbasaur](https://img.pokemondb.net/sprites/x-y/normal/bulbasaur.png)         | **7.** Jynx ![Jynx](https://img.pokemondb.net/sprites/x-y/normal/jynx.png)                  | **7.** Jynx ![Jynx](https://img.pokemondb.net/sprites/x-y/normal/jynx.png)                   | |
| **8.** Psyduck ![Psyduck](https://img.pokemondb.net/sprites/sun-moon/normal/psyduck.png)          | **8.** Hypno ![Hypno](https://img.pokemondb.net/sprites/sun-moon/normal/hypno.png)          | **8.** Hypno ![Hypno](https://img.pokemondb.net/sprites/sun-moon/normal/hypno.png)                   | |
| **9.** Charizard ![Charmander](https://img.pokemondb.net/sprites/x-y/normal/charizard.png)        | **9.** Geodude ![Geodude](https://img.pokemondb.net/sprites/sun-moon/normal/geodude.png)    | **9.** Poliqhirl ![Poliqhirl](https://img.pokemondb.net/sprites/sun-moon/normal/poliwhirl.png)                   | |