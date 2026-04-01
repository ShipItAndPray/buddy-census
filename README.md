# The /buddy Census

**[Live Demo](https://shipitandpray.github.io/buddy-census/)**

Live population dashboard for Claude Code's `/buddy` feature. Enter your username, verify your species deterministically via Mulberry32 PRNG, and see where you land in the global census.

## Features

- **Instant species lookup** -- enter your Claude username, get your buddy (species, rarity, eyes, hat, stats, shiny status)
- **Species distribution chart** -- 18 horizontal bars showing population counts, sorted by frequency
- **Rarity breakdown** -- donut chart comparing actual vs theoretical distribution (Common 60% / Uncommon 25% / Rare 10% / Epic 4% / Legendary 1%)
- **Shiny tracker** -- count of confirmed shinies (1% chance per buddy)
- **Hall of Legendaries** -- gallery of all registered Legendary buddies with ASCII sprites
- **Mass simulation** -- simulate 1K/10K/50K buddies to validate theoretical distributions
- **All 18 species** -- duck, goose, blob, cat, dragon, octopus, owl, penguin, turtle, snail, ghost, axolotl, capybara, cactus, robot, rabbit, mushroom, chonk

## How it works

All computation runs client-side. The PRNG (Mulberry32) and hash function match Claude Code's `companion.ts` exactly, so the species/rarity you see here is the same one you'd get in your terminal. Registrations persist in localStorage.

## Tech

- Single `index.html`, zero dependencies
- Mulberry32 PRNG + FNV-1a hash (matching Claude Code source)
- Canvas-based donut chart
- Dark terminal aesthetic, mobile responsive
- localStorage for persistence

## Species & Rarity

| Rarity | Weight | Probability |
|---|---|---|
| Common | 60 | 60% |
| Uncommon | 25 | 25% |
| Rare | 10 | 10% |
| Epic | 4 | 4% |
| Legendary | 1 | 1% |

Shiny chance: 1% (independent of rarity). Hats: commons get none, all others roll from 8 hat types.

---

Powered by [ShipItAndPray](https://github.com/ShipItAndPray)
