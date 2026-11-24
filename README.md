# La Malédiction de Brumefer

A **solo** tabletop role-playing game set in a dark fantasy world, using the 5th edition rules (SRD 5.1). The player creates a hero, then **Claude acts as the game master**: it tells the story, plays the characters and rules on the player's actions. The page itself keeps the rules: dice rolls, combat, inventory, money, the passage of time and maps.

The whole game is a single file, `brumefer.html`, published as a Claude artifact.

> **Language:** the game is currently in **French only** (interface, story and game master). The documentation is in English so that anyone can contribute.

## The campaign

A long campaign takes the hero from level 1 to level 40. The player makes their own choices, and the game master improvises while staying true to the story.

> **Spoiler warning:** `brumefer.html` contains the whole story. Its texts are encoded, but the code still holds clues: to keep the surprise, play before you read the code.

## What the game does

- **Hero creation**: peoples, classes, backgrounds, ability scores, multiclassing, spells, and starting or purchased equipment, following the SRD 5.1.
- **Claude as game master**: narration, dialogue, checks asked for at the right moment. Each turn, it receives the exact state of the game and must respect it:
  - the hero (HP, AC, load, companion) and the quests, with their completion conditions;
  - the current part and acts of the campaign;
  - the known characters;
  - the calendar date.
- **Rules kept by the page**:
  - rolls with advantage and disadvantage;
  - turn-based combat;
  - rests and levels, including epic levels 21 to 40;
  - money in gold, silver and copper pieces;
  - weight and encumbrance in kilograms;
  - animal companions and mounts.
- **A tracked world**:
  - the Notebook: characters, places, quests and established facts;
  - region, town and dungeon maps;
  - a calendar of 7 named days and festivals;
  - estates and their weekly income;
  - titles.
- **The hero's memoirs**: one chapter per game day, exportable as a Word document.
- **Saves**: several slots, online saving on your Claude account to continue a game on another device (computer, iPhone, iPad, Android), export and import as a `.txt` file.

## Playing

The game is designed to run as a **Claude artifact** on claude.ai: the game master works through the artifact's `sample` capability. Opened directly in a browser, the file lets you create a hero and browse a game, but the game master does not answer.

Each player publishes **their own copy** of the game under their own Claude account: no shared game link is provided. [INSTALLATION.md](INSTALLATION.md) covers every step: publishing your copy, continuing on another device, development tools.

To resume an exported game: **Sauvegarde → Charger un fichier .txt** (Save → Load a .txt file). Exported games (`brumefer-<hero>-niv<N>-<date>.txt`) stay on your disk and are never sent to GitHub.

## Repository contents

| Item | Purpose |
|---|---|
| `brumefer.html` | the complete game: interface, rules, game master instructions; the story texts are encoded so they are not read by accident |
| `carto/` | map tiles, icons and textures |
| `CHANGELOG.md` | version history, in French (the same as in the game, version button) |
| `INSTALLATION.md` | installation guide |
| `CONTRIBUTING.md` | how to propose a change or an idea |
| `LICENSE` | license of the project and of the third-party assets |

Version numbers follow semantic versioning, `MAJOR.MINOR.PATCH`. While the game is at `0.x`, the save format may still change; older saves are migrated when loaded.

## Contributing

Contributions go through a fork and a pull request; only the author decides what goes into the game. See [CONTRIBUTING.md](CONTRIBUTING.md).

### Calls for contributions

1. **[Interface, maps and game experience (UX/UI)](https://github.com/ornacea/brumefer/issues/2)**: readability of the game screen, touch input on phones, a simpler hero creation, clearer and better-looking maps, accessibility, visual identity. Pull requests to `main`, with before and after screenshots.
2. **[Read-aloud narration](https://github.com/ornacea/brumefer/issues/1)**: removed from `main` in version 0.89.0, it is kept in the [`voix`](https://github.com/ornacea/brumefer/tree/voix) branch (as of version 0.88.0: browser voices and VoiceStudio, one voice per character). Reliability, more natural voices, phones, simpler settings: pull requests to `voix`.

Each issue details the ideas and how to proceed. Simple feedback on what bothered you while playing is welcome too.

## License

**CC BY-NC-SA 4.0**: you may play, copy, share and modify the game, as long as you credit "La Malédiction de Brumefer, by Orna", make no commercial use of it, and share your changes under the same license. Details in [LICENSE](LICENSE).

Assets taken from other projects, under their own licenses:

- Rules: material from the **System Reference Document 5.1** by Wizards of the Coast LLC, licensed under [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0). Unofficial game, not affiliated with Wizards of the Coast. Backgrounds (except Acolyte), names, story and flavor texts are original to Brumefer.
- `carto/wn/`: tiles and villages from [Battle for Wesnoth](https://wesnoth.org) (GPL v2+ / CC BY-SA 4.0).
- `carto/icon/`: icons from [game-icons.net](https://game-icons.net) by Lorc, Delapouite, Skoll, sbed and faithtoken (CC BY 3.0).
- `carto/tex/`: [ambientCG](https://ambientcg.com) textures (CC0).
