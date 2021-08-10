---
date: "2021-07-20"
tags: ["rdf2vec", "ldsd", "recommendations"]
title: "Applying Knowledge Graph Embeddings"
---


| Software                                                      | Dataset      | Depth of Walks| Max. Walks per Entity | Reverse Traversal | Random Seed |
| ------------------------------------------------------------- | ------------ | ------------- | --------------------- | ----------------- | ----------- |
| [pyrdf2vec](https://github.com/IBCNServices/pyRDF2Vec) v0.2.3 | [poke-a.nq.gz](/download/dump/poke-a.nq.gz) | 12            | 250                   | False             | 122         |

## t-SNE Visualization

{{< rawhtml >}}
		<table>
		<tbody>
			<tr>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<img src="https://pokemonkg.org/images/star.svg" style="width: 25px; height>:25px;"/>
								</td>
								<td style="border: none;">
									Pikachu
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<img src="https://pokemonkg.org/images/plus.svg" style="width: 25px; height>:25px;"/>
								</td>
								<td style="border: none;">
									Squirtle
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<img src="https://pokemonkg.org/images/square.svg" style="width: 25px; height>:25px;"/>
								</td>
								<td style="border: none;">
									Sunkern
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<img src="https://pokemonkg.org/images/thin-diamond.svg" style="width: 25px; height>:25px;"/>
								</td>
								<td style="border: none;">
									Fletchling
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
		</tbody>
	</table>
	<div style="text-decoration: none;">
		<a href="https://pokemonkg.org/images/post/kge-parti/t_sne.png">
			<img src="https://pokemonkg.org/images/post/kge-parti/t_sne.png" style="width: 100%; object-fit: contain;"/>
		</a>
	</div>
	<table>
		<tbody>
			<tr>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #ff0000;"></div>
								</td>
								<td style="border: none;">
									Pokémon Species
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #800080;"></div>
								</td>
								<td style="border: none;">
									Moves
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #0000ff;"></div>
								</td>
								<td style="border: none;">
									Ability
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
			<tr>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #008000;"></div>
								</td>
								<td style="border: none;">
									Berry
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #ff1493;"></div>
								</td>
								<td style="border: none;">
									Place
								</td>
							</tr>
						</tbody>
					</table>
				</td>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #ff8c00;"></div>
								</td>
								<td style="border: none;">
									Pokédex Entries
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
			<tr>
				<td style="border: none;">
					<table>
						<tbody>
							<tr>
								<td style="border: none; display: flex; justify-content: flex-end;">
									<div style="width: 25px; height: 25px; background: #bfbf00;"></div>
								</td>
								<td style="border: none;">
									Games / Generations
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
		</tbody>
	</table>
{{< /rawhtml >}}

## Recommendations
![Linked Data Semantic Distance (CW) Boxplot](https://pokemonkg.org/images/post/kge-parti/rdf2vec_boxplot.png)
![Linked Data Semantic Distance (CW) Boxplot](https://pokemonkg.org/images/post/kge-parti/ldsd_cw_boxplot.png)

### Pikachu

![Pikachu](https://img.pokemondb.net/sprites/bank/normal/pikachu.png)

**Most related Pokémons (top 5):**

| Google (Collaborative filtering)                                                                                                                                             | Linked Data Semantic Distance (CW)                                                                    | rdf2vec/cosine distance    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| **1.** ![Raichu](https://img.pokemondb.net/sprites/bank/normal/raichu.png) [Raichu](https://bulbapedia.bulbagarden.net/wiki/Raichu_(Pok%C3%A9mon))                           | **1.** ![Pichu](https://img.pokemondb.net/sprites/bank/normal/pichu.png) [Pichu](https://bulbapedia.bulbagarden.net/wiki/Pichu_(Pok%C3%A9mon))                   | **1.** ![Cacturne](https://img.pokemondb.net/sprites/bank/normal/cacturne.png) [Cacturne](https://bulbapedia.bulbagarden.net/wiki/Cacturne_(Pok%C3%A9mon))        |
| **2.** ![Pichu](https://img.pokemondb.net/sprites/bank/normal/pichu.png) [Pichu](https://bulbapedia.bulbagarden.net/wiki/Pichu_(Pok%C3%A9mon))                               | **2.** ![Raichu](https://img.pokemondb.net/sprites/bank/normal/raichu.png) [Raichu](https://bulbapedia.bulbagarden.net/wiki/Raichu_(Pok%C3%A9mon))          | **2.** ![Bayleef](https://img.pokemondb.net/sprites/bank/normal/bayleef.png) [Bayleef](https://bulbapedia.bulbagarden.net/wiki/Bayleef_(Pok%C3%A9mon))           |
| **3.** ![Charizard](https://img.pokemondb.net/sprites/bank/normal/charizard.png) [Charizard](https://bulbapedia.bulbagarden.net/wiki/Charizard_(Pok%C3%A9mon))               | **3.** ![Manectric](https://img.pokemondb.net/sprites/bank/normal/manectric.png) [Manectric](https://bulbapedia.bulbagarden.net/wiki/Manectric_(Pok%C3%A9mon))    | **3.** ![Togekiss](https://img.pokemondb.net/sprites/bank/normal/togekiss.png) [Togekiss](https://bulbapedia.bulbagarden.net/wiki/Togekiss_(Pok%C3%A9mon))        |
| **4.** ![Charmander](https://img.pokemondb.net/sprites/bank/normal/charmander.png) [Charmander](https://bulbapedia.bulbagarden.net/wiki/Charmander_(Pok%C3%A9mon))           | **4.** ![Plusle](https://img.pokemondb.net/sprites/bank/normal/plusle.png) [Plusle](https://bulbapedia.bulbagarden.net/wiki/Plusle_(Pok%C3%A9mon))                  | **4.** ![Electabuzz](https://img.pokemondb.net/sprites/bank/normal/electabuzz.png) [Electabuzz](https://bulbapedia.bulbagarden.net/wiki/Electabuzz_(Pok%C3%A9mon))  |
| **5.** ![Eevee](https://img.pokemondb.net/sprites/bank/normal/eevee.png)  [Eevee](https://bulbapedia.bulbagarden.net/wiki/Eevee_(Pok%C3%A9mon))                              | **5.** ![Ampharos](https://img.pokemondb.net/sprites/bank/normal/ampharos.png) [Ampharos](https://bulbapedia.bulbagarden.net/wiki/Ampharos_(Pok%C3%A9mon))     | **5.** ![Ninetales](https://img.pokemondb.net/sprites/bank/normal/ninetales.png) [Ninetales](https://bulbapedia.bulbagarden.net/wiki/Ninetales_(Pok%C3%A9mon))     |

### Squirtle

![Squirtle](https://img.pokemondb.net/sprites/bank/normal/squirtle.png)

**Most related Pokémons (top 5):**

| Google (Collaborative filtering)                                                                                                                                             | Linked Data Semantic Distance (CW) |    rdf2vec/cosine distance    |
|  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- | -------------------------------- |
| **1.** ![Bulbasaur](https://img.pokemondb.net/sprites/bank/normal/bulbasaur.png) [Bulbasaur](https://bulbapedia.bulbagarden.net/wiki/Bulbasaur_(Pok%C3%A9mon))               | **1.** ![Wartortle](https://img.pokemondb.net/sprites/bank/normal/wartortle.png) [Wartortle](https://bulbapedia.bulbagarden.net/wiki/Wartortle_(Pok%C3%A9mon))    | **1.** ![Greninja](https://img.pokemondb.net/sprites/bank/normal/greninja.png) [Greninja](https://bulbapedia.bulbagarden.net/wiki/Greninja_(Pok%C3%A9mon))       |
| **2.** ![Charmander](https://img.pokemondb.net/sprites/bank/normal/charmander.png) [Charmander](https://bulbapedia.bulbagarden.net/wiki/Charmander_(Pok%C3%A9mon))           | **1.** ![Blastoise](https://img.pokemondb.net/sprites/bank/normal/blastoise.png) [Blastoise](https://bulbapedia.bulbagarden.net/wiki/Blastoise_(Pok%C3%A9mon))    | **2.** ![Medicham](https://img.pokemondb.net/sprites/bank/normal/medicham.png) [Medicham](https://bulbapedia.bulbagarden.net/wiki/Medicham_(Pok%C3%A9mon))       |
| **3.** ![Wartortle](https://img.pokemondb.net/sprites/bank/normal/wartortle.png) [Wartortle](https://bulbapedia.bulbagarden.net/wiki/Wartortle_(Pok%C3%A9mon))               | **3.** ![Totodile](https://img.pokemondb.net/sprites/bank/normal/totodile.png) [Totodile](https://bulbapedia.bulbagarden.net/wiki/Totodile_(Pok%C3%A9mon))      | **3.** ![Tropius](https://img.pokemondb.net/sprites/bank/normal/tropius.png) [Tropius](https://bulbapedia.bulbagarden.net/wiki/Tropius_(Pok%C3%A9mon))          |
| **4.** ![Blastoise](https://img.pokemondb.net/sprites/bank/normal/blastoise.png) [Blastoise](https://bulbapedia.bulbagarden.net/wiki/Blastoise_(Pok%C3%A9mon))               | **3.** ![Swampert](https://img.pokemondb.net/sprites/bank/normal/swampert.png) [Swampert](https://bulbapedia.bulbagarden.net/wiki/Swampert_(Pok%C3%A9mon))      | **4.** ![Silvally](https://img.pokemondb.net/sprites/bank/normal/silvally.png) [Silvally](https://bulbapedia.bulbagarden.net/wiki/Silvally_(Pok%C3%A9mon))       |
| **5.** ![Pikachu](https://img.pokemondb.net/sprites/bank/normal/pikachu.png) [Pikachu](https://bulbapedia.bulbagarden.net/wiki/Pikachu_(Pok%C3%A9mon))                       | **3.** ![Marshtomp](https://img.pokemondb.net/sprites/bank/normal/marshtomp.png) [Marshtomp](https://bulbapedia.bulbagarden.net/wiki/Marshtomp_(Pok%C3%A9mon))    | **5.** ![Zubat](https://img.pokemondb.net/sprites/bank/normal/zubat.png) [Zubat](https://bulbapedia.bulbagarden.net/wiki/Zubat_(Pok%C3%A9mon))                        |


### Sunkern

![Sunkern](https://img.pokemondb.net/sprites/bank/normal/sunkern.png)

**Most related Pokémons (top 5):**

| Google (Collaborative filtering)                                                                                                                                           | Linked Data Semantic Distance (CW) |    rdf2vec/cosine distance    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- | -------------------------------- |
| **1.** ![Sunflora](https://img.pokemondb.net/sprites/bank/normal/sunflora.png) [Sunflora](https://bulbapedia.bulbagarden.net/wiki/Sunflora_(Pok%C3%A9mon))                 | **1.** ![Sunflora](https://img.pokemondb.net/sprites/bank/normal/sunflora.png) [Sunflora](https://bulbapedia.bulbagarden.net/wiki/Sunflora_(Pok%C3%A9mon))             | **1.** ![Abomasnow](https://img.pokemondb.net/sprites/bank/normal/abomasnow.png) [Abomasnow](https://bulbapedia.bulbagarden.net/wiki/Abomasnow_(Pok%C3%A9mon))     |
| **2.** ![Gloom](https://img.pokemondb.net/sprites/bank/normal/gloom.png) [Gloom](https://bulbapedia.bulbagarden.net/wiki/Gloom_(Pok%C3%A9mon))                             | **2.** ![Oddish](https://img.pokemondb.net/sprites/bank/normal/oddish.png) [Oddish](https://bulbapedia.bulbagarden.net/wiki/Oddish_(Pok%C3%A9mon))        | **2.** ![Skiddo](https://img.pokemondb.net/sprites/bank/normal/skiddo.png) [Skiddo](https://bulbapedia.bulbagarden.net/wiki/Skiddo_(Pok%C3%A9mon))                      |
| **3.** ![Hoppip](https://img.pokemondb.net/sprites/bank/normal/hoppip.png) [Hoppip](https://bulbapedia.bulbagarden.net/wiki/Hoppip_(Pok%C3%A9mon))                         | **2.** ![Gloom](https://img.pokemondb.net/sprites/bank/normal/gloom.png) [Gloom](https://bulbapedia.bulbagarden.net/wiki/Gloom_(Pok%C3%A9mon))                 | **3.** ![Machoke](https://img.pokemondb.net/sprites/bank/normal/machoke.png) [Machoke](https://bulbapedia.bulbagarden.net/wiki/Machoke_(Pok%C3%A9mon))                   | 
| **4.** ![Bellossom](https://img.pokemondb.net/sprites/bank/normal/bellossom.png) [Bellossom](https://bulbapedia.bulbagarden.net/wiki/Bellossom_(Pok%C3%A9mon))             | **2.** ![Hoppip](https://img.pokemondb.net/sprites/bank/normal/hoppip.png) [Hoppip](https://bulbapedia.bulbagarden.net/wiki/Hoppip_(Pok%C3%A9mon))                | **4.** ![Pancham](https://img.pokemondb.net/sprites/bank/normal/pancham.png) [Pancham](https://bulbapedia.bulbagarden.net/wiki/Pancham_(Pok%C3%A9mon))                   |
| **5.** ![Oddish](https://img.pokemondb.net/sprites/bank/normal/oddish.png) [Oddish](https://bulbapedia.bulbagarden.net/wiki/Oddish_(Pok%C3%A9mon))                         | **2.** ![Skiploom](https://img.pokemondb.net/sprites/bank/normal/skiploom.png) [Skiploom](https://bulbapedia.bulbagarden.net/wiki/Skiploom_(Pok%C3%A9mon))    | **5.** ![Gogoat](https://img.pokemondb.net/sprites/bank/normal/gogoat.png) [Gogoat](https://bulbapedia.bulbagarden.net/wiki/Gogoat_(Pok%C3%A9mon))                      |

### Fletchling

![Fletchling](https://img.pokemondb.net/sprites/bank/normal/fletchling.png)

**Most related Pokémons (top 5):**

| Google (Collaborative filtering)                                                                                                                                           | Linked Data Semantic Distance (CW)                                                                     |    rdf2vec/cosine distance    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | -------------------------------- |
| **1.** ![Fletchinder](https://img.pokemondb.net/sprites/bank/normal/fletchinder.png) [Fletchinder](https://bulbapedia.bulbagarden.net/wiki/Fletchinder_(Pok%C3%A9mon))            | **1.** ![Fletchinder](https://img.pokemondb.net/sprites/bank/normal/fletchinder.png) [Fletchinder](https://bulbapedia.bulbagarden.net/wiki/Fletchinder_(Pok%C3%A9mon))      | **1.** ![Corvisquire](https://img.pokemondb.net/sprites/home/normal/corvisquire.png) [Corvisquire](https://bulbapedia.bulbagarden.net/wiki/Corvisquire_(Pok%C3%A9mon))                                                                                         |
| **2.** ![Talonflame](https://img.pokemondb.net/sprites/bank/normal/talonflame.png) [Talonflame](https://bulbapedia.bulbagarden.net/wiki/Talonflame_(Pok%C3%A9mon))         | **1.** ![Talonflame](https://img.pokemondb.net/sprites/bank/normal/talonflame.png) [Talonflame](https://bulbapedia.bulbagarden.net/wiki/Talonflame_(Pok%C3%A9mon)) | **2.** ![Electivire](https://img.pokemondb.net/sprites/bank/normal/electivire.png) [Electivire](https://bulbapedia.bulbagarden.net/wiki/Electivire_(Pok%C3%A9mon)) |
| **3.** ![Froakie](https://img.pokemondb.net/sprites/bank/normal/froakie.png) [Froakie](https://bulbapedia.bulbagarden.net/wiki/Froakie_(Pok%C3%A9mon))                     | **2.** ![Swanna](https://img.pokemondb.net/sprites/bank/normal/swanna.png) [Swanna](https://bulbapedia.bulbagarden.net/wiki/Swanna_(Pok%C3%A9mon))                 | **3.** ![Chatot](https://img.pokemondb.net/sprites/bank/normal/chatot.png) [Chatot](https://bulbapedia.bulbagarden.net/wiki/Chatot_(Pok%C3%A9mon)) |
| **4.** ![Litleo](https://img.pokemondb.net/sprites/bank/normal/litleo.png) [Litleo](https://bulbapedia.bulbagarden.net/wiki/Litleo_(Pok%C3%A9mon))                         | **2.** ![Mandibuzz](https://img.pokemondb.net/sprites/bank/normal/mandibuzz.png) [Mandibuzz](https://bulbapedia.bulbagarden.net/wiki/Mandibuzz_(Pok%C3%A9mon))   | **4.** ![Rookidee](https://img.pokemondb.net/sprites/home/normal/rookidee.png) [Rookidee](https://bulbapedia.bulbagarden.net/wiki/Rookidee_(Pok%C3%A9mon)) |
| **5.** ![Bunnelby](https://img.pokemondb.net/sprites/bank/normal/bunnelby.png) [Bunnelby](https://bulbapedia.bulbagarden.net/wiki/Bunnelby_(Pok%C3%A9mon))                 | **2.** ![Pidove](https://img.pokemondb.net/sprites/bank/normal/pidove.png) [Pidove](https://bulbapedia.bulbagarden.net/wiki/Pidove_(Pok%C3%A9mon))                 | **5.** ![Natu](https://img.pokemondb.net/sprites/bank/normal/natu.png) [Natu](https://bulbapedia.bulbagarden.net/wiki/Natu_(Pok%C3%A9mon)) |