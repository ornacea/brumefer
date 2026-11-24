# Contributing to Ironhaze's Curse

Thank you for wanting to help! Proposals are welcome: rule fixes, bugs, interface, accessibility, maps, adventure ideas.

The game itself is in French. You can contribute in English: issues, pull requests and discussions in English are fine.

## Repository rules

- **For now, only the author (@ornacea) decides** what goes into the game. The `main` and `voix` branches are protected: nobody else can write to them, either directly or through a merge.
- This rule is not set in stone: if the number of contributors grows and the project lives on over time, it may evolve towards something more open and democratic.
- This repository is the **public export** of the game. Each version arrives here as a single "Version X.Y.Z" commit, from the author's working source. An accepted proposal is therefore **not merged as is**: the author carries it over into the source, and it ships in the next version. The pull request is then closed with a note naming the version that includes it.

## Proposing a change

1. Make a copy of the repository on your account (**Fork**).
2. Create a branch for your proposal, for example `fix-initiative` or `map-legend`.
3. Edit `brumefer.html` and check your change in your own published copy of the game (see [INSTALLATION.md](INSTALLATION.md)).
4. Open a **pull request** to `main`, explaining:
   - what your change does for the player;
   - how the author can check it in the game;
   - whether older saves are affected.

A short pull request that does one thing is much more likely to be accepted.

## Calls for contributions

Two areas are open as a priority. Each issue details the ideas; comment on it to say what you are taking on, especially for a large piece of work.

### 1. Interface, maps and game experience (UX/UI): [issue #2](https://github.com/ornacea/ironhaze/issues/2)

Readability of the game screen, touch input on phones, a simpler hero creation, clearer and better-looking maps, accessibility, visual identity.

1. In your fork, create your branch **from `main`**.
2. Test on a computer and on a phone, in both the light and dark themes.
3. Open your pull request **to `main`**, with before and after screenshots.
4. Images, fonts and icons: only under a compatible license (CC0, CC BY, CC BY-SA, open fonts), with their source and license stated. No new dependency loaded from the Internet.

### 2. Read-aloud narration, `voix` branch: [issue #1](https://github.com/ornacea/ironhaze/issues/1)

Reading the story aloud was removed from `main` in version 0.89.0. Its code is kept in the [`voix`](https://github.com/ornacea/ironhaze/tree/voix) branch, as of version 0.88.0: reliability, more natural voices, phones, simpler settings.

1. In your fork, create your branch **from `voix`**.
2. Open your pull request **to `voix`**, not to `main`.
3. Once read-aloud narration is solid enough, it will come back to `main`.

## Reporting a problem or suggesting an idea

Open an issue (**Issues → New issue**) with:
- what you did, what you expected, what happened;
- the game version (version button at the top of the page);
- if possible, your exported save (`.txt`), without personal data.

## The story

The story texts are encoded in `brumefer.html` so they are not read by accident: a change to these texts is unreadable in a pull request. For the story, characters or places, **describe your idea in an issue** rather than editing the code.

**No spoilers** in issues, pull requests or commit messages: other players read them before finishing the adventure. If you need to talk about a specific passage, stay vague or describe it without naming who or what.

## License of your contributions

By submitting a contribution, you agree that it is distributed under the project's license, **CC BY-NC-SA 4.0** (see [LICENSE](LICENSE)), and that the author may adapt it when integrating it. Accepted contributions are credited in the version history.

Only add content you hold the rights to: no text, image or sound taken from another game or a protected work, and, for the rules, only SRD 5.1 material.

## Respect

Be kind in discussions. Aggressive or off-topic messages are closed.
