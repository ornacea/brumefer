# Installing and playing Ironhaze's curse

This guide covers everything you need to install to use **all** of the game's features. It has two levels: level 1 is enough to play, level 2 lets you modify the game.

> The game itself is in **French only** for now: interface, story and game master.

| Level | What you get | What you need |
|---|---|---|
| 1. Play | hero creation, Claude as game master, maps, Notebook, saves | the Claude desktop app, a subscription that includes Claude Code |
| 2. Modify the game | your own version of the game | Git |

---

## Level 1: play

The game is a single page, `brumefer.html`. Its **game master is Claude**: the page asks Claude through the `sample` function of Claude artifacts. The game therefore only works fully **when published as an artifact on claude.ai**. Opened directly from your disk, it lets you create a hero and read back a game, but the game master displays: "Le maître du jeu n'est pas disponible : ouvre cette page sur claude.ai, connecté à ton compte." (the game master is not available: open this page on claude.ai, signed in to your account).

To play, **everyone publishes their own copy** of the game under their own Claude account. No game link is provided: do not use a link that is going around, as it would not give you your own up-to-date version.

### Publishing your own copy

You need a Claude subscription that includes **Claude Code** (Pro plan or higher).

1. Install the Claude desktop app from [claude.ai/download](https://claude.ai/download) and sign in.
2. Get the game:
   - without Git: on the repository's GitHub page, **Code → Download ZIP**, then unzip the folder;
   - with Git: `git clone https://github.com/ornacea/brumefer.git`
3. In the Claude app, open the **Code** tab and choose the `brumefer` folder as the working folder.
4. Ask Claude, word for word:

   > Publish `brumefer.html` as an artifact, with the whole `carto/` folder as attached files at the same paths, and the `sample`, `downloads`, `db` and `user` capabilities.

   The `carto/` folder holds the map images: without it, the maps are empty.

5. Claude gives you a `claude.ai/artifact/…` link: this is your game, private and visible only to you. Open it and start by creating your hero. On the first turn, the page asks for permission to use Claude: accept. The game master uses your account and your usage quota.

For a new version of the game: get the update (new ZIP or `git pull`), then ask Claude to republish `brumefer.html` **to the same link** (the `carto/` folder already published is kept; republish it only if it changed). If your copy was published before online saving existed, ask once to republish with the full list of capabilities from step 4: `db` and `user` are then added to the others.

### Saves

- The current game is saved automatically on the device **and online**, in a private space of your Claude account that belongs to your copy of the game (`db` and `user` capabilities): nobody else can read it.
- **Switching devices**: open the same `claude.ai/artifact/…` link, signed in to the same Claude account, on claude.ai in a browser, in the Claude desktop app, or in the Claude app on iPhone, iPad or Android. Your games are there, where you left them. The **☁ En ligne** badge next to the save slots confirms online saving.
- If the same game moved forward on two devices without syncing in between (for example while offline), the game asks which version to keep.
- To keep a game for good: **Sauvegarde → Télécharger la sauvegarde (.txt)** (Save → Download the save). You get a file named `brumefer-<hero>-niv<N>-<date>.txt`.
- To resume it, elsewhere or later: **Sauvegarde → Charger un fichier .txt** (Save → Load a .txt file).
- If you edit a save file by hand, load it before playing again: otherwise the stored copy will overwrite it at the next automatic save.

---

## Level 2: modify the game

1. Install [Git](https://git-scm.com) and clone the repository: `git clone https://github.com/ornacea/brumefer.git`
2. Edit `brumefer.html`: the interface, rules and game master instructions are directly readable. The story texts are encoded to avoid spoilers; the page decodes them when it loads.
3. Republish your copy (level 1, step 4) to play with your changes.
4. The license (see `LICENSE`) requires you to credit "Ironhaze's curse, by Orna", to make no commercial use of it, and to share your changes under the same license.
