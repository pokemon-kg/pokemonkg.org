---
date: "2022-10-09"
tags: ["rdf2vec", "ldsd", "transe", "recommendations"]
title: "Contextual KG-based Recommendations"
---

## Scenario
Ash wants to go to the Pokémon Tower in Lavender Town in the Kanto region, but
wants to research first what he might be facing in this tower to think about 
strategies: 

* What of his Pokémon monster should he carry with himself? 
* Are there any rare Pokémons to catch? 
* Are there any moves that should be learned or improved by Pokémons?

After some minutes of searching, the following contextual knowledge graph was
built.

![Context](/assets/content/post/pkgrec/context.png)

## Metrics

### Naiv

## Introspection

### TransE Cosine

| Naiv                         |    |
| ---------------------------- | -- |
| **1.** Haunter (Pokémon) ![Haunter](https://img.pokemondb.net/sprites/sun-moon/normal/haunter.png)    ||
| **2.** Dream Eater (Move) ![Dream Eater](https://archives.bulbagarden.net/media/upload/5/59/Harrison_Hypno_Dream_Eater_effect.png)   ||
| **3.** Gengar (Pokémon) ![Gengar](https://img.pokemondb.net/sprites/sun-moon/normal/gengar.png)     ||
| **4.** Night-Shade (Move) ![Night-Shade](https://archives.bulbagarden.net/media/upload/thumb/9/99/Ash_Gengar_Night_Shade.png/800px-Ash_Gengar_Night_Shade.png)    ||
| **5.** Shadow-Ball (Move) ![Shadow-Ball](https://archives.bulbagarden.net/media/upload/thumb/6/60/Ursula_Flareon_Shadow_Ball.png/800px-Ursula_Flareon_Shadow_Ball.png)    ||
| **6.** Power-Gem (Move) ![Power-Gem](https://archives.bulbagarden.net/media/upload/thumb/5/5e/Giovanni_Persian_Power_Gem.png/800px-Giovanni_Persian_Power_Gem.png)     ||
| **7.** Polteageist (Pokémon) ![Polteageist](https://archives.bulbagarden.net/media/upload/b/b9/855Polteageist_WF.png)  ||
| **8.** Destiny-Bond (Move) ![Destiny-Bond](https://archives.bulbagarden.net/media/upload/6/69/Katie_Misdreavus_Destiny_Bond_effect.png)   ||
| **9.** Phantom-Force (Move) ![Phantom-Force](https://archives.bulbagarden.net/media/upload/thumb/c/cd/Diantha_Gourgeist_Phantom_Force.png/800px-Diantha_Gourgeist_Phantom_Force.png) ||
| **10.** Lick (Move) ![Lick](https://archives.bulbagarden.net/media/upload/5/53/Morty_Gengar_Lick.png) ||