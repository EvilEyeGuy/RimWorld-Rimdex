# Rimdex

![Rimdex](https://raw.githubusercontent.com/EvilEyeGuy/RimWorld-Rimdex/workshop/preview.png?v=4)

A dynamic in-game encyclopedia that connects items, creatures, recipes, research,
workbenches and more across your loaded mods. On a normal medieval modlist that
comes to around 8000 pages.

Rimdex was originally built for
[Medieval Overhaul](https://steamcommunity.com/sharedfiles/filedetails/?id=3219596926),
where the same questions kept coming up. Where does this come from, how is it
processed, what is a golem corpse good for. The answers now come out of the
game's own definitions instead of out of a forum thread, and a good deal more
with them. Nothing in it is tied to Medieval Overhaul, which is why it works on
any modlist. Medieval Overhaul simply gets the deepest coverage, because that is
where the questions started.

For any item it answers the two questions the game itself never answers: where
does this come from, and what is it for. Everything is linked, so you can follow
a chain instead of guessing, from a locked research to the schematic it needs,
to the ruin that schematic drops in and the odds of finding it there.

## What a page shows

![What a page shows](https://raw.githubusercontent.com/EvilEyeGuy/RimWorld-Rimdex/workshop/02_what_it_shows.png?v=3)

1. Search by name or def name
2. Filter the list by category, by mod, or by where something comes from
3. Every entry in the list opens its own page
4. Pick the material, the values below change with it
5. Values, and where the thing is on your maps right now
6. Click a heading to fold the section away
7. Rows are links, they open the page behind them

## What it covers

- **Items, buildings, plants and materials**: recipes, processing chains,
  mining, harvesting, smelting, construction costs and stats
- **Creatures**: combat power, armour, attacks with damage per second, and where
  they occur: biomes with commonality, events, factions, or the container they
  hide in
- **Pawns**: every pawn kind with its faction variants, skills, possible weapons
  and apparel, plus a generated example
- **Factions, traders and royal titles**, including full room and apparel
  requirements
- **Research**: what it unlocks, what it leads to, and what blocks it, meaning
  schematics, techprints, benches and prerequisites
- **Structures**: the ruins and hideouts of the world generator, drawn as a floor
  plan in the colours of the materials they are built from, with every possible
  layout as a tab, what you can loot there, and how you come across the place
- **Quests**: the name the game would show you, the written text where it
  resolves to plain words, threat points, challenge rating, expiry, where it
  takes you and which quest it hangs off
- **Genes, memes and precepts**: cost and carriers for a gene, and for a precept
  what it does to mood and on which occasion, which memes need it, go with it or
  fight it, and what you could pick instead. Rituals sit in the same list
- **Abilities and health conditions**: cast time, range, cooldown and what an
  ability applies. A condition walks its stages with pain, capacities and stats
  for each one, says whether it worsens or heals on its own, and names what
  causes it and what gets rid of it
- **Traits and backstories**: one block per trait degree with its own text and
  numbers, and for a backstory the skills it teaches, the work it rules out for
  life, the traits it settles and which pawn kinds turn up with it

Content from an expansion says so. The badge in the corner of a page names
Royalty, Ideology, Biotech, Anomaly or Odyssey the same way it names a mod.

While a game is running, each page also shows where that thing currently is on
your maps, in stockpiles, carried by a pawn or out with a caravan. Clicking the
entry jumps the camera there, and clicking again walks through the other copies.

Floor plans give away what a ruin looks like inside, so they start blurred and
uncover on a click. You can turn that off in the mod settings.

## Two views

![Two views](https://raw.githubusercontent.com/EvilEyeGuy/RimWorld-Rimdex/workshop/03_two_views.png?v=5)

1. The full view shows the whole page
2. The compact view is a small panel you can leave open while playing. It
   follows your current selection, so clicking something on the map updates the
   panel to that page

The button in the top right switches between them, and the game remembers which
one you selected.

Every page opens with all of its sections unfolded. Fold away the ones you
never read and the heading keeps the number of entries behind it, so nothing
disappears without saying so.

Anything built from a material carries a picker. Choose granite instead of wood
and the market value, the mass, the hit points, the beauty and the work all
follow. Opening Rimdex from something on your map sets the material for you.

## Where to open it

![Where to open it](https://raw.githubusercontent.com/EvilEyeGuy/RimWorld-Rimdex/workshop/04_where_to_open.png?v=5)

1. The book button in the bottom right toggle row
2. The button beside the info button when something is selected
3. The button in the info card

The window also remembers the last page you opened.

## What it reads

Nothing is hard-coded. The index is generated at runtime from whatever mods you
have installed, so it stays correct when they update and it covers modded content
the same way it covers vanilla.

Most normal Def based content is picked up automatically. Some mods carry their
own mod extensions or special code. Rimdex reads those too and links what
belongs together, but it cannot always tell what a mechanic means, so a few mods
may need extra support for certain mechanics. If a mod is missing something
important, open an issue and I can have a look.

The Medieval Overhaul support reads what is otherwise invisible: monster drop
chances, loot table percentages, which schematic a research project needs, which
container a mimic is hiding in, and what the Explorer's Workbench can discover.

With Combat Extended loaded, the vanilla ranged numbers are wrong, so they are
not shown. In their place you get the real ones: range, minimum range, warmup,
burst, recoil, magazine, reload time, sight efficiency and bulk, plus every
ammunition type the weapon fires with its armour penetration.

## Performance

![Performance](https://raw.githubusercontent.com/EvilEyeGuy/RimWorld-Rimdex/workshop/05_performance.png?v=2)

Nothing is built while the game starts. The index is put together the first time
you open the window in a session, with a progress bar, and on a big mod list that
takes a moment. Every time after that it opens instantly. If you never open it,
that work never happens at all.

Drawing was measured with Dubs Performance Analyzer on a paused colony. With the
window open on its heaviest page it costs about 1.04 ms per frame, roughly the
same as the vanilla work tab at 1.02 ms and a fifth of the vanilla research tree
at 4.90 ms. In the small panel view the same page costs about 0.25 ms, so
leaving it open beside the game is close to free. The live occurrence lookup
refreshes every few seconds and does not register.

## FAQ

**Does Rimdex require Medieval Overhaul?**
No. It works with any mod list.

**Does it spoil ruins?**
Floor plans are blurred by default.

**Does it slow down startup?**
No. The index is built when you open Rimdex.

**What if a mechanic is missing?**
Open an issue and I can look into it.

## Requirements

Harmony. Nothing else.

## Installing from here

Download the repository and drop the folder into `RimWorld/Mods`. The built
assembly is included, so nothing needs to be compiled.
