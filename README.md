# La Malédiction de Brumefer

Jeu de rôle **en solo**, en français, dans un univers de dark fantasy, aux règles de la 5ᵉ édition (SRD 5.1). Le joueur crée son héros, puis un **meneur de jeu joué par Claude** raconte l'aventure, joue les personnages et arbitre les actions. La page, elle, tient les règles : jets de dés, combats, inventaire, argent, temps qui passe et cartes.

Tout le jeu tient dans un seul fichier, `brumefer.html`, publié comme artefact Claude.

## La campagne

Une longue campagne mène le héros du niveau 1 au niveau 40. Le joueur reste libre de ses choix, et le meneur de jeu improvise en restant fidèle à l'histoire.

> **Attention, révélations** : `brumefer.html` contient tout le scénario. Ses textes sont encodés, mais le code garde des indices : pour garder la surprise, joue avant de lire le code.

## Ce que fait le jeu

- **Création du héros** : peuples, classes, historiques, caractéristiques, multiclassage, sorts et équipement acheté ou de départ, selon le SRD 5.1.
- **Meneur de jeu Claude** : narration, dialogues, tests demandés au bon moment. Chaque tour, il reçoit l'état exact de la partie et doit le respecter :
  - le héros (PV, CA, charge, compagnon) et les quêtes, avec leur condition de fin ;
  - la partie et les actes en cours ;
  - les personnages connus ;
  - la date du calendrier.
- **Règles tenues par la page** :
  - jets avec avantage et désavantage ;
  - combats au tour par tour ;
  - repos et niveaux, y compris les niveaux épiques 21 à 40 ;
  - argent en po, pa et pc ;
  - poids et encombrement en kg ;
  - compagnons animaux et montures.
- **Monde suivi** :
  - le Carnet : personnages, lieux, quêtes et faits établis ;
  - les cartes de région, de ville et de donjon ;
  - un calendrier de 7 jours nommés et de fêtes ;
  - les domaines et leurs rentes hebdomadaires ;
  - les titres.
- **Mémoires du héros** : un chapitre par jour de jeu, exportable en document Word.
- **Sauvegardes** : plusieurs emplacements, sauvegarde en ligne sur ton compte Claude pour reprendre ta partie sur un autre appareil (ordinateur, iPhone, iPad, Android), export et import en fichier `.txt`.

## Jouer

Le jeu est fait pour tourner comme **artefact Claude** sur claude.ai : le meneur de jeu passe par la capacité `sample` de l'artefact. Ouvert directement dans un navigateur, le fichier permet de créer un héros et de consulter une partie, mais le meneur de jeu ne répond pas.

Chaque joueur publie **sa propre copie** du jeu, sous son propre compte Claude : aucun lien de partie n'est diffusé. Le guide [INSTALLATION.md](INSTALLATION.md) détaille toutes les étapes : publication de sa copie, reprise sur un autre appareil, outils de développement.

Pour reprendre une partie exportée : **Sauvegarde → Charger un fichier .txt**. Les parties exportées (`brumefer-<héros>-niv<N>-<date>.txt`) restent sur le disque et ne sont pas envoyées sur GitHub.

## Contenu du dépôt

| Élément | Rôle |
|---|---|
| `brumefer.html` | le jeu complet : interface, règles, consignes du meneur de jeu ; les textes du scénario y sont encodés pour ne pas être lus par hasard |
| `carto/` | tuiles, icônes et textures des cartes |
| `CHANGELOG.md` | journal des versions (le même que dans le jeu, bouton de version) |
| `INSTALLATION.md` | guide d'installation |
| `CONTRIBUTING.md` | comment proposer une modification ou une idée |
| `LICENSE` | licence du projet et des éléments repris |

Le numéro de version suit le versioning sémantique `MAJEUR.MINEUR.CORRECTIF`. Tant que le jeu est en `0.x`, le format des sauvegardes peut encore changer ; les anciennes sauvegardes sont migrées au chargement.

## Contribuer

Les propositions passent par un fork et une pull request ; seul l'auteur décide de ce qui entre dans le jeu. Voir [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

**CC BY-NC-SA 4.0** : tu peux jouer, copier, partager et modifier le jeu en créditant « La Malédiction de Brumefer, par Orna », sans usage commercial, et en diffusant tes modifications sous la même licence. Détails dans [LICENSE](LICENSE).

Éléments repris d'autres projets, sous leur propre licence :

- Règles : éléments du **System Reference Document 5.1** de Wizards of the Coast LLC, sous licence [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0). Jeu non officiel, sans lien avec Wizards of the Coast. Les historiques (hors Acolyte), les noms, le scénario et les textes d'ambiance sont propres à Brumefer.
- `carto/wn/` : tuiles et villages de [Battle for Wesnoth](https://wesnoth.org) (GPL v2+ / CC BY-SA 4.0).
- `carto/icon/` : icônes de [game-icons.net](https://game-icons.net) par Lorc, Delapouite, Skoll, sbed et faithtoken (CC BY 3.0).
- `carto/tex/` : textures [ambientCG](https://ambientcg.com) (CC0).
