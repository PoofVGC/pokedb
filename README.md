[![MIT license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)

# Pokémon Sprites

This is a collection of sprites of Pokémon from the main game series, ranging from collectibles to box sprites. It includes both official and custom versions of sprites that may not be available in-game.

**Examples of sprites:**

<p align="center"><img align="center" src="resources/images/banner_gen8_2x.png" alt="Pokésprite Gen 8 examples banner" width="726"></p>

These sprites can be used as individual files, or accessed programmatically using the included sprite database files.

## Sprites and metadata

This project contains both Pokémon box sprites and item sprites. For Pokémon, both the old style sprites from *Pokémon Sun/Moon* (Gen 7) and the new style sprites from *Pokémon Sword/Shield* (Gen 8), including the DLC, are included. Item sprites are available with Gen 8 style white outlines and without.

| Directory | Example1 | Example2 | Size | Type | Description |
|:----------|:-------:|:-------:|:----------|:-----|:------------|
| `/pokemon‑gen7x` | ![/pokemon-gen7x/ example1](pokemon-gen7x/shiny/bulbasaur.png) | ![/pokemon-gen7x/ example](pokemon-gen7x/shiny/venusaur.png) | 68×56 | Pokémon | [Gen 7 Sprites](https://msikma.github.io/pokesprite/overview/dex-gen7.html), updated to Gen 8 size and contrast |
| `/pokemon‑gen8` | ![/pokemon-gen8/ example2](pokemon-gen8/shiny/bulbasaur.png) | ![/pokemon-gen8/ example](pokemon-gen8/shiny/venusaur.png) | 68×56 | Pokémon | [Gen 8 Sprites](https://msikma.github.io/pokesprite/overview/dex-gen8.html) (plus older Gen 7 sprites where needed) |
| `/pokemon‑gen9` | ![/pokemon-gen8-centered/ example2](pokemon-gen8-centered/shiny/bulbasaur.png) | ![/pokemon-gen8-centered/ example](pokemon-gen8-centered/shiny/venusaur.png) | 68×56 | Pokémon | [Gen 8 Sprites](https://msikma.github.io/pokesprite/overview/dex-gen8.html) (plus older Gen 7 sprites where needed) |
| `/items` | ![/items/ example](items/evo-item/thunder-stone.png) | | 32×32 | Items | [Gen 3–8 inventory items](https://msikma.github.io/pokesprite/overview/inventory.html) |
| `/misc` | ![/misc/ example](misc/body-style/wings-multiple-gen6.png) | Varies | Varies | Misc. | [Miscellaneous sprites](https://msikma.github.io/pokesprite/overview/misc.html) from multiple gens |


The original 40×30 Pokémon sprites from Gen 6–7 are kept for legacy purposes in the [`/icons`](icons/) directory.

### Inventory items list

Several files are available for processing the sprites for inventory items:

* [`/data/item-map.json`](data/item-map.json) – a 1:1 map of item IDs and sprite files, e.g. `"item_0017": "medicine/potion"`
* [`/data/item-unlinked.json`](data/item-unlinked.json) – all inventory sprites not linked to an item ID—these are mostly duplicates (e.g. the *Metal Coat* sprite is in both *"hold-item"* and *"evo-item"*, and so one goes unused) and legacy files
* [`/data/item-legacy.json`](data/item-legacy.json) – a list of old item sprites from previous gen games

See the [inventory overview page](https://msikma.github.io/pokesprite/overview/inventory.html) for a list of items.

### Miscellaneous sprites

For all other sprites that are neither Pokémon nor inventory items, see [`/data/misc.json`](data/misc.json). Notably, the [ribbons](misc/ribbon) can be found there. Each group of miscellaneous sprites has its own unique data format. See the [miscellaneous overview page](https://msikma.github.io/pokesprite/overview/misc.html) for all included images.

## Sprite Dimensions

Since Gen 8, Pokémon box sprites have become 68×56 (up from 40×30 in Gen 7) to accommodate larger sprite designs. 

<p align="center">
<img src="resources/images/readme_gen8_size_1.png" width="166">
&nbsp;&nbsp;&nbsp;
<img src="resources/images/readme_gen8_size_2.png" width="166">
<p>

Most Pokémon did not get a new sprite as of Gen 8, meaning their old sprite was padded to the new size. Sprites were padded from below.

Since most Pokémon take up a very small amount of pixels of the allotted space, they'll look far more spaced apart than in Gen 7 if they're displayed adjacent to each other. This effect is especially noticeable for not-fully-evolved Pokémon.

To somewhat mitigate this, the sprites can be made to overlap each other. In nearly all cases, only the empty space around the sprite will overlap—if there are multiple large sprites next to each other (like several Gigantamax forms) the sprites themselves will overlap, but only a little.

The recommended overlap is **-24px left** and **-16px top**, which is a compromise between bringing the smaller sprites closer together and not letting the larger sprites overlap. **Here's an example of what that looks like:**

<p align="center"><img align="center" src="resources/images/offset_example_2x.png" width="552" alt="Sprite offset example"></p>

With this setup, the larger sprites are quite close together but not uncomfortably so, and the smaller sprites are not too far away from each other. There is some small overlap for the largest sprites (the special Gigantamax forms), but not excessively so, and in most cases it should be rare to see multiple Gigantamax forms next to one another since it's not a permanent form.

For a better example of what many adjacent sprites look like with this setup, see the banner image at the top of the readme, which also uses the same amount of spacing.

## Related projects

**Projects using PokéSprite:**

* **[PokéSprite spritesheet](https://github.com/msikma/pokesprite-spritesheet/)** – spritesheet of all Pokémon box sprites and inventory items for use in websites
* **[PikaSprite](https://github.com/arcanis/pikasprite)** – a different interface for PokéSprite sprites
* [Spinda Painter](https://msikma.github.io/spinda-spots/) – proof of concept for displaying accurate Spinda spots on its box sprite

If your project uses PokéSprite and you'd like to be added to this list, feel free to [open an issue](https://github.com/msikma/pokesprite/issues) to request it.

**Pokémon artwork related links:**

* [Project Pokémon - Animated 3D sprites index](https://projectpokemon.org/docs/spriteindex_148/)
* [Bulbapedia - List of game sprites](https://archives.bulbagarden.net/wiki/Category:Game_sprites) – contains many other graphics and icons not included in this project
* [PokéDings](https://github.com/msikma/PokeDings) – webfont and SVG icons of special characters used in Pokémon nicknames
* [PokéResources](https://github.com/msikma/pokeresources) – Various Pokémon image resources

## License

The sprite images are © Nintendo/Creatures Inc./GAME FREAK Inc.

Everything else, and the programming code, is governed by the [MIT license](http://opensource.org/licenses/MIT).

See [the contributors file](contributors.md) for further information.
