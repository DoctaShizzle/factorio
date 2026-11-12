# Project Prometheus Product and Scope Taxonomy

*Status: Approved for the product-tree work*
*Last updated: 2026-11-12*

## Product-Tree Layers

The canonical design trace is:

**mineral feeds -> pure/refined materials -> manufactured products -> usable or constructable outputs and research ingredients**

An item can appear at multiple points in the trace or serve multiple roles. Give each catalog entry one primary class and use tags for secondary roles.

| Term | Definition |
|---|---|
| **Mineral feed** | A mined or otherwise extracted raw input entering the production tree. It may be a mineral, rock, or commodity resource. |
| **Pure/refined material** | A separated or purified material produced from a mineral feed or other raw input and used as a downstream input. |
| **Manufactured product / intermediate** | A chemical, alloy, component, or assembly produced by processing other inputs. It is not necessarily directly usable by the player. |
| **Usable output** | A product used directly by the player or factory, including fuel, ammunition, weapons, armor equipment, utilities, and modules. |
| **Constructable** | A player-built or player-equipped endpoint, such as a placeable building, vehicle, weapon, armor equipment, utility, or module. A constructable is a product role, not a synonym for all products. |
| **Research ingredient** | An item consumed by a research process. It may also be a usable output or manufactured product; record the research role as a tag. |

## Distinct Things to Count

| Term | Counting rule |
|---|---|
| **Product** | A distinct inventory/resource item or other explicitly modeled production output. Count once by stable catalog ID, regardless of how many recipes produce it or roles it serves. |
| **Recipe** | One defined transformation with its inputs, outputs, process, and prerequisites. A recipe with coproducts is still one recipe; each distinct output is a product. |
| **Entity** | A distinct in-world Factorio object. Count it separately from the item that places or equips it. |
| **Placeable entity** | An entity that can be placed in the world. It is a subset of entities and often has a corresponding constructable item. |
| **Machine family** | A group of equipment with the same primary industrial role and capability progression. Count the family separately from each buildable tier or entity. |
| **Tier / variant** | A distinct progression version within a product or machine family. Count separate item/entity variants individually when they are distinct game objects; do not count them as separate families. |
| **Technology** | A research node that consumes research ingredients and unlocks defined capabilities. Count independently from the ingredients and unlocks. |

Do not use one count as a proxy for another. For example, a tiered machine family may be one family, several entities, several constructable items, and several recipes.

## Scope Labels

Apply one or more scope labels independently of product class:

- **Core:** required in the main mod experience.
- **Vanilla retained:** existing Factorio content remains in use without a Prometheus replacement.
- **Vanilla modified:** existing Factorio content remains but its behavior, recipe, or progression is changed.
- **Vanilla replaced:** a Prometheus design intentionally replaces existing Factorio content.
- **Extension:** optional content outside core scope; note its core dependencies.

Keep counts for these scope labels separate. In particular, do not treat vanilla-retained content as new Prometheus products or include extension-only content in core totals.
